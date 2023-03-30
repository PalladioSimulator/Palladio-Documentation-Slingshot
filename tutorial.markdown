---
layout: page
title: Tutorial
permalink: /tutorial/
---

# Tutorial

This tutorial explains how to import and run Slingshot. 
The tutorial assumes, that the reader already has some basic knowledge about Eclipse and Palladio. 
The tutorial does not explain how to install Eclipse, nor how to import projects in detail.  

The last section provides some screenshots. 

## Preparation

- install Eclipse Modeling Edition
  - for this tutorial, i used 2021-12
- it's also possible to use a Palladio Bench instead of an Eclipse Modeling Edition. 
- clone Slingshot repositories from GitHub:
  * [https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot)
  * [https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-PCM-Core](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-PCM-Core)
  * [https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-Monitoring](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-Monitoring)
  * (optional) [https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter](https://github.com/PalladioSimulator/Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter)
  * (otional) [https://github.com/PalladioSimulator/Palladio-Addons-SPD-Metamodel](https://github.com/PalladioSimulator/Palladio-Addons-SPD-Metamodel)

- (optional) get minimal example from GitHub:
  * [https://github.com/PalladioSimulator/Palladio-Documentation-Slingshot/tree/master/examples/minimalexample](https://github.com/PalladioSimulator/Palladio-Documentation-Slingshot/tree/master/examples/minimalexample)

## Import 

* import `Palladio-Analyzer-Slingshot`
  - pay attention to import nested projects as well.
  - a pop up may suggest to install maven extension. This is optional. Slingshot runs, even if you ignore the popup.
  - open the *Problems* view. You should see some errors about bundles that cannot be resolved. Ignore these errors for now.

* set the target platform
  - go to `releng/org.palladiosimulator.analyzer.slingshot.targetplatform/` and open `tp.target`
  - click *Set as active target platform* (to be found in the upper right corner).
  - eclipse is now loading the target platform. This may take some minutes.
  - once the target platform is set, all errors should be resolved.

* import `Palladio-Analyzer-Slingshot-Extension-PCM-Core`
  - pay attention to import nested projects as well.
  - ignore any Errors due to unresolved dependency on bundles in monitoring. 

* import `Palladio-Analyzer-Slingshot-Extension-Monitoring`
  - pay attention to import nested projects as well.
  - all errors should now be gone.

* (optional) import `Palladio-Addons-SPD-Metamodel`
  - provides the meta model for the SPD Language
  - required, if you want to Slingshot's SPD-Interpreter extension (c.f. next bullet point) 

* (optional) import `Palladio-Analyzer-Slingshot-Extension-SPD-Interpreter`
  - requires `Palladio-Addons-SPD-Metamodel` to be imported
  - TODO

### Hints 
In case you encounter Errors, especially after switching workspaces, or closing and reopening Eclipse, try one or all of these things in different orders:
- refresh workspace
- *Set as active Target Platform*, respective *reload Target Platform* 
- Clean and Build 

If neither of these options helps, you should probably start thinking. 

## Usage
*prerequisite* : all desired extensions are imported into eclipse workspace. 
- start runtime eclipse from within workspace.
  * e.g. via *Run* -> *Run As* -> *Eclipse Application*
  * should not yield any popups with warnings. If it does, try to proceed. Maybe Slingshot runs anyway.
- open Palladio perspective.
- get a model to simulate.
  * *either* : create a new model.
  * *or* : import an existing modelling project, e.g. the `minimalexample` listed above.
- open the *Run Configurations* Dialog.
- scroll down to *Slingshot Simlation* and create a new configuration.
- select models in the *Architectural Models* Tab (similar to 'normal' Palladio) 
  - if the *Architectural Models* tab does not show any fields, check whether `Palladio-Analyzer-Slingshot-Extension-PCM-Core` is correctly imported.
- select Data Set and Stop Conditions in the *Simulation* Tab (identical to 'normal' Palladio)
- apply and run the simulation.
- check experiment results. 


## Screenshots
### Workspace after importing Slingshot:
<img src="../images/tutorial/workspace.png" alt="workspace"/>

### Target Platform:
<img src="../images/tutorial/targetplatform.png" alt="targetplatform"/>

### Run Configurations Dialog:
<img src="../images/tutorial/runconfiguration.png" alt="runconfiguration"/>

### Run Configurations Dialog with missing fields, e.g because the PCM-Core extension is not in the workspace:
<img src="../images/tutorial/runconfiguration_missingFields.png" alt="runconfiguration—with—missing-fields"/>


