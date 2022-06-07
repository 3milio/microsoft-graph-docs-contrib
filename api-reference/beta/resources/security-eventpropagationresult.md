---
title: "eventPropagationResult resource type"
description: "Retrieve the status of an event and additional information about location and workload."
author: "sseth"
ms.localizationpriority: medium
ms.prod: "compliance"
doc_type: resourcePageType
---

# eventPropagationResult resource type

Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve the status of an event and additional information about location and workload.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|location|String|Location in the workload.|
|status|retentionEventStatusType|Is the event completed. The possible values are: `none`, `inProcessing`, `failed`, `success`.|
|statusInformation|String|Additional infroamtion about the status.|
|workload|String|Workload being targetted by the event.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.security.eventPropagationResult"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.security.eventPropagationResult",
  "workload": "String",
  "location": "String",
  "status": "String",
  "statusInformation": "String"
}
```


