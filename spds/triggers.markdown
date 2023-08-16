---
layout: page
title: Triggers
parent: SPD Language
nav_order: 3
permalink: /triggers/
---
# Triggers for Scaling

A ScalingTrigger in SPD defines an abstract construct that determines 'when to scale' and 'based on what'. To create more complex 
triggering conditions, SPD offers the ComposedTrigger that connects multiple triggers with logical operators.  

One abstract refinement for a scaling trigger is the BaseTrigger. A BaseTrigger is a containment of a Stimulus and Expectation. 
The Stimulus defines the 'based on what' part of the trigger and the Expectation defines the 'when to scale' part of the trigger.
Concrete refinements of the BaseTrigger define how the Stimulus and Expectation are evaluated. For example, the SimpleFireOnValue 
is the most basic trigger that fires when the stimulus and the expectation are compared with a relational operator.
The SimpleFireOnValue allows to define elasticity policies of type threshold-based which are quite common in the cloud.

The following figure shows the class diagram of the trigger hierarchy.

![mermaid-triggers.png](../images/mermaid-triggers.png)

## Common Stimulus and Expectations: Examples for SimpleFireOnValue

The Stimulus defines observable information during the simulation of an architectural model upon which a trigger can fire. 
There exist a variety of stimuli that can be used to define triggers. 

[//]: # (Please check the [Stimuli]&#40;../docu/#triggersStimulus&#41; section for more information.)
Here we cover a set of common stimuli that are used in the context of elasticity and a set of common expectations that are used to define policies that use 
the SimpleFireOnValue trigger.

### SimulationTime (SimulationStateStimulus)

With the SimulationTime stimulus, the modeller can define a trigger that fires based on the simulation time. For example, one can define scenarios
where the system scales out after 20 seconds of simulation time. 

<details>
  <summary>Example</summary>
<br>
An example with a SimpleFireOnValue trigger that fires when the simulation time is above 20 seconds.
<hr>
<img src="../images/simulation-time.png" alt="Simulation Time Trigger"/>
<br>
</details>

### OperationResponseTime (SourceInterfaceStimulus)

The OperationResponseTime is an example of a stimulus obtained from the SourceInterface of the target group. 
This particular stimulus is based on the response time of an operation. For example, one can define a trigger that fires when the response time of an operation is 
above 200ms.

<details>
  <summary>Example</summary>
<br>
An example with a SimpleFireOnValue trigger that fires when the response time of a particular operation (e.g., 'getItems') is above 200ms.
<hr>
<img src="../images/operation-response-time.png" alt="Operation Response Time Trigger"/>
<br>
</details>


### CPUUtilization (ResourceUtilizationState ➝ ManagedElementsStateStimulus ➝ TargetGroupStateStimulus)

The CPUUtilization is an example of a stimulus obtained from the ResourceUtilizationState of the target group. The ManagedElementsState requires 
from the modeller to specify a statistical aggregation across the managed elements (e.g., Max, Average, Min). For example, in the case of the CPUUtilization,
this means that the reported CPU utilization of each managed element is aggregated to a single value. 

<details>
  <summary>Example</summary>
<br>
  Scale out when average CPU utilization across managed elements is above 80%.
<hr>
<img src="../images/cpu-util.png" alt="CPU Utilization Trigger"/>
<br>
</details>


### NumberOfElements (TargetGroupStateStimulus)

The NumberOfElements is a simple stimulus that yields information from the target group state, in particular the number of elements in the target group.
For example, one can define a trigger that fires when the number of elements in the target group is above 10. This can be used to create policies that
are scale dependent. For example, one can define a policy that scales the application with a lower factor when the number of elements exceeds a certain number of elements.


<details>
  <summary>Example</summary>
<br> 
  A composed trigger that uses the number of elements stimulus as a guard for changing the scaling policy, i.e., when number of elements is above 10, the policy 
    fires when the cpu utilization is above 80%. 
<hr>
<img src="../images/number-of-elements.png" alt="Number of Elements Trigger"/>
<br>
</details>