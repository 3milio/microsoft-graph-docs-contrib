---
title: "Get teamwork."
description: "Get organization settings for teamwork, such as the region of the organization and the Microsoft Teams enablement status."
author: "mea"
ms.localizationpriority: high
ms.prod: "microsoft-teams"
doc_type: apiPageType
---

# Get teamwork

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get the properties and relationships of a [teamwork](../resources/teamwork.md) object, such as the region of the organization and whether Microsoft Teams is enabled.

[!INCLUDE [national-cloud-support](../../includes/all-clouds.md)]

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission Type                        | Permissions (from least to most privileged)  |
| :------------------------------------- | :------------------------------------------------------------------------------------------------ |
| Delegated (work or school account)     | Teamwork.Read.All                                                                                 |
| Delegated (personal Microsoft account) | Not supported.                                                                                    |
| Application                            |  Teamwork.Read.All                                                                            |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /teamwork
```

## Request headers

| Header           | Value                      |
| :--------------- | :------------------------- |
| Authorization    | Bearer {token}. Required.  |

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code along with a [teamwork](../resources/teamwork.md) object in the response body.

## Examples

### Request

The following example shows the request.

<!-- {
  "blockType": "request",
  "name": "get_teamworkSettings_for_organization",
}-->
```msgraph-interactive
GET https://graph.microsoft.com/beta/teamwork
```

### Response

The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.teamwork"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#teamwork",
    "id": "teamwork",
    "isTeamsEnabled": true,
    "region": "Americas"
}
```

## See also

- [Get the licensing details of a user](licenseDetails-getteamslicensingdetails.md)
- [Get the settings of a user for Microsoft Teams](userteamwork-get.md)
