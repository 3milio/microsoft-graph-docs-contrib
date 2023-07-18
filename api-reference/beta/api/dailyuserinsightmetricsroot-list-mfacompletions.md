---
title: "List dailyMfaCompletions"
description: "Get the mfaCompletionMetric resources from the mfaCompletions navigation property."
author: "kingjuli"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# List dailyMfaCompletions
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get the mfaCompletionMetric resources from the mfaCompletions navigation property.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|Insights-UserMetrics.Read.All|
|Delegated (personal Microsoft account)|Not supported|
|Application|Not supported|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /reports/userInsights/daily/mfaCompletions
```

## Optional query parameters
This method supports the $filter, $select, server-side paging through a large response, and in-clause filter OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [mfaCompletionMetric](../resources/mfacompletionmetric.md) objects in the response body.

## Examples

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "list_mfacompletionmetric"
}
-->
``` http
GET https://graph.microsoft.com/beta/reports/userInsights/daily/mfaCompletions
```


### Response
The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(Microsoft.AAD.Reporting.mfaCompletionMetric)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#Microsoft.AAD.Reporting.mfaCompletionMetric",
      "id": "87675ec1-a1c5-712f-7b62-af3e5bcd0b51",
      "factDate": "Date",
      "attemptsCount": "Integer",
      "successCount": "Integer",
      "mfaMethod": "String",
      "os": "String",
      "appId": "String"
    }
  ]
}
```

