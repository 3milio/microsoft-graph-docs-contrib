---
title: "plannerBaseApprovalAttachment resource type"
description: "The **plannerBaseApprovalAttachment** resource represents the base approval attachment that will be added to a [plannerTask](plannertask.md), which contains the common properties that are required for an approval. 
While the derived types, such as [plannerBasicApprovalAttachment](plannerbasicapprovalattachment.md), have details corresponding to the type of approval."
author: "ShravanthiReddy"
ms.localizationpriority: medium
ms.prod: "planner"
doc_type: resourcePageType
---

# plannerBaseApprovalAttachment resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The **plannerBaseApprovalAttachment** resource represents the base approval attachment that will be added to a [plannerTask](plannertask.md), which contains the common properties that are required for an approval. 
While the derived types, such as [plannerBasicApprovalAttachment](plannerbasicapprovalattachment.md), have details corresponding to the type of approval.
This is an abstract type.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|status|[plannerApprovalStatus](../resources/plannerbaseapprovalattachment.md#plannerapprovalstatus-values)|Status of the approval.The possible values are: `requested`, `approved`, `rejected`, `cancelled`, `unknownFutureValue`. You must use the `Prefer: include-unknown-enum-members` request header to get the following value in this [evolvable enum](/graph/best-practices-concept#handling-future-members-in-evolvable-enumerations).

### plannerApprovalStatus values 

| Member             |
|:-------------------|
| requested          |
| approved           |
| rejected           |
| cancelled          |
| unknownFutureValue |

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.plannerBaseApprovalAttachment"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.plannerBaseApprovalAttachment",
  "status": "String"
}
```

