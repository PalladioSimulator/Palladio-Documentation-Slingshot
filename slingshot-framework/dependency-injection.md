---
layout: page
parent: Slingshot Framework
title: Dependency Injection Mechanism in Slingshot
permalink: /slingshot-framework/dependency-injection/
nav_order: 1
---
# Dependency Injection Mechanism in Slingshot
To further loosen the coupling between the extensions and the (core) framework, and therefore improve extensibility, we use [Guice](https://github.com/google/guice), which is a
dependency injection library. 

Every application that uses Guice has a **main injector** that holds a *dependency graph*. Typically, a graph looks like this: 

<img src="../../images/dependencygraph.svg">

The graph is automatically created by [Grapher](https://github.com/google/guice/wiki/Grapher), where

* **Solid Edges**: represents dependencies from implementations to the types they depend on.
* **Dashed edges**: represents bindings from types to their implementation.
* **Double arrows**: indicate that the binding or dependency is to a *Provider*.

When injecting, the Injector will search in the graph for a concrete implementation / instance and inject that to the constructor. 

Generally speaking, within the framework there is a (parent) Injector that is instantiated as follows:

```java
injector = Guice.createInjector(modules);
```

Here, `modules` is a list/collection of modules that should be considered within Guice. More specifically, a module is an implementation of Guice's `Module` interface, or rather a subclass of `AbstractModule`. In Slingshot's case, each extension is already a Guice module (`AbstractSlingshotExtension` inherits from `AbstractModule`). Within that module, one specifies all the bindings this module provides. The bindings are explained in [Extensions](../extensions/) section.

## Eclipse Workflow / Jobs
As mentioned, there are two phases within the framework: The **configuration / system phase** and **simulation phase**. The system phase is started the first time when Slingshot is needed within the Eclipse instance (in this case, when the launch configuration has started). In Eclipse, when a plugin is needed, an *Activator* class of that plugin will be instantiated. In this case, the framework's *Slingshot* will be created. Afterwards, the module of Slingshot (*SlingshotModule*) will create the parent injector in which case all the extensions of any type will be imported, as well as the *SlingshotSystem* module:

<img src="../../images/DI.svg">

Slingshot is based on [Palladio's Job Workflow Engine](https://sdq.kastel.kit.edu/wiki/Palladio_Workflow_Engine). When hitting the *Launch* button, the UI module will call the *SimulationLauncher* which will in turn create a *SimulationRootJob*. The root job is a *CompositeJob* consisting of multiple sub jobs in the following order:

1. `PreparePCMBlackboardPartitionJob`: This will initialize the *blackboard* of the composite job that will contain all the data shared between the sub jobs.
2. `LoadModelIntoBlackboardJob`: For every specified model in the launcher tab, the URI is loaded and parsed into the blackboard.
3. `SimulationJob`: Slingshot's custom job: It initializes the driver and starts the simulation.

Once the SimulationJob starts, we initialize the SimulationDriver, which in turn creates a **child injector** including all the extension *behaviors*. This step is needed because it is not possible to add new modules in an existing injector.

<img src="../../images/childinjector.svg">

The child injector inherits the dependency graph from the parent injector, but it adds further modules to it which are invisible to the parent.