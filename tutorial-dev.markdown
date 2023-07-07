---
layout: page
title: Developer Tutorial
permalink: /tutorial-dev/
nav_order: 9002
---

# Developer Tutorial

This tutorial focuses on the developer perspective. 
It is of interest to you, if you want to extend or otherwise contribute to Slingshot.
The tutorial assumes basic knowledge about Eclipse and Palladio. 
The tutorial does neither detail how to install Eclipse / Palladio, nor how to import projects, nor how to handle Ecore/EMF or MDSE in general.  

The Slingshot Simulator is organized in multiple repositories.
The core of the simulator and each plugin has its own repository. 
Most repositories are part of the [Palladio Organisation](https://github.com/PalladioSimulator).

This tutorial explains which repos to clone and which plugins to import into an Eclipse Workspace to receive a basic Slingshot Simulator.
At the end of the Tutorial, we'll have an Eclipse Workspace to 
1. develop new Slingshot plugins or extend existing once.
2. start the Slingshot Simulator as an Eclipse Runtime Instance.

The last section provides some screenshots. 

## Preparation

To run a basic Slingshot Simulation with PCM instances only, you need the following repositories:

[Palladio-Analyzer-Slingshot](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot) :
* The Simulator core that glues all other plug-ins together. 

[Palladio-Analyzer-Slingshot-Extension-PCM-Core](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-PCM-Core):
* Plug-ins to interpret PCM instance.

[Palladio-Analyzer-Slingshot-Extension-Monitoring](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-Monitoring)
* Plug-ins to interpret *MonitorRepositories* and *MeasuringPoints*.


### Step-by-Step

1. Install *Palladio Bench* or *Eclipse Modelling Edition 2021-11*
  - [https://www.palladio-simulator.com/tools/download/](https://www.palladio-simulator.com/tools/download/)
    *!!* wont work because it's java 11 under the hood. 
  - [https://www.eclipse.org/downloads/](https://www.eclipse.org/downloads/)

2. clone essential Slingshot repositories from GitHub:
```
git clone https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot.git
git clone https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-Monitoring.git
git clone https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-PCM-Core.git
```

1. import [Palladio-Analyzer-Slingshot](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot)
  - also import nested projects. Otherwise, Eclipse cannot recognize the nested plug-in projects.  
  **either** : in the import dialogue, tick the checkbox *Search for nested projects* 
  **or** : after importing, right-click on the project and select *Configure* -> *Configure and Detect Nested Projects...* and tick the checkbox *Search for nested projects* in the dialogue.
  - a pop up may suggest to install maven extension. This is optional. Slingshot runs, even if you ignore the popup.
  - open the *Problems* view. You should see errors about unresolved bundles. Ignore these errors for now.

2. set the target platform
  - go to `releng/org.palladiosimulator.analyzer.slingshot.targetplatform/` and open `tp.target`
  - click *Set as active target platform* (to be found in the upper right corner, c.f. image at the end of this page).
  - the Target Platform is now loading. This may take some minutes.
  - once the target platform is set, all errors should be resolved.

2. import [Palladio-Analyzer-Slingshot-Extension-PCM-Core](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-PCM-Core)
  - pay attention to import nested projects as well.
  - ignore any Errors due to unresolved dependency on bundles in [Palladio-Analyzer-Slingshot-Extension-Monitoring](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-Monitoring). 

3. import [Palladio-Analyzer-Slingshot-Extension-Monitoring](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-Monitoring)
  - pay attention to import nested projects as well.
  - all errors should now be resolved.

### Hints 
In case you encounter Errors, especially after switching workspaces, (re-) importing or opening / closing projects, try any or all of the following options in different orders:
- close and reopen Eclipse
- refresh workspace / projects 
- Clean and Build 
- *Set as active Target Platform*, respectively *reload Target Platform*

If neither of these options helps, you must probably do some proper thinking.  

## Preparation for SPD

If you want to use the Scaling Policy Definition (SPD) Language (TODO : link to page within docu), you must import two more repositories:

[Palladio-Addons-SPD-Metamodel](https://github.com/PalladioSimulator/Palladio-Addons-SPD-Metamodel) : 
- meta-models to create SPD model instances and their semantics, as well as the QVTo transformations to reconfigure the simulated architecture.  
- *Hint* The transformations are QVTo. Depending on you Palladio / Eclipse `.qvto` are not yet supported. However, this does not hinder the execution of transformation by the simulator. 

[Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter) : 
- Slingshot Simulator Plug-In to interpret SPD instances, trigger reconfigurations and execute transformations. 

### Step-by-step

1. clone repositories
```
git clone https://github.com/PalladioSimulator/Palladio-Addons-SPD-Metamodel.git
git clone https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter.git
```

2. import [Palladio-Addons-SPD-Metamodel](https://github.com/PalladioSimulator/Palladio-Addons-SPD-Metamodel)
  - For those familiar with MDSE : the repository already contains the generated code, regeneration should not be required.  
3. import [Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter)
  - The interpreter depends on the meta model, i.e. if you switch the order of import you might witness unresolved dependencies. 
  - Depending on your Eclipse/Palladio, you may need to set your *Compiler compliance level* to >= 17.
  The Palladio Bench is still at Java 11, whereas the [Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter) is already at Java 17.





- (optional) get minimal example from GitHub:
  * [https://github.com/PalladioSimulator/Palladio-Documentation-Slingshot/tree/master/examples/minimalexample](https://github.com/PalladioSimulator/Palladio-Documentation-Slingshot/tree/master/examples/minimalexample)


## Start a Run Time Instance
start runtime eclipse from within workspace.
* e.g. via *Run* -> *Run As* -> *Eclipse Application*
* should not yield any popups with warnings. If it does, try to proceed. Maybe Slingshot runs anyway.

## Screenshots
### Workspace after importing Slingshot:
<img src="../images/tutorial/workspace.png" alt="workspace"/>

### Target Platform:
<img src="../images/tutorial/targetplatform.png" alt="targetplatform"/>

### Run Configurations Dialog:
<img src="../images/tutorial/runconfiguration.png" alt="runconfiguration"/>

### Run Configurations Dialog with missing fields, e.g because the PCM-Core extension is not in the workspace:
<img src="../images/tutorial/runconfiguration_missingFields.png" alt="runconfiguration—with—missing-fields"/>


