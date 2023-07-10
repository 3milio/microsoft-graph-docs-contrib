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

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | AttackSimulation.Read.All                   |
| Delegated (personal Microsoft account) | Not supported.                              |
| Application                            | AttackSimulation.Read.All                   |

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
  "name": "list_loginpage"
}
-->
``` http
GET https://graph.microsoft.com/beta/security/attackSimulation/loginPages?$filter=source eq 'tenant'
```


### Response
The following is an example of the response
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
      "@odata.type": "#microsoft.graph.loginPage",
      "id": "588f1ccc-011f-0d7a-5fee-d2e66a1185c3",
      "displayName": "String",
      "description": "String",
      "content": "String",
      "language": "String",
      "status": "microsoft.graph.simulationContentStatus",
      "source": "microsoft.graph.simulationContentSource",
      "createdBy": {
        "@odata.type": "microsoft.graph.emailIdentity"
      },
      "createdDateTime": "String (timestamp)",
      "lastModifiedBy": {
        "@odata.type": "microsoft.graph.emailIdentity"
      },
      "lastModifiedDateTime": "String (timestamp)"
    }
  ]
}
```

