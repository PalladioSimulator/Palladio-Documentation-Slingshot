---
layout: page
grand_parent: Slingshot Simulator
parent: The System-Driver Module
title: UI and Workflow
permalink: /slingshot-simulator/system-driver/ui/
nav_order: 1
---
# UI and Workflow
In Slingshot, the only UI components that can be added are launch configuration tabs and text fields to the so-called *architectural tab*. Slingshot enables the ability to add other model types that are not standard in PCM, and let you provide the functionality to add new text-fields in the launch configuration, so that the user can select the model of your model-type.

## 1. Creating a Text-Field in the Launcher

First, the user should be able to specify the model file that should be considered during the simulation. This can be done by adding a file picker text field in the Launch configuration.

These extensions are also made in an event-driven way. The following figure shows the flow of how UI components are added and how custom model files can be registered in slingshot.

<img src="../../../images/ui_workflow.svg" />

Thus, to add another text-field to the Slingshot Launcher, you must register the following extension as a `SystemBehaviorExtension`:

```java
@OnEvent(when = ArchitectureModelsTabBuilderStarted.class)
public class UsageModelLaunchConfig implements SystemBehaviorExtension {

	public static final String FILE_NAME = "usagemodel"; 
	
	@Subscribe
	public void onArchitectureModelsTab(final ArchitectureModelsTabBuilderStarted event) {
		event.newModelDefinition() // Create a new model definition
			 .fileName(FILE_NAME) // Specify the required file ending
			 .modelClass(UsageModel.class) // To which EMF Model it belongs
			 .label("Usage Model") // Label for the Text Field
			 .build(); // register it
	}
	
}
```

Install it in your module and run the Eclipse instance. The following result should appear as soon as you try to create a new Slingshot run configuration:
<img src="../../../images/run_configuration.png" />

## 2. Register the Custom Model into the Resource Set
In EMF, a `ResourceSetPartiton` is a class that contains all the resources that need to be considered. Now, the above extension only creates the text field, but it does not add it to the resource set partition. To do so, you need to subscribe to another event:

```java
@OnEvent(when = WorkflowLaunchConfigurationBuilderInitialized.class)
public class UsageModelWorkflowConfig implements SystemBehaviorExtension {

	@Subscribe
	public void onWorkflowConfiguration(final WorkflowLaunchConfigurationBuilderInitialized init) {
		init.getConfiguration(UsageModelLaunchConfig.FILE_NAME, 
				"usageModel", 
				(conf, model) -> conf.setUsageModelFile((String) model));
	}
	
}
```

The `conf` is of type `PCMConfiguration`. If the specified model file is not part of the standard PCM framework, you set it by `addModelFile`. Notice that `model` is of type `Object`.

To get the right configuration, you must specify the right key, which typically is the same as the file name / ending.

Note: You do not have to create another class for it. The above handler can also be put in the same class as the UI text-field creator. Just make sure that you do not mix up `SystemBehaviorExtension`s and `SimulationBehaviorExtension`s.

## 3. Provide model Instance for other Simulators to Use
While the model can now be loaded into the PCM configuration, there is still no real Java instance of that model yet. Simulators should be able to get that instance by injecting it into their constructor. To make this possible, you need to *provide* your instance. Thus, this time you bind the instance by a provider, instead of doing it event-drivenly, since you need to make Guice aware of your instance.

### Provide by a Provider Class

First, create a provider for your model:

```java
public class UsageModelProvider implements Provider<UsageModel> {

    private final Provider<PCMResourceSetPartition> resourceSetPartition; // Lazy loading.

    @Inject
    public UsageModelProvider(final Provider<PCMResourceSetPartition> resourceSetPartition) {
        this.resourceSetPartition = resourceSetPartition;
    }

    @Override
    public UsageModel get() {
        return resourceSetPartition.get().getUsageModel();
    }

}
```

Then, register your provider in your module. More specifically, write the following code in your `configure()` method of the module class:

```java
// We want to provide the UsageModel by our UsageModelProvider
provideModel(UsageModel.class, UsageModelProvider.class);
```

Or, alternatively, you can call Guice directly:

```java
bind(UsageModel.class).toProvider(UsageModelProvider.class);
```

With the above code, Guice will be able to retrieve a model instance of your model by looking into the `PCMResourceSetPartition`, where you registered your resource. If your model is not part of the standard PCM library, you might need to retrieve it in the following way:

```java
resourceSetPartition.getElement(<YOUR MODEL FILE CLASS>.eINSTANCE.get<MODEL FILE CLASS>()) // Returns a list of registered model files of that particular meta model
        .get(0); // If you are sure that there must be (at least) one, you can return the first one instead.
```

### Alternative way
Depending on your taste, you can also provide the model directly in your module without creating a provider class. In your module class, add the following method:

```java

@Provides
public UsageModel provideUsageModel(final Provider<PCMResourceSetPartition> resourceSetPartiton) {
    return resourceSetPartition.get().getUsageModel();
}

```

Guice will be able to pick up this method if you annotate it by `@Provides`.

## Further Reading
Especially for the model provider, since this is purely a Guice construction, you can make use of other Guice features here as well. For example, you can set that there is only one instance to be created by annotating the class or the provider method with `@Singleton`, or you can set that the instance can only be retrieved if the injectable parameter is annotated with a qualifier. Especially the latter is important if you want to provide multiple models of the same type (Guice cannot distinguish between `List<A>` and `List<B>` on runtime; it'll be always of type `List`). Read more on [Guice's Wiki page](https://github.com/google/guice/wiki).