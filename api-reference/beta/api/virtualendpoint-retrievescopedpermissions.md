---
title: "virtualEndpoint: retrieveScopedPermissions"
description: "Get the permissions and corresponding scope IDs for which the authenticated user has access."
author: "AshleyYangSZ"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: apiPageType
---

# virtualEndpoint: retrieveScopedPermissions

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get the permissions and corresponding scope IDs for which the authenticated user has access.

[!INCLUDE [national-cloud-support](../../includes/global-us.md)]

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|CloudPC.Read.All, CloudPC.ReadWrite.All|
|Delegated (personal Microsoft account) | Not supported.|
|Application| Not supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

``` http
GET /deviceManagement/virtualEndpoint/retrieveScopedPermissions
```

## Request headers

| Name          | Description               |
| :------------ | :------------------------ |
| Authorization | Bearer {token}. Required. |

## Request body

Don't supply a request body for this method.

## Response

If successful, this function returns a `200 OK` response code and a collection of [cloudPcScopedPermission](../resources/cloudpcscopedpermission.md) objects in the response body.
This API supports filter with permission, when no filter, this function returns all permissions and scope Tag IDs of the authenticated user.

## Optional query parameters
This method supports the $filter OData query parameter to customize the response. If the $filter parameter is not included, the function returns all permissions and scope IDs of the authenticated user.

## Examples

### Example 1: Get all the permissions and scope IDs of the authenticated user
The following example shows a request without the `$filter` query to get the permissions and scope IDs of the authenticated user. 

#### Request

The following example shows the request.

<!-- {
  "blockType": "request",
  "name": "virtualendpoint_retrieveScopedPermissions1"
}
-->

``` http
GET https://graph.microsoft.com/beta/deviceManagement/virtualEndpoint/retrieveScopedPermissions
```

#### Response

The following example shows the response.

> **Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(Edm.String)"
}
-->

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#Collection(microsoft.graph.cloudPcScopedPermission)",
    "@odata.count": 4,
    "value": [
        {
            "permission": "Microsoft.CloudPC/ProvisioningPolicies/Create",
            "scopeIds": ["1"]
        },
        {
            "permission": "Microsoft.CloudPC/ProvisioningPolicies/Update",
            "scopeIds": ["1","2"]
        },
        {
            "permission": "Microsoft.CloudPC/ProvisioningPolicies/Read",
            "scopeIds": ["1","2"]
        },
        {
            "permission": "Microsoft.CloudPC/ProvisioningPolicies/Assign",
            "scopeIds": ["1"]
        }
    ]
}
```

### Example 2: Get a filtered list of permissions and scope IDs of the authenticated user
The following example shows a request with the specific `$filter` query to get a list of permissions and scope IDs of the authenticated user. 

#### Request

The following example shows a request with a filter.

<!-- {
  "blockType": "request",
  "name": "virtualendpoint_retrieveScopedPermissions2"
}
-->

``` http
GET https://graph.microsoft.com/beta/deviceManagement/virtualEndpoint/retrieveScopedPermissions?$filter=permission in ('Microsoft.CloudPC/ProvisioningPolicies/Update','Microsoft.CloudPC/ProvisioningPolicies/Create')
```

#### Response

The following example shows the response.

> **Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(Edm.String)"
}
-->

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#Collection(microsoft.graph.cloudPcScopedPermission)",
    "@odata.count": 2,
    "value": [
        {
            "permission": "Microsoft.CloudPC/ProvisioningPolicies/Update",
            "scopeIds": ["1","2"]
        },
        {
            "permission": "Microsoft.CloudPC/ProvisioningPolicies/Update",
            "scopeIds": ["1"]
        }
    ]
}
```

### Example 3: No scope IDs are returned

#### Request

When the signed-in user has the Microsoft Entra Global admin role, the Windows 365 admin role, or the Intune admin role assigned by Microsoft Entra ID, the returned permission is *\**, and no scope IDs are returned. In these cases, queries aren't supported.

<!-- {
  "blockType": "request",
  "name": "virtualendpoint_retrieveScopedPermissions3"
}
-->

``` http
GET https://graph.microsoft.com/beta/deviceManagement/virtualEndpoint/retrieveScopedPermissions
```

#### Response

The following example shows the response.

> **Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(Edm.String)"
}
-->

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#Collection(microsoft.graph.cloudPcScopedPermission)",
    "@odata.count": 1,
    "value": [
        {
            "permission": "*",
            "scopeIds": []
        }
    ]
}
```
