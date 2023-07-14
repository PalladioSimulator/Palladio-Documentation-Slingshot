---
layout: page
title: Target Groups
parent: SPD Language
nav_order: 2
permalink: /targets/
---

# Target Groups

Target groups determine what is being affected by a defined policy. 
One can view the target group as a set of elements that is adjusted every time the policy is triggered.
As stated previously, the way how the target group is adjusted is determined by the defined adjustment type (see [[⇢ Adjustments]](../adjustments/) and when this is happening is determined by the defined trigger (see [[⇢ Triggers]](../triggers/)).

The following type of target groups are available for use: Elastic Infrastructure, Service Group, Competing Queue Consumers.

| Name                                                               | Description                                                                                                           | Supertype                                                               |
|--------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| [ElasticInfrastructure](../docu/#targetsElasticInfrastructure)     | The ElasticInfrastructure denotes that the target group is the set of all elements of the elastic infrastructure.     | [TargetGroup](../docu/#targetsTargetGroup)                              |
| [ServiceGroup](../docu/#targetsServiceGroup)                       | The ServiceGroup denotes that the target group is the set of all elements of a service group i.e., service instances. | [TargetGroup](../docu/#targetsTargetGroup)                              |
| [CompetingQueueConsumers](../docu/#targetsCompetingConsumersGroup) | The CompetingQueueConsumers denotes that the target group is the set of all elements of a competing queue consumers.  | [TargetGroup](../docu/#targetsTargetGroup)                              |

Since SPD relies on Palladio for simulating the behavior of the system under a policy the target groups map to structures in the Palladio model.
The mapping is configured through an auxiliary model that is defined in the [SPD Semantic] which also defines the semantic of the SPD language.

## Elastic Infrastructure

An Elastic Infrastructure target group gives end-users the opportunity to model policies at the infrastructure level. 
This allows the architect to express policies that are usually provided by the cloud provider (e.g., auto-scaling groups in AWS).

In Palladio, the Elastic Infrastructure target group maps to a subset of resource containers part of the `ResourceEnvironment` model element. 
For example, in the following figure the elastic infrastructure is the highlighted subset of resource containers. 
One can imagine, that the resource containers labelled with `...Node2` and `...Node3` were created after the policy got enacted.
![resource-env-elasticinfrastructure.png](../images/resource-env-elasticinfrastructure.png)

When the elastic infrastructure is adjusted, other Palladio models are adjusted as well to reflect the changes in the resource environment (i.e., to make use of the newly created resource containers).
The behavior is ultimately configured through the [SPD Semantic] auxiliary model, however, to the modeller creating the SPD it is transparent. 
They can add policies, adjust triggers, constraints and other elements without additional effort.

## Service Group

A Service Group target group gives end-users the opportunity to model policies at the service level. 
We define a service group in Palladio, as a set of assembly contexts that are load balanced by a load balancer assembly context.
For example, in the following figure the service group is the highlighted set of assembly contexts. The load balancer is highlighted inside the service group.
![service-group.png](../images/service-group.png)

Whenever an adjustment occurs, the service group is adjusted accordingly in the Palladio model. The following steps are performed: 
1. A new assembly context is created for each new service instance and the new assemblies are connected correctly to the load balancer and to downstream components.
2. The load balancer component is adjusted to distribute load to the new number of `AssemblyContexts`.
3. The new assembly contexts are placed on the right resource containers by modifying the `Allocation` model.

## Competing Queue Consumers

TBA