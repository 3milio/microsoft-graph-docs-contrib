---
title: "List loginPages"
description: "Get a list of the loginPage objects and their properties."
author: "stuartcl"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: apiPageType
---

# List loginPages

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [loginPage](../resources/loginpage.md) objects and their properties.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged)                            |
|:---------------------------------------|:-----------------------------------------------------------------------|
| Delegated (work or school account)     | AttackSimulation.Read.All, AttackSimulation.ReadWrite.All              |
| Delegated (personal Microsoft account) | Not supported.                                                         |
| Application                            | AttackSimulation.Read.All, AttackSimulation.ReadWrite.All              |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /security/attackSimulation/loginPages?$filter=source eq 'tenant'
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

If successful, this method returns a `200 OK` response code and a collection of [loginPage](../resources/loginpage.md) objects in the response body.

## Examples

### Request

The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "list_loginpages"
}
-->
``` http
GET https://graph.microsoft.com/beta/security/attackSimulation/loginPages?$filter=source eq 'tenant'
```

### Response

The following is an example of the response.

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.loginPage)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "id": "2f5548d1-0dd8-4cc8-9de0-e0d6ec7ea3dc",
      "diplayName": "AttackSimTest loginPage",
      "description": "AttackSim Test loginPage",
      "status": "draft",
      "source": "tenant",
      "language": "en",
      "createdBy": {
        "email": "alexwaber@contoso.com",
        "id": "1rdfcb49-1065-46a6-b1c3-672071e20a6b",
        "displayName": "Alex Waber"
      },
      "createdDateTime": "2022-01-12T03:15:01.5906699Z",
      "lastModifiedBy": {
        "email": "alexwaber@contoso.com",
        "id": "1rdfcb49-1065-46a6-b1c3-672071e20a6b",
        "displayName": "Alex Waber"
      },
      "lastModifiedDateTime": "2021-10-07T12:23:18.8157586Z"
    }
  ]
}
```
