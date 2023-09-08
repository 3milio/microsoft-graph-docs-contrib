---
title: "Get authorizationSystemResource"
description: "Read the properties and relationships of an authorizationSystemResource object."
author: "**TODO: Provide Github Name. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
ms.localizationpriority: medium
ms.prod: "**TODO: Add MS prod. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
doc_type: apiPageType
---

# Get authorizationSystemResource
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of an [authorizationSystemResource](../resources/authorizationsystemresource.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|**TODO: Provide applicable permissions.**|
|Delegated (personal Microsoft account)|**TODO: Provide applicable permissions.**|
|Application|**TODO: Provide applicable permissions.**|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /authorizationSystemResource
GET /encryptedAwsStorageBucketFinding/storageBucket
GET /encryptedGcpStorageBucketFinding/storageBucket
GET /encryptedAzureStorageAccountFinding/storageAccount
GET /openNetworkAzureSecurityGroupFinding/securityGroup
GET /externallyAccessibleAwsStorageBucketFinding/storageBucket
GET /externallyAccessibleGcpStorageBucketFinding/storageBucket
GET /virtualMachineWithAwsStorageBucketAccessFinding/ec2Instance
GET /externallyAccessibleAzureBlobContainerFinding/storageAccount
GET /privilegeEscalation/resources/{authorizationSystemResourceId}
GET /openNetworkAzureSecurityGroupFinding/virtualMachines/{authorizationSystemResourceId}
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

If successful, this method returns a `200 OK` response code and an [authorizationSystemResource](../resources/authorizationsystemresource.md) object in the response body.

## Examples

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "get_authorizationsystemresource"
}
-->
``` http
GET https://graph.microsoft.com/beta/authorizationSystemResource
```


### Response
The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.authorizationSystemResource"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.authorizationSystemResource",
    "id": "9034f4e1-5d4b-761d-4b79-71d3c0a48220",
    "externalId": "String",
    "displayName": "String",
    "resourceType": "String"
  }
}
```

