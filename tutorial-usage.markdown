---
layout: page
title: Usage Tutorial
permalink: /tutorial-usage/
nav_order: 50
---

# Usage Tutorial

This tutorial explains how to use the Slingshot Simulator. 
It focuses on a the perspective of the analyst.
If you are interested in contributing or extending Slingshot, go to the [Developer Tutorial](/tutorial-dev/).

This Tutorial assumes a basic understanding of Eclipse Modeling Tools and their Usage.

## Preparation

TODO : installation instructions, once an installable unit exist.

There is not yet a "ready-to-use" Slingshot Drop, the only option is to run Slingshot in an development environment. 
Please follow the [Developer Tutorial](/tutorial-dev/) to achieve this. 

## Create PCM Models

The Slingshot Simulator is an extension to the Palladio Approach.
Thus, at first, you need a basic understanding of Palladio. 

Follow the <a target="_blank" href="https://sdq.kastel.kit.edu/wiki/Palladio_Usecase_Tutorial">[↗ Palladio Tutorial]</a> to achieve this.
However, you need not read all steps.
Instead, read steps or skip them as listed in the following. 
Sadly, the tutorial is already outdated with regard to some details.
To avoid confusion, heed the warnings given below.  
- Follow step **1.** to **7.** to learn about the *Component Repository*, *System*, *Execution Environment*, *Component Allocation* and *Usage Model*. 
  * Beware of step **1.**, you already installed the Slingshot Simulator and need not install any additional Palladios.
  * Beware of step **3.**, substep **3.** and **4.** : the default names might differ from those given by the tutorial. 
  * Beware of step **3.**, substep **5.** : the instructions to create the operation signature are wrong. you write the operation signatures name, and fill parameters, parameter types, and return types in the respective columns.
  * Beware of step **3.**, substep **11.** : do not add the HDD Resource Demand, as the Slingshot Simulator is struggling with multiple Resource Demand inside one internal Action. 
  * Beware of step **4.**: the default names might differ from those given by the tutorial. 
  * Beware of step **5.**, substep **4.** : "A stochastic expression editor pops up". This might not happen. Instead, select processing resource type and scheduling policy, create the specification and afterwards edit the stochastic expression in the properties view (*StoexEdit*).
  * Beware of step **6.**, substep **3.** to **5.** : The assembly contexts might already be created. In this case, just drag-and-drop them into their respective resource container.
  * Beware of step **7.**, substep **2.** : the new usage model might not include a default usage scenario. In this case, you need to add it on your own. 
- Skip steps **8.** to **12.**
- Continue at step **13.** to learn about the *Monitor Repository* and *Measuring Points Repository Model*
  * Skip substep **10.**, we are not going to use experiment automation.
- Skip steps **14.** and **15.** 

## Run Slingshot Simulator without SPD

This sections explains how to run a simulation with the Slingshot Simulator.
It requires a set of PCM instances, as created in the previous section. 

This section is an edited copy of step **8. Performance Predictions** from the <a target="_blank" href="https://sdq.kastel.kit.edu/wiki/Palladio_Usecase_Tutorial">[↗ Palladio Tutorial]</a> tutorial.

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
You should be able to see one entry with measurements taken by the usage scenario response time monitor.
If the *Experiments* view is not visible, check your perspective or open the view manually.
<img src="../images/tutorial/palladio-tutorial-experiments.png" alt="palladio-tutorial-experiments"/>

For further explanations on result in general, go back to the <a target="_blank" href="https://sdq.kastel.kit.edu/wiki/Palladio_Usecase_Tutorial">[↗ Palladio Tutorial]</a> tutorial and continue step **8. Performance Predictions** at substep **8.**.

## Create Scaling Policies with SPD and semantic SPD

This section explains how to create instance of the SPD and semantic SPD models (TODO : check naming consistency).

At first, before adding elasticity, you must introduce a LoadBalancer into the architecture.
To achieve this, follow Step **9.** of the <a target="_blank" href="https://sdq.kastel.kit.edu/wiki/Palladio_Usecase_Tutorial">[↗ Palladio Tutorial]</a>.

### SPD 
For further information on SPD, confer (TODO : insert section link)
+ Create a new SPD model instance (*File* -> *New* -> *Other...* and filter for "spd")
  - Select *SPD* as *Model Object*
+ Use the tree editor to populate the model instance (If you don't know how to use the tree editor, read up on some Ecore / EMF basics)
  - Add an *Elastic Infrastructure* to the SPD instance to target a Resource Environment in the scaling rules (*rightclick on SPD node* -> *New Child -> Elastic Infrastructure*)
    - Add a reference to the resource environment model into the SPD instance (*rightclick* -> *Load Resource* or drag-and-drop)
    - In the properties view : Set the EI's resource environment 
  - Add a *Scaling Policy* to the SPD instance (*rightclick on SPD node* -> *New Child -> Scaling Policy*)
    - In the properties view : Set the policy's target group to newly added EI, and the policy to *active* (orange boxes)
      <img src="../images/tutorial/palladio-tutorial-spd-properties.png" alt="palladio-tutorial-spd" width="700px" />
  - Add more children to the policy (c.f. image below):
    - Add a *Step Adjustemnt* of 2 (green box). 
    - Add a *Simple Fire On Value* trigger (blue box), that awaits a *Simulation Time* stimulus (pink box) and triggers, if the *Expected Time* is equal to 5.0 seconds (purple box).
    - In the properties view of the trigger : Set the `Relational Operator` to `EqualTo` (orange box).
      <img src="../images/tutorial/palladio-tutorial-spd-trigger-properties.png" alt="palladio-tutorial-spd-trigger" width="700px" />


### Semantic SPD 
For further information on semantic SPD, confer (TODO : insert section link)
+ Create a new semantic SPD model instance (*File* -> *New* -> *Other...* and filter for "semanticspd")
  - Select *Configuration* as *Model Object*.
  - Add references to the repository, resource environment, spd and system model to the semantic mapping (*rightclick* -> *Load Resource* or drag-and-drop).
  - In the properties view of the configuration : Set the models (blue boxes in image below). 
    Leave the *Enacted Policy* (orange box in image below) empty. The enacted policy is set during runtime.
    The configuration defines the input to the QVTo transformation.
    <img src="../images/tutorial/spdsemantic-configuration.png" alt="spdsemantic-configuration" width="500px" />

+ Use the tree editor to populate the model instance (If you don't know how to use the tree editor, read up on some Ecore / EMF basics)
  - Add a child *Elastic Infrastructure Cfg* and set its properties as displayed here : 
    <img src="../images/tutorial/spdsemantic-configurationEI.png" alt="spdsemantic-configuration-ei" width="700px" />

  - Add a child *Service Group Cfg* and set its properties as displayed here : 
    <img src="../images/tutorial/spdsemantic-configurationSG.png" alt="spdsemantic-configuration-sg" width="700px" />


+ The resulting model for the semantic mapping should look similar to the image below.
<img src="../images/tutorial/palladio-tutorial-spdsemantic.png" alt="palladio-tutorial-spdsemantic" width="600px" />


## Run a Simulation with SPD and semantic SPD

Follow the Step-by-Step Explanation [Run Slingshot Simulator without SPD](Run Slingshot Simulator without SPD) until step **4.**.

* After step **4.**, still in the *Architecture Models* tab, select additional models from the workspace (orange boxes in image below):
  - *Scaling Policy Definition (Optional)* : the SPD model (`.spd`)
  - *SPD Semantic Configuration (Optional)* : the semantic mapping (`.semanticspd`)
* Continue with step **5.** in [Run Slingshot Simulator without SPD](Run Slingshot Simulator without SPD).
<img src="../images/tutorial/runSPD01.png" alt="runSPD01"/>

## Results 

* The model transformations happen in memory and are not stored back to the input models, i.e. the input models remain unchanged. 
* With the current usage scenario, the system is already overprovisioned, i.e. the scaling has no impact on the experiment results.
* However, if you set the *Output verboseness level* to *INFO* (open *Run Configuration* -> go to tab *Common*), the console logs the published events and other information.
If you find something similar to the following text block in the console log, the scaling was probably successful. 
Disclaimer : exact wording of logs is prone to change.
```
[Worker-18: Launching palladio-tutorial] INFO : Even dispatched at 5.0: ModelAdjustmentRequested(d7229048-aa61-43e3-832b-ea3e13e0eac8)
[Worker-18: Launching palladio-tutorial] INFO : Used SPD for transformation {name: aName}
[Worker-18: Launching palladio-tutorial] INFO : Used SPD for transformation {name: aName}
[Worker-18: Launching palladio-tutorial] INFO : Current number of containers 2
[Worker-18: Launching palladio-tutorial] INFO : lets create
[Worker-18: Launching palladio-tutorial] INFO : lets create
[Worker-18: Launching palladio-tutorial] INFO : no allocations for this assembly exist, lets create
[Worker-18: Launching palladio-tutorial] INFO : no allocations for this assembly exist, lets create
[Worker-18: Launching palladio-tutorial] INFO : operation required roles+needed:2
[Worker-18: Launching palladio-tutorial] INFO : operation required roles+needed:2
[Worker-18: Launching palladio-tutorial] INFO : Post interception result was successful: true
[Worker-18: Launching palladio-tutorial] INFO : Even dispatched at 5.0: ModelAdjusted(67588333-8590-410a-a343-0559e00cc42b)
``````
