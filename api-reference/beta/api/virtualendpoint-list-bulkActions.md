---
title: "List cloudPcBulkActions"
description: "Get a list of the cloudPcBulkAction objects and their properties."
author: "Guoan-Tang"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: apiPageType
---

# List cloudPcBulkActions
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [cloudPcBulkAction](../resources/cloudpcbulkaction.md) objects and their properties.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|CloudPC.Read.All, CloudPC.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|CloudPC.Read.All, CloudPC.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /deviceManagement/virtualEndpoint/bulkActions
```

## Optional query parameters
This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [cloudPcBulkAction](../resources/cloudpcbulkaction.md) objects in the response body.

## Examples

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "list_cloudpcbulkaction"
}
-->
``` http
GET https://graph.microsoft.com/beta/deviceManagement/virtualEndpoint/bulkActions
```


### Response
The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.cloudPcBulkAction)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.cloudPcBulkAction",
      "id": "231ad98f-41b3-872b-dd37-c70bf22cbdac",
      "displayName": "String",
      "cloudPcIds": [
        "Guid"
      ],
      "actionSummary": {
        "@odata.type": "microsoft.graph.cloudPcBulkActionSummary"
      },
      "createdDateTime": "String (timestamp)"
    }
  ]
}
```

