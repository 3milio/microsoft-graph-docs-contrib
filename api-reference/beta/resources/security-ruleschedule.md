---
title: "ruleSchedule resource type"
description: "Describes how often the custom detection rule runs, and when it next runs."
author: "mmekler"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: resourcePageType
---

# ruleSchedule resource type

Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

 Describes how often the [Custom Detection Rule](../resources/security-detectionrule.md) runs, and when it next runs.

## Properties
| Property        | Type           | Description                                                                                                                                       |
|:----------------|:---------------|:--------------------------------------------------------------------------------------------------------------------------------------------------|
| nextRunDateTime | DateTimeOffset | Timestamp of the custom detection rule's next scheduled run.                                                                                      |
| period          | String         | How often the detection rule is set to run. The allowed values are: `0`, `1H`, `3H`, `12H`, or `24H`. "0" signifies the rule is run continuously. |

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.security.ruleSchedule"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.security.ruleSchedule",
  "period": "String",
  "nextRunDateTime": "String (timestamp)"
}
```

