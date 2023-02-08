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
| [CPUUtilizationTrigger](../docu/#deunistuttgartsqaslingshotspdtriggersCPUUtilizationTrigger)                                  | A utilization based trigger based on the CPU resource.                               | [ProcessingResourceUtilizationBasedTrigger](../docu/#deunistuttgartsqaslingshotspdtriggersProcessingResourceUtilizationBasedTrigger) |
| [HDDUtilizationTrigger](../docu/#deunistuttgartsqaslingshotspdtriggersHDDUtilizationTrigger)                                  | A utilization based trigger based on the HDD resource.                               |  [ProcessingResourceUtilizationBasedTrigger](../docu/#deunistuttgartsqaslingshotspdtriggersProcessingResourceUtilizationBasedTrigger)  |
| [RAMUtilizationTrigger](../docu/#deunistuttgartsqaslingshotspdtriggersRAMUtilizationTrigger)                                | A utilization based trigger based on the RAM resource.                               |  [ProcessingResourceUtilizationBasedTrigger](../docu/#deunistuttgartsqaslingshotspdtriggersProcessingResourceUtilizationBasedTrigger)  |
| [IdleTimeTrigger](../docu/#deunistuttgartsqaslingshotspdtriggersIdleTimeTrigger) | IdleTimeTrigger bases the trigger on the idle time of a resource container.          | [TimeBasedTrigger](../docu/#deunistuttgartsqaslingshotspdtriggersTimeBasedTrigger)                     |
| [ResponseTimeTrigger](../docu/#deunistuttgartsqaslingshotspdtriggersResponseTimeTrigger)                              | A trigger based on the response time exceeding a reference threshold value.          |  [TimeBasedTrigger](../docu/#deunistuttgartsqaslingshotspdtriggersTimeBasedTrigger)                                   |
| [PointInTimeTrigger](../docu/#deunistuttgartsqaslingshotspdtriggersPointInTimeTrigger)                             | A trigger that is defined by the time on which a spd.TargetGroup should be adjusted. | [Scaling Trigger](../docu/#deunistuttgartsqaslingshotspdtriggersScalingTrigger)                         |

You can now import Markdown table code directly using File/Paste table data... dialog. 