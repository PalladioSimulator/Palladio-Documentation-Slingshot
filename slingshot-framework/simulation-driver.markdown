---
layout: page
parent: Slingshot Framework
title: The Simulation-Driver Module
permalink: /slingshot-framework/simulation-driver/
nav_order: 3
---
# Simulation-Driver

The simulation driver is a module that concerns about *simulation events*. Unlike system events, simulation events carry time information that are important to the event-based simulation world view.

The simulation driver will be called upon running "Run" in the launch configuration. It loads all the `SimulationBehaviorExtension`s and fires `SimulationStarted`.

Thus, to make your extension being called eventually, make sure that there is a path from the events you listen to `SimulationStarted`, or listen directly to it. If there is no such path, this event will never be published and therefore your handles will never be called.

## Simulation Events
As already mentioned, simulation events carry time information. In Slingshot, every simulation event must implement the `DESEvent` interface. Here, *DESEvent* stands for *Discrete Event(-based) Simulation Event*.

Unlike system events, however, it is not possible to publish events from the outside. That is, you cannot load this module into your extension and directly post an event there. You must only publish events by returning them in the `Result` type.

If you want to specify that your event should be published as soon as possible but with some delay, then the event class should return that information in `getDelay()`.

Furthermore, if you want to specify that your event should be published at a specific time (in future), then the event class should return that information in `getTime()`.

How this information is set depends on the implementation of `DESEvent`. For example, in most Slingshot events that are present in the standard simulators, the information can be given in the constructors:

```java
@Subscribe
public Result onSomeEvent(final SomeEvent event) {
    return Result.of(
        new AnotherEvent(DESEvent.NOW, 4), // Post this event now, but with a delay of 4ms
        new AnotherEvent(98765, 1), // Post this event at 98765ms simulation time, and with a delay of 1ms
    ); 
}
```

But you could also use builders, or even not give the ability to set this information.

After **all** simulation events have been processed, and no new simulation events happen, the `SimulationDriver` module will fire `SimulationFinished` one last time, and it closes the registration of new events. You are again able to listen to this event (i.e. for clean-up), but your returned events will be ignored.