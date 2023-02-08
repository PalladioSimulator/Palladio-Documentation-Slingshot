---
layout: page
title: Core concepts
parent: SPD Language
nav_order: 1
permalink: /overview/
---
# Scaling Policy Definition

# Scaling Policy
<img src="../images/icons/scalingpolicy.png" alt="slingshot-scaling-policy"/>

A [*Scaling Policy*](../docu/#deunistuttgartsqaslingshotspdScalingPolicy) determines the complete information for scaling a parituclar target. It is a containment of a [*trigger*](../docu/#deunistuttgartsqaslingshotspdtriggersScalingTrigger) and an [*adjustment type*](../docu/#deunistuttgartsqaslingshotspdadjustmentsAdjustmentType) and a finite number of [*constraints*](../docu/#deunistuttgartsqaslingshotspdconstraints). It references a [*target group*](../docu/#deunistuttgartsqaslingshotspdtargetsTargetGroup) which is adjusted when the trigger fires.

## Trigger
<img src="../images/icons/scalingtrigger_placeholder.png" alt="slingshot-scaling-trigger"/>

A [*Scaling Trigger*](../docu/#deunistuttgartsqaslingshotspdtriggersScalingTrigger) encapsulates both what is observed on the modeled system (the monitoring) as well as how such observation lead to a trigger (the analysis part). 

## Constraints
<img src="../images/icons/constraint_placeholder.png" alt="slingshot-scaling-trigger"/>

[*Constraints*](../docu/#deunistuttgartsqaslingshotspdconstraintsAbstractConstraint) represents ways to constraint the scaling behavior. A typical example would be to constrain the number of adaptations for a time interval. In the SPD language we distinguish between two different types of constraints: constraints that are applicable to the policy, and, constraints that are applicable to the target group. An example for the later would be the maximum number of elements in the group (e.g., maximum number of Pods per Deployment in Kubernetes).

### Policy Constraints
### Target Constraints


## Adjustment type
<img src="../images/icons/adjustmenttype_placeholder.png" alt="slingshot-scaling-trigger"/>

An *Adjustment Type* determines how the target group is adjusted. For example a [*Step Adjustment*](../docu/#deunistuttgartsqaslingshotspdadjustmentsStepAdjustment) denotes that the target group is adjusted by adding or removing a fixed amount of elements.

# Target Groups

Policies apply to target groups. A *Target Group* defines a structure of elements on which adjustments are precisely defined. We distingiush three different such structures: *Elastic Infrastructure*, *Elastic Service*, *Elastic Queue Consumers*. The first and the later two are **antinomical** meaning that in one *SPD* definition either polcies are defined on the infrastructure level or service level. For the service-level groups we distinguish two types of groups depending on the communication style employed in the architecture: synchronous (*Elastic Service*) vs asynchronous (*Elastic Queue Consumers*).

When policies are defined on the service-level, the infrastructure is adjusted automatically to meet the demands of the scaled services.

## Elastic Infrastructure
<img src="../images/icons/target_group.png" alt="slingshot-target-group"/>

## Elastic Service 
<img src="../images/icons/target_group_service.png" alt="slingshot-target-group"/>

## Elastic Queue Consumers

TBA