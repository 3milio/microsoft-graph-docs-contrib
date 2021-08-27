---
title: "crossTenantAccessPolicyConfigurationDefault: resetToSystemDefault"
description: "Reset any changes made to the default configuration in a cross tenant access policy back to the system default."
author: "jkdouglas"
localization_priority: Normal
ms.prod: "microsoft-identity-platform"
doc_type: apiPageType
---

# crossTenantAccessPolicyConfigurationDefault: resetToSystemDefault

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Reset any changes made to the default configuration in a cross tenant access policy back to the system default.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|Policy.ReadWrite.CrossTenantAccess|
|Delegated (personal Microsoft account)|Not applicable|
|Application|Policy.ReadWrite.CrossTenantAccess|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

``` http
POST /policies/crossTenantAccessPolicy/default/resetToSystemDefault
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body

Do not supply a request body for this method.

## Response

If successful, this action returns a `200 OK` response code and an empty response. To confirm the reset system defaults, run [Get crossTenantAccessPolicyConfigurationDefault](../api/crosstenantaccesspolicyconfigurationdefault-get.md) and confirm that `isSystemDefault` is set to **true**.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "crosstenantaccesspolicyconfigurationdefault_resettosystemdefault"
}
-->

``` http
POST https://graph.microsoft.com/beta/policies/crossTenantAccessPolicy/default/resetToSystemDefault
```

### Response

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.crossTenantAccessPolicyConfigurationDefault"
}
-->

``` http
HTTP/1.1 200 OK
Content-Type: application/json

{

}
```
