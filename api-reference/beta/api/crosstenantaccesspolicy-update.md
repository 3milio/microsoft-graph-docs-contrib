---
title: "Update crossTenantAccessPolicy"
description: "Update the properties of a cross tenant access policy."
author: "jkdouglas"
ms.localizationpriority: Medium
ms.prod: "microsoft-identity-platform"
doc_type: apiPageType
---

# Update crossTenantAccessPolicy

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [cross tenant access policy](../resources/crosstenantaccesspolicy.md).

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
PATCH /policies/crossTenantAccessPolicy
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body

In the request body, supply a JSON representation of the [crossTenantAccessPolicy](../resources/crosstenantaccesspolicy.md) object.

The following table shows the properties that are required when you update the [crossTenantAccessPolicy](../resources/crosstenantaccesspolicy.md).

|Property|Type|Description|
|:---|:---|:---|
|displayName|String|The display name of the cross tenant access policy. Inherited from [policyBase](../resources/policybase.md)|

## Response

If successful, this method returns a `200 OK` response code and an updated [crossTenantAccessPolicy](../resources/crosstenantaccesspolicy.md) object in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "update_crosstenantaccesspolicy"
}
-->

``` http
PATCH https://graph.microsoft.com/beta/policies/crossTenantAccessPolicy
Content-Type: application/json

{
  "displayName": "CrossTenantAccessPolicy",
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
HTTP/1.1 204 No Content
```
