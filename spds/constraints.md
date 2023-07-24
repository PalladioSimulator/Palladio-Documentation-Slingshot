---
layout: page
title: Constraints
parent: SPD Language
nav_order: 3
permalink: /constraints/
---
# Constraints

In SPD constraints restrict and alter the final behaviour of a policy. Constraints aid the modeller in 
defining and analyzing policies that are more robust and less prone to oscillations.
There are two types of constraints: temporal constraints and state based constraints. Furthermore, some constraints 
are applicable for [ScalingPolicies](../docu/#spdScalingPolicy) and some for [TargetGroups](../docu/#targetsTargetGroup).

## Temporal Constraints
 
Temporal constraints are constraints in which the restriction and behavior alternation considers time as the main input source. 
Two temporal constraints, which are applicable to a policy, are the [Interval Constraint](../docu/#constraintspolicyIntervalConstraint) and the [Cooldown Constraint](../docu/#constraintspolicyCooldownConstraint).
One temporal constraint, that is applicable to the whole target group, is the [Thrashing Constraint](../docu/#constraintstargetThrashingConstraint).

### Cooldown Constraint

To exemplify the cooldown constraint, consider the image below which shows the behavior of a policy without a cooldown constraint.

![example-constraint.png](..%2Fimages%2Fconstraints%2Fexample-constraint.png)

The picture below depicts the behavior if a cooldown constraint is defined for a time period of 4 time units and with maximum scaling operation within that period of 0.
Once the policy is enacted once and an adjustment is made there is no further adjustment for the next 4 time units.
![example-cooldown-1.png](..%2Fimages%2Fconstraints%2Fexample-cooldown-1.png)

In case the max number of scaling operations is set to 1, after the first adjustment, there is one additional operation allowed within the cooldown period but no more than one.
![example-cooldown-2.png](..%2Fimages%2Fconstraints%2Fexample-cooldown-2.png)

Cooldown constraints are applicable to the policy and help to allow the system to stabilize after another adjustment is made so that the effects are better observable.

### Interval Constraint
An interval constraint is defined by a time offset and a time period in which the policy is switched to an inactive state.
For the same example, the picture below defines a time offset of 2 time units and a time period of 5 time units.
During the offset period, the policy is active and adjustments are made normally. 
After offset ends, the inactivity period as defined by the value of the interval parameter.

After the inactivity period ends and the simulation continues, then the interval constraint is applied again,
i.e., the policy is active again and adjustments are made within the offset. 

![example-interval.png](..%2Fimages%2Fconstraints%2Fexample-interval.png)

### Thrashing Constraint

Another temporal constraints that is applicable to the whole [TargetGroup](../docu/#targetsTargetGroup) and restricts the behavior of all the policies applying to it. 
The main objective behind the thrashing constraint is to avoid oscillations in the system. 
The thrashing constraint is defined by a minimum time period between two consecutive adjustments with opposite directions.
The motivation behind defining a thrashing constraint can be the stability of the system and the billing type of the cloud provider.
Often when resources are provisioned it does not make any sense to deprovision them after a short period of time while you are billed for the next 10 minutes. 
Hence, the modeller can specify a Thrashing constraint.

The picture below shows the behavior of a policy without a thrashing constraint in which a consecutive scale in is occurring after a scale out.
![constraint-thrashing.png](..%2Fimages%2Fconstraints%2Fconstraint-thrashing.png)

When adding a Thrashing constraint, the modeler can avoid such an oscillation. The picture below shows the behavior of the same policy with a thrashing constraint of 5 time units.
![constraint-thrashing-2.png](..%2Fimages%2Fconstraints%2Fconstraint-thrashing-2.png)


## State Based Constraints

State based constraints are constraints in which the restriction and behavior alternation considers the model state during the simulation.
At the moment there is only one state based constraint available, the [TargetGroup Size Constraint](../docu/#constraintstargetTargetGroupSizeConstraint).

### TargetGroup Size Constraint

The TargetGroup Size Constraint is a constraint that is applicable to the whole [TargetGroup](../docu/#targetsTargetGroup) and restricts the behavior of all the policies applying to it.
The constraint is defined by a minimum and maximum number of elements that the target group can have at any given time. 
All adjustments to a number of elements outside of the defined range are changed to either scaling to the minimum or the maximum.

![group-size-constraint.png](..%2Fimages%2Fconstraints%2Fgroup-size-constraint.png)
