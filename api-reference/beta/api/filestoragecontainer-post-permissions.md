---
title: "Add permission"
description: "Add permission to a fileStorageContainer instance"
author: "tonchan-msft"
ms.localizationpriority: medium
ms.prod: "files"
doc_type: apiPageType
---

# Create permission
Namespace: microsoft.graph



Adds [permission](../resources/permission.md) objects to an existing fileStorageContainer. The application calling this API must have permissions to manage access to containers of the containerType the container belongs to.


## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|FileStorageContainer.Selected|
|Delegated (personal Microsoft account)|FileStorageContainer.Selected|
|Application|FileStorageContainer.Selected|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /storage/fileStorage/containers/{fileStorageContainerId}/permissions
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [permission](../resources/permission.md) object.

## Response

If successful, this method returns a `201 Created` response code and a [permission](../resources/permission.md) object in the response body.

## Examples

### Request
This example adds a new user as reader to a container.
<!-- {
  "blockType": "request",
  "name": "create_permission_from_"
}
-->
``` http
POST https://graph.microsoft.com/beta/storage/fileStorage/containers/{containerId}/permissions
Content-type: application/json

{
  "roles": ["reader"],
  "grantedToV2": {
    "user": {
      "userPrincipalName": "jacob@fabrikam.com"
    }
  }
}
```


### Response
The following is an example of the response. If successful, this method returns a `201 Created` response code and a [permission](../resources/permission.md) object in the response body.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "oneDrive.permission"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.permission",
  "id": "cJpbmNpcGFsT3duZAJfaLowIy5mfG1lbWJliZXJzaGlwfHJvcnlicjExMUBvdXRsb29rLmNvbQ",
  "roles": ["reader"],
  "grantedToV2": {
    "user": {
      "id": "89ea5c94-7736-4e25-95ad-3fa95f62b66e",
      "userPrincipalName": "jacob@fabrikam.com",
      "displayName": "Jacob Hancock",
      "email": "jacob@fabrikam.com"
    }
  }
}
```

