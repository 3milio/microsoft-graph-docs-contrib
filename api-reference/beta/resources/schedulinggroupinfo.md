---
title: schedulingGroupInfo resource type
description: A description of the scheduling group.
author: shanemalone
ms.localizationpriority: high
ms.prod: microsoft-teams
doc_type: resourcePageType
---

# schedulingGroupInfo resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Information about the [schedulingGroup](schedulingGroup.md).

## Properties

| Property             | Type                          | Description            |
| -------------------- | ----------------------------- | ---------------------- |
| displayName          | `string`                      | The display name for the `schedulingGroup`. Required.      |
| schedulingGroupId    | `string`                      | ID of the `schedulingGroup`.  

## JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.schedulingGroupInfo"
}-->

```json
{
  "displayName": "String",
  "schedulingGroupId": "String"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->

<!--
{
  "type": "#page.annotation",
  "description": "schedulingGroupInfo resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
