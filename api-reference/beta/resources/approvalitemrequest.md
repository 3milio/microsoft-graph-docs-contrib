---
title: "approvalItemRequest resource type"
description: "Collections of requests created for each approver on the approval item."
author: "asgautam1997"
ms.localizationpriority: medium
ms.subservice: "approvals"
doc_type: resourcePageType
---

# approvalItemRequest resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Collections of requests created for each approver on the approval item.

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List](../api/approvalitem-list-requests.md)|[approvalItemRequest](../resources/approvalitemrequest.md) collection|Get a list of the [approvalItemRequest](../resources/approvalitemrequest.md) objects and their properties.|
|[Get](../api/approvalitemrequest-get.md)|[approvalItemRequest](../resources/approvalitemrequest.md)|Read the properties and relationships of an [approvalItemRequest](../resources/approvalitemrequest.md) object.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|approver|[approvalIdentitySet](../resources/approvalidentityset.md)|The identity set of the principal assigned to this request.|
|createdDateTime|DateTimeOffset|The date and time at which the request was created.|
|isReassigned|Boolean|A flag used for identifying if a request was reassigned.|
|reassignedFrom|[approvalIdentitySet](../resources/approvalidentityset.md)|The identity set of the principal who reassigned the request.|

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.approvalItemRequest",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.approvalItemRequest",
  "createdDateTime": "String (timestamp)",
  "approver": {
    "@odata.type": "microsoft.graph.approvalIdentitySet"
  },
  "reassignedFrom": {
    "@odata.type": "microsoft.graph.approvalIdentitySet"
  },
  "isReassigned": "Boolean"
}
```

