---
title: "virtualEvent resource type"
description: "Information about a virtual event."
author: "awang119"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
doc_type: resourcePageType
---

# virtualEvent resource type

Namespace: microsoft.graph

Represents a base virtual event. Base type of [virtualEventWebinar](virtualEventWebinar.md).

Inherits from [entity](../resources/entity.md).

> [!TIP]
> This is an abstract type and can't be used directly. Use the derived type [virtualEventWebinar](virtualEventWebinar.md) instead.

## Properties

|Property|Type|Description|
|:---|:---|:---|
|createdBy|[communicationsIdentitySet](communicationsidentityset.md)|Identity information of who created the virtual event. Inherited from [virtualEvent](../resources/virtualevent.md).|
|description|[itemBody](../resources//itembody.md)|Description of the virtual event.|
|displayName|String|Display name of the virtual event|
|endDateTime|[dateTimeTimeZone](../resources/datetimetimezone.md)|End time of the virtual event.|
|id|String|Unique identifier of the virtual event. Inherited from [entity](../resources/entity.md).|
|startDateTime|[dateTimeTimeZone](../resources/datetimetimezone.md)|Start time of the virtual event.|
|status|virtualEventStatus|Status of the virtual event. The possible values are: `draft`, `published`, `canceled`, `unknownFutureValue`.|

## Relationships

|Relationship|Type|Description|
|:---|:---|:---|
|sessions|[virtualEventSession](../resources/virtualeventsession.md) collection|Sessions of the virtual event.|

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.virtualEvent",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.virtualEvent",
  "id": "String (identifier)",
  "status": "String",
  "displayName": "String",
  "description": {
    "@odata.type": "microsoft.graph.itemBody"
  },
  "startDateTime": {
    "@odata.type": "microsoft.graph.dateTimeTimeZone"
  },
  "endDateTime": {
    "@odata.type": "microsoft.graph.dateTimeTimeZone"
  },
  "createdBy": {
    "@odata.type": "microsoft.graph.communicationsIdentitySet"
  }
}
```

