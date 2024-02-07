---
title: "Update customClaimsPolicy"
description: "Update the properties of a customClaimsPolicy object."
author: "rahul-nagraj"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---

# Update customClaimsPolicy

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [customClaimsPolicy](../resources/customclaimspolicy.md) object.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "customclaimspolicy-update-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/customclaimspolicy-update-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /policies/claimsPolicy
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
|Content-Type|application/json. Required.|

## Request body

[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]


**TODO: Remove properties that don't apply**
|Property|Type|Description|
|:---|:---|:---|
|includeBasicClaimSet|Boolean|**TODO: Add Description** Optional.|
|includeApplicationIdInIssuer|Boolean|**TODO: Add Description** Optional.|
|audienceOverride|String|**TODO: Add Description** Optional.|
|groupFilter|[groupClaimFilterBase](../resources/groupclaimfilterbase.md)|**TODO: Add Description** Optional.|
|claims|[customClaimBase](../resources/customclaimbase.md) collection|**TODO: Add Description** Optional.|



## Response

If successful, this method returns a `200 OK` response code and an updated [customClaimsPolicy](../resources/customclaimspolicy.md) object in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "update_customclaimspolicy"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/policies/claimsPolicy
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.customClaimsPolicy",
  "includeBasicClaimSet": "Boolean",
  "includeApplicationIdInIssuer": "Boolean",
  "audienceOverride": "String",
  "groupFilter": {
    "@odata.type": "microsoft.graph.groupClaimFilterBase"
  },
  "claims": [
    {
      "@odata.type": "microsoft.graph.customClaim"
    }
  ]
}
```


### Response

The following example shows the response.
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
  "@odata.type": "#microsoft.graph.customClaimsPolicy",
  "id": "f914f36d-167e-3fa7-cfa2-355cc5a36689",
  "includeBasicClaimSet": "Boolean",
  "includeApplicationIdInIssuer": "Boolean",
  "audienceOverride": "String",
  "groupFilter": {
    "@odata.type": "microsoft.graph.groupClaimFilterBase"
  },
  "claims": [
    {
      "@odata.type": "microsoft.graph.customClaim"
    }
  ]
}
```

