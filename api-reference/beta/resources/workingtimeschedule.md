---
title: "workingTimeSchedule resource type"
description: "Represents user's working time schedule entity."
author: "galalalym"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: resourcePageType
---

# workingTimeSchedule resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents user's working time schedule entity.

## Methods

|Method|Return type|Description|
|:---|:---|:---|
|[Get workingTimeSchedule](../api/workingtimeschedule-get.md)|[workingTimeSchedule](../resources/workingtimeschedule.md)|Read the properties and relationships of a [workingTimeSchedule](../resources/workingtimeschedule.md) object.|
|[startWorkingTime](../api/workingtimeschedule-startworkingtime.md)|None|Trigger the policies associated with the start of working hours for a specific user.|
|[endWorkingTime](../api/workingtimeschedule-endworkingtime.md)|None|Trigger the policies associated with the end of working hours for a specific user.|

## Properties

|Property|Type|Description|
|:---|:---|:---|
|id|String|A unique programmatic identifier for the entity. Read-only.|

## Relationships

None.

## JSON representation

The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.workingTimeSchedule",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.workingTimeSchedule",
  "id": "String (identifier)"
}
```
