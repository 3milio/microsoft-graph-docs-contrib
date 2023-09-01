---
title: "hostPortComponent resource type"
description: "Represents a web component that is running on a specific hostPort"
author: "angelo-moulic"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: resourcePageType
---

# hostPortComponent resource type

Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a web component that is running on a specific **hostPort**

## Properties

| Property          | Type           | Description                                                                                                                                                                                                                                                                                                          |
| :---------------- | :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| firstSeenDateTime | DateTimeOffset | The first date and time when Microsoft Defender Threat Intelligence observed the **hostPortComponent**. The timestamp type represents date and time information using ISO 8601 format and is always in UTC. For example, midnight UTC on Jan 1, 2014, is 2014-01-01T00:00:00Z.                                       |
| isRecent          | Boolean        | Indicates whether this **hostPortComponent** is recent. It is recent if either it was seen at the same time or more recently than the latest **hostPortBanner** in the scan history or it was seen within two days of the latest scan of the **hostPort**, and there are no **hostPortBanners** in the scan history. |
| lastSeenDateTime  | DateTimeOffset | The last date and time when Microsoft Defender Threat Intelligence observed the **hostPortComponent**. The timestamp type represents date and time information using ISO 8601 format and is always in UTC. For example, midnight UTC on Jan 1, 2014, is 2014-01-01T00:00:00Z.                                        |

## Relationships

| Relationship | Type                                                                             | Description                                                       |
| :----------- | :------------------------------------------------------------------------------- | :---------------------------------------------------------------- |
| component    | [microsoft.graph.security.hostComponent](../resources/security-hostcomponent.md) | The **hostComponent** associated with this **hostPortComponent**. |

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.security.hostPortComponent"
}
-->

```json
{
  "@odata.type": "#microsoft.graph.security.hostPortComponent",
  "firstSeenDateTime": "String (timestamp)",
  "lastSeenDateTime": "String (timestamp)",
  "isRecent": "Boolean",
  "component": {
    "@odata.type": "microsoft.graph.security.hostComponent"
  }
}
```
