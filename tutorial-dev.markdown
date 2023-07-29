---
layout: page
title: Developer Tutorial
permalink: /tutorial-dev/
nav_order: 4
---

# Developer Tutorial

This tutorial focuses on the developer perspective. 
It explains how to set up the Slingshot Simulator in an development environment. 
Consult the section <a href="tutorial-dev">Slingshot Simulator</a> on technical details regarding the development of the Slingshot Simulator.
The tutorial assumes basic knowledge about Eclipse and Palladio. 
The tutorial does neither detail how to install Eclipse / Palladio, nor how to import projects, nor how to handle Ecore/EMF or MDSE in general.  

The Slingshot Simulator is organized in multiple repositories.
The core of the simulator and each plugin has its own repository. 
Most repositories are part of the [[↗ Palladio Organisation]](https://github.com/PalladioSimulator).

This tutorial explains which repos to clone and which plugins to import into an Eclipse Workspace to receive a basic Slingshot Simulator.
At the end of the Tutorial, we will have an Eclipse Workspace to 
* Develop new Slingshot plugins or extend existing once.
* Start the Slingshot Simulator as an Eclipse Runtime Instance.

The last section provides some screenshots. 

## Preparation

To run a basic Slingshot Simulation with PCM instances only, you need the following repositories:

[[↗ Palladio-Analyzer-Slingshot]](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot) :
* The Simulator core that glues all other plug-ins together. 

[[↗ Palladio-Analyzer-Slingshot-Extension-PCM-Core]](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-PCM-Core):
* Plugins to interpret PCM instance.

[[↗ Palladio-Analyzer-Slingshot-Extension-Monitoring]](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-Monitoring)
* Plugins to interpret *MonitorRepositories* and *MeasuringPoints*.


### Step-by-Step

* Install *Palladio Bench* or *Eclipse Modelling Edition 2021-11*
  - <a target="_blank" href="https://www.palladio-simulator.com/tools/download/">[↗ Palladio]</a>
  - <a target="_blank" href="https://www.eclipse.org/downloads/">[↗ Eclipse]</a>

* Clone essential Slingshot repositories from GitHub:
```
git clone https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot.git
git clone https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-Monitoring.git
git clone https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-PCM-Core.git
```

* Import <a target="_blank" href="https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot"> Palladio-Analyzer-Slingshot</a>
  - Also import nested projects. Otherwise, Eclipse cannot recognize the nested plugin projects.  
    * *Either* : in the import dialogue, tick the checkbox *Search for nested projects* 
    * *Or* : after importing, right-click on the project and select *Configure* -> *Configure and Detect Nested Projects...* and tick the checkbox *Search for nested projects* in the dialogue.
  - A pop up may suggest to install maven extension. This is optional. Slingshot runs, even if you ignore the popup.
  - Open the *Problems* view. You should see errors about unresolved bundles. Ignore these errors for now.

* Set the target platform
  - Go to `releng/org.palladiosimulator.analyzer.slingshot.targetplatform/` and open `tp.target`
  - Click *Set as active target platform* (to be found in the upper right corner, c.f. image at the end of this page).
  - The Target Platform is now loading. This may take some minutes.
  - Once the target platform is set, all errors should be resolved.

* Import <a target="_blank" href="https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-PCM-Core"> Palladio-Analyzer-Slingshot-Extension-PCM-Core</a>
  - Pay attention to import nested projects as well.
  - Ignore any Errors due to unresolved dependency on bundles in Palladio-Analyzer-Slingshot-Extension-Monitoring.

* Import <a target="_blank" href="https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-Monitoring"> Palladio-Analyzer-Slingshot-Extension-Monitoring</a>
  - Pay attention to import nested projects as well.
  - All errors should now be resolved.

### Hints 
In case you encounter Errors, especially after switching workspaces, (re-) importing or opening / closing projects, try any or all of the following options in different orders:
- Close and reopen Eclipse / Palladio.
- Refresh workspace / projects. 
- Clean and Build 
- *Set as active Target Platform*, respectively *Reload Target Platform*

If neither of these options helps, you must probably do some proper thinking.  

## Preparation for SPD

If you want to use the Scaling Policy Definition (SPD) Language (TODO : link to page within docu), you must import two more repositories:

<a target="_blank" href="https://github.com/PalladioSimulator/Palladio-Addons-SPD-Metamodel">[↗ Palladio-Addons-SPD-Metamodel]</a>
- Meta-models to create SPD model instances and their semantics, as well as the QVTo transformations to reconfigure the simulated architecture.  
- *Hint* : The transformations are QVTo. Depending on your Palladio / Eclipse `.qvto` files are not supported. However, this does not hinder the execution of transformation by the simulator. 

<a target="_blank" href="https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter">[↗ Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter]</a>
- Slingshot Simulator plugin to interpret SPD instances, trigger reconfigurations and execute transformations. 

### Step-by-step

* Clone repositories
```
git clone https://github.com/PalladioSimulator/Palladio-Addons-SPD-Metamodel.git
git clone https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter.git
```

* Import [Palladio-Addons-SPD-Metamodel](https://github.com/PalladioSimulator/Palladio-Addons-SPD-Metamodel)
  - For those familiar with MDSE : the repository already contains the generated code, regeneration should not be required.  
* Import [Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter)
  - The interpreter depends on the meta model, i.e. if you switch the order of import you might witness unresolved dependencies. 
  - Depending on your Eclipse/Palladio, you may need to set your *Compiler compliance level* to >= 17.
  The Palladio Bench is still at Java 11, whereas the [Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter) is already at Java 17.

## Start a Run Time Instance
Start a runtime eclipse from within workspace, e.g. via *Run* -> *Run As* -> *Eclipse Application*
This should not yield any popups with warnings. If it does, try to proceed. Sometimes Slingshot runs anyway.

## Screenshots
### Workspace after importing Slingshot:
<img src="../images/tutorial/workspace.png" alt="workspace"/>

### Target Platform:
<img src="../images/tutorial/targetplatform.png" alt="targetplatform"/>

### Run Configurations Dialog:
<img src="../images/tutorial/runconfiguration.png" alt="runconfiguration"/>

### Run Configurations Dialog with missing fields, e.g because the PCM-Core extension is not in the workspace:
<img src="../images/tutorial/runconfiguration_missingFields.png" alt="runconfiguration—with—missing-fields"/>


