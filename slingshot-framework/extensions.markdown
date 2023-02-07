---
layout: page
parent: Slingshot Framework
title: Making Extensions
permalink: /slingshot-framework/extensions/
nav_order: 4
---
# Making extensions and adding behavior
The slingshot framework is based on the event-driven architecture. Almost all extensions are made by *listening to* and *publishing* events. This is done by utilizing the event driver.

An extension itself is defined by creating a new **Guice**-module. In particular, the extension needs to define a class that inherits from `AbstractSlingshotModule`, which in turn extends from `AbstractModule`. There, you "install" simulation and system behaviors (i.e. listeners and event providers to SimulationDriver and SystemDriver respectively).

Example: Let's assume you have made an extension to the SimulationDriver and provided subscribers to its events in the `SimulationBehavior` class. Furthermore, let's assume you defined it in a plugin called "Extension". Then you need to create the following class:

```java
public class Extension extends AbstractSlingshotModule {

    @Override
    public void configure() {
        install(SimulationBehavior.class); // <-- Registers the subscribers here
        // Further behavior classes
    }

}
```

After that, you register this class in the Eclipse's extension registry, that is, in the `plugin.xml` the following should be contained:

```xml
<extension point="org.palladiosimulator.analyzer.slingshot">
      <slingshot-extension
            module="org.palladiosimulator.analyzer.slingshot.extension.Extension"></slingshot-extension>
      <!-- Further extensions -->
</extension>
```

As you can see, you can actually define multiple slingshot extensions in the same plugin.

## Simulation Behavior extensions (to the SimulationDriver)
In order for the simulation driver to pick up the extension, your class that defines the subscriber handlers needs to implement the `SimulationBehaviorExtension` interface. This is just a super type and does not define any methods you need to implement. Generally, you should keep subscribers that handle system events and subscribers that handle simulation events apart from each other (see below).

```java
@OnEvent(...)
public class SimulationBehavior implements SimulationBehaviorExtension {

}
```

## System Behavior extensions (to the SystemDriver)
In this case, your class of subscribers should implement the `SystemBehaviorExtension`.

## Model Contribution
See more at [UI and Workflow](/slingshot-framework/system-driver/ui/)