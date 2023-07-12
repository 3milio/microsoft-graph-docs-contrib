---
title: "List userCountMetrics"
description: "Get a list of the userCountMetric objects and their properties."
author: "kingjuli"
ms.localizationpriority: medium
ms.prod: "user-insights"
doc_type: apiPageType
---

# List userCountMetrics
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [userCountMetric](../resources/usercountmetric.md) objects and their properties.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|Insights-UserMetrics.Read.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /reports/userInsights/daily/userCount
```

## Optional query parameters
This method supports the $filter, $select, server-side paging through a large response and in-clause filter OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [userCountMetric](../resources/usercountmetric.md) objects in the response body.

## Examples

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "list_usercountmetric"
}
-->
``` http
GET https://graph.microsoft.com/beta/reports/userInsights/daily/userCount
```


### Response
The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(Microsoft.AAD.Reporting.userCountMetric)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#Microsoft.AAD.Reporting.userCountMetric",
      "id": "9bf0ee43-c44c-d3bb-2559-47d849b63d84",
      "factDate": "Date",
      "count": "Integer"
    }
  ]
}
```

