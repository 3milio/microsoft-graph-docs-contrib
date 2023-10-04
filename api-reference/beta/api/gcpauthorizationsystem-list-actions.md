---
title: "List gcpAuthorizationSystemTypeActions"
description: "List the gcpAuthorizationSystemTypeAction objects and their properties."
author: "mrudulahg01"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: apiPageType
---

# List gcpAuthorizationSystemTypeActions
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

List the [gcpAuthorizationSystemTypeAction](../resources/gcpauthorizationsystemtypeaction.md) objects and their properties.

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
GET /external/authorizationSystems/{computedId}/graph.gcpAuthorizationSystem/actions
```

## Optional query parameters
This method supports the `$filter` OData query parameter to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [gcpAuthorizationSystemTypeAction](../resources/gcpauthorizationsystemtypeaction.md) objects in the response body.

## Examples

### Example 1: List GCP Actions For A Specific Service

Returns collection of all gcpAuthorizationSystemTypeAction entities for a provided GCP authorization system and service the action is performed on. Listing actions for a GCP project "carbide-bonsai-205017" and service "compute".

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "list_gcpauthorizationsystemtypeaction"
}
-->
``` http
GET https://graph.microsoft.com/beta/external/authorizationSystems/{computedId}/graph.gcpAuthorizationSystem/actions?$filter=service/id eq 'compute'
```


### Response
The following is an example of the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.gcpAuthorizationSystemTypeAction)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#external/authorizationSystems/{computedId}/graph.gcpAuthorizationSystem/actions?$filter=service/id eq 'compute'",
  "value": [
    {
      "id": "Y29tcHV0ZS5hY2NlbGVyYXRvclR5cGVzLmdldA==",
      "externalId": "compute.acceleratorTypes.get",
      "resourceTypes": ["applications"],
      "severity": "normal",
      "actionType": "read",
      "service": {
        "id": "compute"
      }
    },
    {
      "id": "Y29tcHV0ZS5hY2NlbGVyYXRvclR5cGVzLmxpc3Q=",
      "externalId": "compute.acceleratorTypes.list",
      "resourceTypes": ["applications"],
      "severity": "normal",
      "actionType": "read",
      "service": {
        "id": "compute"
      }
    },
    {
      "id": "Y29tcHV0ZS5hZGRyZXNzZXMuY3JlYXRl"
      "externalId": "compute.addresses.create",
      "resourceTypes": ["addresses"],
      "severity": "high",
      "actionType": null,
      "service": {
        "id": "compute"
      }
    }
  ]
}
```

