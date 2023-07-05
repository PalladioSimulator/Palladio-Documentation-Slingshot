---
layout: page
parent: Slingshot Framework
title: The Event-Driver Module
permalink: /slingshot-simulator/event-driver/
nav_order: 1
---
# Event-Driver
As already said, Slingshot is based on the event-driven architecture. Thus, one of the core modules of the framework is the **Event-Driver**, which provides an *event bus* for handling events and delegating them to the right subscriber. More specifically, Slingshot follows the Publish-Subscriber paradigm: As soon as an event is *published*, all *subscriber* to that event will be executed.

Slingshot registers subscribers via annotations. Currently, there are four annotations that can be used:
* `@Subscribe`
* `@PreIntercept`
* `@PostIntercept`
* `@OnException`

## Events
In the event-driver, an event is a Java *object*. This means essentially that every object can be interpreted as an event and posted to the bus. The event-bus delegates the instantiated event to the *subscriber*.

To provide an event, simply *post* the event:
```java
final Object event = new Object();
eventBus.post(event);
```

### Event Contracts
There are multiple ways to restrict the possibilities from where events can be published, and who can listen to which events. For example, assume that an event of type `SomeEvent` can only be published by `ClassA` and `ClassB`, and only listened by classes inside the package `org.example.eventlistener`. Then you define the event type as follows:

```java
@PublishableBy(classes = {ClassA.class, ClassB.class})
@ListenableBy(packages = "org.example.eventlistener")
public class SomeEvent {
    ...
}
```

Now, if a class other than `ClassA` or `ClassB` tries to publish the event, the exception `IllegalPublisherException` will be thrown and the execution stopped. Furthermore, if a listener class that is not within the `org.example.eventlistener` package tries to listen to this event,
the `IllegalListenerException` will be thrown.

Fortunately, if you are correctly using the `@OnEvent` (see below) annotation, the annotation processor can already determine whether you are using the events illegally at compile-time.

{: .note }
> In these annotations there is also a `bundles` property. The idea was to restrict events to be publishable/listenable by certain OSGi bundles. However, this functionality is not implemented (yet), and will be ignored.

If these annotations are not specified, then the default is always assumed. Furthermore, there is an order of restriction, from more restrictive to least: class >> package >> bundle. This means that if both class and packages are specified, then only the classes are considered.

#### @PublishableBy

| Property | Type | Description | Default |
| :------- | :--- | :---------- | :------ |
| `classes` | `Class<?>[]` | Array of classes that are allowed to publish this event | empty, meaning that every class can publish it |
| `packages` | `String[]` | Array of package names, whose classes are allowed to publish this event | empty, meaning that every package can publish it |
| `bundles` | `String[]` | *ignored* | empty |


#### @ListenableBy

| Property | Type | Description | Default |
| :------- | :--- | :---------- | :------ |
| `classes` | `Class<?>[]` | Array of classes that are allowed to publish this event | empty, meaning that every class can listen to it |
| `packages` | `String[]` | Array of package names, whose classes are allowed to publish this event | empty, meaning that every package can listen to it |
| `bundles` | `String[]` | *ignored* | empty |

## Subscriber
A subscriber is a method that *subscribes* or listens to a specific event. The type of event is determined by the parameter type of the method.
```java
@Subscriber
public Result onSomeEvent(final SomeEvent event) {
    // do something
    return Result.of(new AnotherEvent());
}
```
The signature of the method is fixed: It needs to be a **public**, **non-static** method; the return type must either be `Result` or `void`, and it must have exactly one parameter with the type of the event you want to subscribe to.

The `Result` contains a set of new events that shall be published afterwards. If there are no new events to be published, then simply return `Result.empty()` or declare the method as `void`.

### Prioritization
The annotation consists of one `int priority()` parameter. It tells how the order of events should be executed. The default value is `0`. The higher the number, the more prioritized the event should be. Example: `@Subscribe(priority = 2)`.

### Contract `@OnEvent`
Each subscriber must specify a contract of what events will be published afterwards. The contracts are given on class level:

```java
@OnEvent(when = SomeEvent.class, then = { EventOne.class, EventTwo.class }, cardinality = SINGLE)
class EventHandlers {

    @Subscribe
    public Result onSomeEvent(final SomeEvent event) {
        //...
        return Result.of(new EventOne());
    }

}
```

The `cardinality` tells how many events will be published after this one: It can be either `SINGLE` or `MANY`. `then` tells the possible events that could result afterwards. It could specify more events than the actual published ones. 

## Interceptors: `@PreIntercept` and `@PostIntercept`
It is possible to intercept event subscribers by using the `@PreIntercept` or `@PostIntercept` annotations on methods. Interceptors are generally able to abort an event, or give further information to an event. You can use interceptors to log events as well. Unlike `@Subscribe`, the event that is specified can be any super-type (while `@Subscribe` requires a concrete type).

Interceptor are generally specified by parameters of `InterceptorInformation` and the actual event type to intercept. The interceptor must return some value of `InterceptorResult`. Example:

```java
@PreIntercept
public InterceptorResult preInterceptSomeEvent(final InterceptorInformation information, final SomeEvent event) {
    LOGGER.info("Some event is about to be dispatched by the method " + information.getMethod().getName());
    
    return InterceptorResult.success();
}

@PostIntercept
public InterceptorResult postInterceptSomeEvent(final InterceptorInformation information, final SomeEvent event) {
    LOGGER.info("Result is " + information.getResult());
    return InterceptorResult.success();
}
```

### InterceptorInformation
This class contains information about the subscriber method that is about to be called, or was called.

| Property | Type | Description |
| :------- | :--- | :---------- |
| `method` | `Method` | The subscriber method |
| `target` | `Object` | The target object on which the method will be / was called. |
| `result` | `Result` | The result that was returned by the method. This can be `null`, especially if the information is for *pre* intercepting. |

### InterceptorResult
The interceptor result can contain further information about what to do next. It is possible to continue, abort, provide exceptions, and so on.

## Error Handlers: `@OnException`
During subscriber handling, exceptions can occur. Typically, the exception will not be processed but simply printed out, and the execution continued.

The handler is similar to `@Subscriber` methods. The method contains the information about where the exception occurred, to which event, and which exception.

An exception handler can then decide what should happen next: Continue execution, abort the overall execution, "rethrow" to the next exception handler, and/or return another result replaced by the result of the subscriber method:

```java
@OnException
public ExceptionResult onIllegalArgumentException(final ExceptionInformation information, final IllegalArgumentException exception) {
    LOGGER.info("Illegal argument exception occured. Abort execution completely!");
    return ExceptionResult.abort();
}
```

As you can see, the exception to listen to is specified in the second argument. The exception type does not need to be concrete, but can be any super-type as well. However, exception handlers with a more concrete type have higher precedence. Exception handlers with more abstract types will be ignored in this case, unless the handler returns `ExceptionResult.rethrow(exception)`.

If there are more exception handlers of the same type (on the same level), then all of these handlers will be executed in arbitrary order. The result will be collected, and using the cumulated result, the event driver will decide on how to continue:

* If one results in `abort`, the cumulated result will say `abort`.
* If one results in `rethrow`, the cumulated result will say `rethrow`.
* If one results in `replace`, the new result will be collected, and afterwards the union of all results will be used.
* If everyone results in `continue`, then the cumulated result will say `continue`.

### ExceptionInformation

### ExceptionResult