---
layout: page
title: Triggers
parent: SPD Language
nav_order: 3
permalink: /triggers/
---
# Triggers for Scaling

| Name                                                   | Description                                                                          | Supertype                                 |
|--------------------------------------------------------|--------------------------------------------------------------------------------------|-------------------------------------------|
| [CPUUtilizationTrigger](../docu/#triggersCPUUtilizationTrigger)                                  | A utilization based trigger based on the CPU resource.                               | [ProcessingResourceUtilizationBasedTrigger](../docu/#triggersProcessingResourceUtilizationBasedTrigger) |
| [HDDUtilizationTrigger](../docu/#triggersHDDUtilizationTrigger)                                  | A utilization based trigger based on the HDD resource.                               |  [ProcessingResourceUtilizationBasedTrigger](../docu/#triggersProcessingResourceUtilizationBasedTrigger)  |
| [RAMUtilizationTrigger](../docu/#triggersRAMUtilizationTrigger)                                | A utilization based trigger based on the RAM resource.                               |  [ProcessingResourceUtilizationBasedTrigger](../docu/#triggersProcessingResourceUtilizationBasedTrigger)  |
| [IdleTimeTrigger](../docu/#triggersIdleTimeTrigger) | IdleTimeTrigger bases the trigger on the idle time of a resource container.          | [TimeBasedTrigger](../docu/#triggersTimeBasedTrigger)                     |
| [ResponseTimeTrigger](../docu/#triggersResponseTimeTrigger)                              | A trigger based on the response time exceeding a reference threshold value.          |  [TimeBasedTrigger](../docu/#triggersTimeBasedTrigger)                                   |
| [PointInTimeTrigger](../docu/#triggersPointInTimeTrigger)                             | A trigger that is defined by the time on which a spd.TargetGroup should be adjusted. | [Scaling Trigger](../docu/#triggersScalingTrigger)                         |

You can now import Markdown table code directly using File/Paste table data... dialog. 