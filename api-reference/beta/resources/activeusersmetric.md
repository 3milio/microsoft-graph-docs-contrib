---
title: "activeUsersMetric resource type"
description: "Insights for users who were active for a specific period. This is calculated as count of all users who made at least one authentication request in that period."
author: "kingjuli"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# activeUsersMetric resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Insights for users who were active for a specific period. This is calculated as count of all users who made at least one authentication request in that period.

> **_NOTE:_**
> A user may be counted more that once if they use multiple device platforms. This shall be communicated to the customer.
> Because of this, if you combine all counts in this entity, it should **NOT** tally with the sum in the summary entity above.

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List dailyActiveUsersMetric](../api/dailyuserinsightmetricsroot-list-activeusers.md)|[dailyActiveUsersMetric](../resources/activeusersmetric.md) collection|Get a list of the daily [activeUsersMetric](../resources/activeusersmetric.md) objects and their properties.|
|[List monthlyActiveUsersMetric](../api/monthlyuserinsightsmetricsroot-list-activeusers.md)|[activeUsersMetric](../resources/activeusersmetric.md) collection|Get a list of the monthly [activeUsersMetric](../resources/activeusersmetric.md) objects and their properties.|


## Properties
|Property|Type|Description|
|:---|:---|:---|
| `id`       | `string`    | Identifier for the user insight. |
| `factDate` | `Edm.Date`  | Day of the insight.              |
| `count`    | `Edm.Int64` | Number of users.                 |

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.activeUsersMetric",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.activeUsersMetric",
  "id": "String (identifier)",
  "factDate": "Date",
  "count": "Integer"
}
```

