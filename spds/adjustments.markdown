---
layout: page
title: Adjustments
parent: SPD Language
nav_order: 3
permalink: /adjustments/
---

# Adjustment Types

An *Adjustment Type* determines how the target group is adjusted. For example a [*Step Adjustment*](../docu/#adjustmentsStepAdjustment) denotes that the target group is adjusted by adding or removing a fixed amount of elements.

The following type of adjustments are available for use: 

| Name               | Description                                                                                                    | Supertype      |
|--------------------|----------------------------------------------------------------------------------------------------------------|----------------|
| [RelativeAdjustment](../docu/#adjustmentsRelativeAdjustment) | The RelativeAdjustment denotes that the group should is adjusted relatively to the current number of elements. | [AdjustmentType](../docu/#adjustmentsAdjustmentType) |
| [AbsoluteAdjustment](../docu/#adjustmentsAbsoluteAdjustment) | The AbsoluteAdjustment denotes that the group is adjusted to a goal value.                                     | [AdjustmentType](../docu/#adjustmentsAdjustmentType) |
| [StepAdjustment](../docu/#adjustmentsStepAdjustment)   | The StepAdjustment denotes that the group is adjusted by adding or removing a fixed amount of elements.        | [AdjustmentType](../docu/#adjustmentsAdjustmentType) |
