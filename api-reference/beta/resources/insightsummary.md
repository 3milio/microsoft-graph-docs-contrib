---
title: "insightSummary resource type"
description: "Summary of all usage insights for a specific time period."
author: "srutto"
ms.localizationpriority: medium
ms.prod: "identity-and-access-reports"
doc_type: resourcePageType
---

# insightSummary resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Summary of all usage insights for a specific time period.

> **_NOTE:_**
> A user (in activeUsers) may be counted more that once if they use multiple device platforms. This shall be communicated to the customer.
> This endpoint is meant to provide a summary of the insights. A breakdown of each insight is available in the latter entities.

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List insightSummaries](../api/dailyuserinsightmetricsroot-list-summary.md)|[insightSummary](../resources/insightsummary.md) collection|Get a list of the [insightSummary](../resources/insightsummary.md) objects and their properties.|
|[Get insightSummary](../api/insightsummary-get.md)|[insightSummary](../resources/insightsummary.md)|Read the properties and relationships of an [insightSummary](../resources/insightsummary.md) object.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|activeUsers|Int64|Daily active users.|
|appId|String|Application id the users sent requests to.|
|authenticationCompletions|Int64|Daily authentication completions.|
|authenticationRequests|Int64|Daily authentication requests.|
|factDate|Date|Day/Month of the insight.|
|id|String|Identifier for the insight.|
|os|String|The device plaform that the customers used. (Filterable)|
|securityTextCompletions|Int64|Daily MFA SMS completions.|
|securityTextRequests|Int64|Daily MFA SMS requests.|
|securityVoiceCompletions|Int64|Daily MFA Voice completions.|
|securityVoiceRequests|Int64|Daily MFA Voice requests.|

## Relationships
None.

## JSON representation
Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.insightSummary",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.insightSummary",
  "id": "String (identifier)",
  "factDate": "Date",
  "activeUsers": "Integer",
  "authenticationRequests": "Integer",
  "authenticationCompletions": "Integer",
  "securityTextRequests": "Integer",
  "securityTextCompletions": "Integer",
  "securityVoiceRequests": "Integer",
  "securityVoiceCompletions": "Integer",
  "os": "String",
  "appId": "String"
}
```

