---
title: "Get cloudPcProvisioningPolicy"
description: "Read the properties and relationships of a cloudPcProvisioningPolicy object."
author: "AshleyYangSZ"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: apiPageType
---

# Get cloudPcProvisioningPolicy

Namespace: microsoft.graph

Read the properties and relationships of a [cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md) object.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "cloudpcprovisioningpolicy_get" } -->
[!INCLUDE [permissions-table](../includes/permissions/cloudpcprovisioningpolicy-get-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

``` http
GET /deviceManagement/virtualEndpoint/provisioningPolicies/{id}
```

## Optional query parameters

This method supports the `$select` and `$expand` OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

| Name          | Description               |
| :------------ | :------------------------ |
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md) object in the response body.

## Examples

### Example 1: Get the properties of the specified provisioning policy

The following example shows how to get the properties of the specified provisioning policy.

#### Request

The following example shows a request.

<!-- {
  "blockType": "request",
  "name": "get_cloudpcprovisioningpolicy_1"
}
-->

``` http
GET https://graph.microsoft.com/v1.0/deviceManagement/virtualEndpoint/provisioningPolicies/{id}
```

#### Response

The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.cloudPcProvisioningPolicy"
}
-->

``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.type": "#microsoft.graph.cloudPcProvisioningPolicy",
    "description": "Description value",
    "displayName": "Display Name value",
    "domainJoinConfigurations": [
      {
        "onPremisesConnectionId": "16ee6c71-fc10-438b-88ac-daa1ccafffff",
        "domainJoinType": "hybridAzureADJoin"
      },
      {
        "onPremisesConnectionId": "26e16c71-f210-438b-88ac-d481ccafffff",
        "domainJoinType": "hybridAzureADJoin"
      }
    ],
    "enableSingleSignOn": true,
    "id": "1d164206-bf41-4fd2-8424-a3192d39ffff",
    "imageDisplayName": "Image Display Name value",
    "imageId": "Image ID value",
    "imageType": "custom",
    "windowsSetting": {
        "locale": "en-US"
    },
    "provisioningType": "dedicated"
}
```

### Example 2: Get the properties of the specified provisioning policy and expand on the assignments

The following example shows how to get the properties of the specified provisioning policy and expand on the assignments.

#### Request

The following example shows a request.

<!-- {
  "blockType": "request",
  "name": "get_cloudpcprovisioningpolicy_2"
}
-->

``` http
GET https://graph.microsoft.com/v1.0/deviceManagement/virtualEndpoint/provisioningPolicies/{id}?$expand=assignments
```

#### Response

The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.cloudPcProvisioningPolicy"
}
-->

``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.type": "#microsoft.graph.cloudPcProvisioningPolicy",
    "description": "Description value",
    "displayName": "Display Name value",
    "domainJoinConfigurations": [
      {
        "onPremisesConnectionId": "16ee6c71-fc10-438b-88ac-daa1ccafffff",
        "domainJoinType": "hybridAzureADJoin"
      },
      {
        "onPremisesConnectionId": "26e16c71-f210-438b-88ac-d481ccafffff",
        "domainJoinType": "hybridAzureADJoin"
      }
    ],
    "enableSingleSignOn": true,
    "id": "1d164206-bf41-4fd2-8424-a3192d39ffff",
    "imageDisplayName": "Image Display Name value",
    "imageId": "Image ID value",
    "imageType": "custom",
    "windowsSetting": {
        "locale": "en-US"
    },
    "assignments": [
      {
        "@odata.type": "microsoft.graph.cloudPcProvisioningPolicyAssignment",
        "id": "b0c2d35f-3385-46c8-a6f5-6c3dfad7708b_64ff06de-9c00-4a5a-98b5-7f5abe26ffff",
        "target": {
          "@odata.type":"microsoft.graph.cloudPCManagementGroupAssignmentTarget",
          "groupId":"64ff06de-9c00-4a5a-98b5-7f5abe26bfd9"
          }
      }
    ],
    "provisioningType": "dedicated"
}
```

### Example 3: Get the selected properties of the specified provisioning policy

The following example shows a request that retrieves the selected properties of the specified provisioning policy.

#### Request

The following example shows a request.

<!-- {
  "blockType": "request",
  "name": "get_cloudpcprovisioningpolicy_3"
}
-->

``` http
GET https://graph.microsoft.com/v1.0/deviceManagement/virtualEndpoint/provisioningPolicies/60b94f83-3e22-430e-a69d-440f65b922d6?$select=id,description,displayName,domainJoinConfigurations,imageDisplayName,imageId,imageType,windowsSetting,cloudPcGroupDisplayName,gracePeriodInHours,localAdminEnabled,alternateResourceUrl
```

#### Response

The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.cloudPcProvisioningPolicy"
}
-->

``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.type": "#microsoft.graph.cloudPcProvisioningPolicy",
    "alternateResourceUrl": "https://ms.portal.azure.com/#contoso.com/resource/subscriptions/827f2432-9c7b-4637-b694-570b3c2f969c/resourceGroups/myResourceGroupName/providers/Microsoft.Fidalgo/projects/myProjectName/pools/myPoolName",
    "cloudPcGroupDisplayName": "MyCloudPcGroup",
    "description": "The ProvisioningPolicy for West US employees.",
    "displayName": "WestUsPolicy",
    "domainJoinConfigurations": [
      {
        "onPremisesConnectionId": "16ee6c71-fc10-438b-88ac-daa1ccafffff",
        "domainJoinType": "hybridAzureADJoin"
      },
      {
        "onPremisesConnectionId": "26e16c71-f210-438b-88ac-d481ccafffff",
        "domainJoinType": "hybridAzureADJoin"
      }
    ],
    "enableSingleSignOn": true,
    "gracePeriodInHours": 2,
    "id": "1d164206-bf41-4fd2-8424-a3192d39ffff",
    "imageDisplayName": "myCustomImage",
    "imageId": "d4e0541a-f7bb-4bdf-ad8f-b92b915a229f",
    "imageType": "custom",
    "localAdminEnabled": true,
    "windowsSetting": {
        "locale": "en-US"
    },
    "provisioningType": "dedicated"
}
```
