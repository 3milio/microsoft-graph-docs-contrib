---
title: "Get permissionsRequestChange"
description: "Read the properties and relationships of a permissionsRequestChange object."
author: "mrudulahg01"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: apiPageType
---

# Get permissionsRequestChange
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of a [permissionsRequestChange](../resources/permissionsrequestchange.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|Not supported.|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

[!INCLUDE [epm-rbac-servicenow-apis-read](../includes/rbac-for-apis/epm-rbac-servicenow-apis-read.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /beta/identityGovernance/permissionsManagement/permissionsRequestChanges/{permissionsRequestChangeId}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [permissionsRequestChange](../resources/permissionsrequestchange.md) object in the response body.

## Examples

Retrieving a single changelog of a scheduled permissions request.

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "get_permissionsrequestchange"
}
-->
``` http
GET https://graph.microsoft.com/beta/identityGovernance/permissionsManagement/permissionsRequestChanges/00000000-0000-0000-0000-000000000001
```


### Response
The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.permissionsRequestChange"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#permissionsRequestChanges",
  "id": "00000000-0000-0000-0000-000000000001",
  "modificationDateTime": "2023-02-06T12:15:00Z",
  "statusDetail": "submitted",
  "ticketId": "INC1234567",
  "permissionsRequestId": "00000000-0000-0000-0000-000000000001"
}
```

