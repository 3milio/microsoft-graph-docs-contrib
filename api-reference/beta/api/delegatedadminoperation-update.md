---
title: "Update delegatedAdminOperation"
description: "Update the properties of a delegatedAdminOperation object."
author: "amharris1331"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---

# Update delegatedAdminOperation
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [delegatedAdminOperation](../resources/delegatedadminoperation.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)| DelegatedAdminRelationship.ReadWrite.All |
|Delegated (personal Microsoft account)| Not supported. |
|Application| Not supported. |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /tenantRelationship/delegatedAdminRelationships/{delegatedAdminRelationshipId}/operations/{delegatedAdminOperationId}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|If-Match|Last known ETag value for the **delegated admin operation** to be updated. Required.|
|Content-Type|application/json. Required.|

## Request body
[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]


|Property|Type|Description|
|:---|:---|:---|
|operationType|String|The type of long running operation. This is set by the system and cannot be set by the caller. Required.|
|data|String|The data (payload) for the operation. Required.|
|status|String|The status of the operation. Required.|


## Response

If successful, this method returns a `200 OK` response code and an updated [delegatedAdminOperation](../resources/delegatedadminoperation.md) object in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "update_delegatedadminoperation"
  "@odata.type": "microsoft.graph.delegatedAdminOperation"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/tenantRelationship/delegatedAdminRelationships/{delegatedAdminRelationshipId}/operations/{delegatedAdminOperationId}
Authorization: Bearer {token}
If-Match: W/"JyI0NzAwNjg0NS0wMDAwLTE5MDAtMDAwMC02MGY0Yjg4MzAwMDAiJw=="
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.delegatedAdminOperation",
  "operationType": "String",
  "data": "String",
  "status": "String"
}
```


### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.delegatedAdminOperation",
  "id": "5640623e-b692-c9a1-8ab1-2ce73a84fe6f",
  "operationType": "String",
  "data": "String",
  "status": "String",
  "createdDateTime": "String (timestamp)",
  "lastModifiedDateTime": "String (timestamp)"
}
```

