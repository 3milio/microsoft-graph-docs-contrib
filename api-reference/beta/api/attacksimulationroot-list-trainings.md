---
title: "List trainings"
description: "Get a list of the training objects and their properties."
author: "stuartcl"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: apiPageType
---

# List trainings

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [training](../resources/training.md) objects and their properties.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | AttackSimulation.ReadWrite.All              |
| Delegated (personal Microsoft account) | Not supported.                              |
| Application                            | AttackSimulation.ReadWrite.All              |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /security/attackSimulation/trainings
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

If successful, this method returns a `200 OK` response code and a collection of [training](../resources/training.md) objects in the response body.

## Examples

### Request

The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "list_trainings"
}
-->
``` http
GET https://graph.microsoft.com/beta/security/attackSimulation/trainings
```

### Response

The following is an example of the response.

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.training)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "id": "1cdfcb49-1065-46a6-b1c3-672071e20a6b",
      "displayName": "Email phish prevention training",
      "description": "Email phish prevention training",
      "duratonInMinutes": "30",
      "source": "microsoft",
      "type": "dataPrivacy",
      "tags": [],
      "availabilityStatus": "available",
      "hasEvaluation": false,
      "supportedLocales": [
        "en-us",
        "de-de"
      ],
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
