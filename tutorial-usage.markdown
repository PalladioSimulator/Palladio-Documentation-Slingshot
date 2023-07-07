---
layout: page
title: Usage Tutorial
permalink: /tutorial-usage/
nav_order: 9001
---

# Usage Tutorial

This tutorial explains how to use the Slingshot Simulator. 
It focuses on a the perspective of the analyst.
If you are interested in contributing or extending Slingshot, go to the [Developer Tutorial](/tutorial-dev/).

This Tutorial assumes a basic understanding of Eclipse Modeling Tools and their Usage.

## Preparation

TODO : actual installation instructions.

There is not yet a "ready-to-use" Slingshot Drop, the only option is to run Slingshot in Developer mode. 
Please follow the [Developer Tutorial](/tutorial-dev/) to achieve this. 

## Create PCM Models

The Slingshot Simulator is an extension to the Palladio Approach.
Thus, at first, you need a basic understanding of Palladio. 

Follow the tutorial [Engineering a Web Application with Palladio (Version 2.0)](https://github.com/PalladioSimulator/Palladio-Addon-ArchitecturalTemplates/blob/master/misc/org.palladiosimulator.architecturaltemplates.doc/PalladioWorkshop.pdf) to achieve this.
Work through the tutorial like this:
- Skip step **1. Installation**. You already installed the Slingshot Simulator. 
- Follow step **2.** to **7.** to learn about the *Component Repository*, *System*, *Execution Environment*, *Component Allocation* and *Usage Model*. 
- Skip steps **8.** to **12.**
- Continue at step **13.** to learn about the *Monitor Repository* and *Measuring Points Repository Model*
- Skip steps **14.** and **15.** 

## Run Slingshot Simulator without SPD

This sections explains how to run a simulation with the Slingshot Simulator.
It requires a set of PCM instances, as created in the previous section. 

This section is an edited copy of **8. Performance Predictions** from the [Engineering a Web Application with Palladio (Version 2.0)](https://github.com/PalladioSimulator/Palladio-Addon-ArchitecturalTemplates/blob/master/misc/org.palladiosimulator.architecturaltemplates.doc/PalladioWorkshop.pdf) tutorial.

1. Open the *Run Configurations* dialog (*Run* -> *Run Configurations...*).
2. Doubleclick the *Slingshot Simulator* configuration category to create a new run configuration.
3. Name the configuration appropriately.
4. In the *Architecture Models* tab, select models from the workspace:
  - *Allocation Model* : an allocation model (`.allocation`)
  - *Usage Model* :  an usage model (`.usagemodel`) 
  - *Monitor Respository (Optional)* : a monitor repository model (`.monitorrepository`)
<img src="../images/tutorial/run01.png" alt="run01"/>

5. Switch to the  *Simulation* tab.
  - set the *Maximum Simulation time* to a value in seconds. 
  - select *Experiment Data Persistency & Presentation (EDP2)* as *Persistence Framework*
  - click *Browse...* to select a *LocalMemoryRepository* for storing our measurement results in main memory. 
    If none exists, add a new *In-Memory data source*.
<img src="../images/tutorial/run02.png" alt="run02"/>

6. Apply your changes and press the *Run* button.
The simulation may take a short while. You can follow the simulation status in the *Console* view.
7. After the simulation, go to the *Experiments* view. 
Expand your data source completely if not already expanded. 
You should be able to see different entries with measurements taken by different monitors.
If the *Experiments* view is not visible, check your perspective or open the view manually.
<img src="../images/tutorial/result01.png" alt="result01"/>

For further explanations on result, go back to the [Engineering a Web Application with Palladio (Version 2.0)](https://github.com/PalladioSimulator/Palladio-Addon-ArchitecturalTemplates/blob/master/misc/org.palladiosimulator.architecturaltemplates.doc/PalladioWorkshop.pdf) tutorial and continue **8. Performance Predictions** at step **8.**.

## Create Scaling Policies with SPD and semantic SPD

This section explains how to create instance of the SPD and semantic SPD models (TODO : check naming consistency).

### SPD 
For further information on SPD, confer (TODO : insert section link)
+ create a new SPD model instance (*File* -> *New* -> *Other...* and filter for "spd")
  - select *SPD* as *Model Object*
+ use the tree editor to populate the model instance
  - if you don't know how to do that, read up on some Ecore / EMF basics ;)

### Semantic SPD 
For further information on semantic SPD, confer (TODO : insert section link)
+ create a new semantic SPD model instance (*File* -> *New* -> *Other...* and filter for "semanticspd")
  - select *Configuration* as *Model Object*
+ use the tree editor to populate the model instance
  - if you don't know how to do that, read up on some Ecore / EMF basics ;)
+ leave the property *Enacted Policy* of *Configuration* empty. 
  This property is set to the selected policy during runtime. 

## Run a Simulation with SPD and semantic SPD

Follow the Step-by-Step Explanation [Run Slingshot Simulator without SPD](Run Slingshot Simulator without SPD) until step **4.**.

After step **4.**, still in the *Architecture Models* tab, select additional models from the workspace:
  - *Scaling Policy Definition (Optional)* : the SPD model (`.spd`)
  - *SPD Semantic Configuration (Optional)* : the semantic SPD model (`.semanticspd`)
<img src="../images/tutorial/runSPD01.png" alt="runSPD01"/>

Now, continue at step **5.** in [Run Slingshot Simulator without SPD](Run Slingshot Simulator without SPD).