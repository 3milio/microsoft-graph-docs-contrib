---
title: "virtualEvent resource type"
description: "Represents an abstract base type for a virtual event. "
author: "awang119"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
doc_type: resourcePageType
---

# virtualEvent resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents an abstract base type for a virtual event. 

Base type of [virtualEventTownhall](virtualeventtownhall.md) and [virtualEventWebinar](virtualeventwebinar.md).

Inherits from [entity](../resources/entity.md).

> [!TIP]
> This is an abstract type and can't be used directly. Use the derived types [virtualEventTownhall](virtualeventtownhall.md) or [virtualEventWebinar](virtualeventwebinar.md) instead.

## Properties

|Property|Type|Description|
|:---|:---|:---|
|createdBy|[communicationsIdentitySet](communicationsidentityset.md)|Identity information for the creator of the virtual event. Inherited from [virtualEvent](../resources/virtualevent.md).|
|description|[itemBody](../resources/itembody.md)|Description of the virtual event.|
|displayName|String|Display name of the virtual event. |
|endDateTime|[dateTimeTimeZone](../resources/datetimetimezone.md)|End time of the virtual event. The **timeZone** property _can_ be set to any of the [time zones currently supported by Windows](/windows-hardware/manufacture/desktop/default-time-zones).|
|id|String|Unique identifier of the virtual event. Inherited from [entity](../resources/entity.md).|
|startDateTime|[dateTimeTimeZone](../resources/datetimetimezone.md)|Start time of the virtual event. The **timeZone** property _can_ be set to any of the [time zones currently supported by Windows](/windows-hardware/manufacture/desktop/default-time-zones).|
|status|virtualEventStatus|Status of the virtual event. The possible values are: `draft`, `published`, `canceled`, `unknownFutureValue`.|

## Relationships

|Relationship|Type|Description|
|:---|:---|:---|
|presenters|[virtualEventPresenter](../resources/virtualeventpresenter.md) collection|The virtual event presenters.|
|sessions|[virtualEventSession](../resources/virtualeventsession.md) collection|Sessions for the virtual event.|

## JSON representation

The following JSON representation shows the resource type
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
  "createdBy": {
    "@odata.type": "microsoft.graph.communicationsIdentitySet"
  },
  "description": {
    "@odata.type": "microsoft.graph.itemBody"
  },
  "displayName": "String",
  "endDateTime": {
    "@odata.type": "microsoft.graph.dateTimeTimeZone"
  },
  "id": "String (identifier)",
  "startDateTime": {
    "@odata.type": "microsoft.graph.dateTimeTimeZone"
  },
  "status": "String"
}
```
