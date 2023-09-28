---
title: "List fileStorageContainers"
description: "Get a list of fileStorageContainers and their properties."
author: "tonchan-msft"
ms.localizationpriority: medium
ms.prod: "files"
doc_type: apiPageType
---

# List fileStorageContainers
Namespace: microsoft.graph

> [!IMPORTANT]
> APIs under the `/beta` version in Microsoft Graph are subject to change. Use of these APIs in production applications is not supported. To determine whether an API is available in v1.0, use the **Version** selector.

Retrieve the list of [fileStorageContainer](../resources/filestoragecontainer.md) objects visible to the caller. ContainerTypeId filter parameter is required. The application calling these APIs must have read permission to fileStorageContainers of the respective container type.

Note: Only a limited subset of properties will be returned for each fileStorageContainer. $expand operation is not supported for drive, permissions and customProperties properties.


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
GET /storage/fileStorage/containers?$filter=containerTypeId eq {containerTypeId}
GET /storage/fileStorage/containers?$filter=containerTypeId eq {containerTypeId} and viewpoint/effectiveRole eq 'principalOwner'
```


## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Response

If successful, this method returns a `200 OK` response code and a collection of [fileStorageContainer](../resources/filestoragecontainer.md) objects in the response body.

## Examples

### Request
The following is an example of enumerating all tenant-owned containers of a given type.
<!-- {
  "blockType": "request",
  "name": "list_filestoragecontainer"
}
-->
``` http
GET /storage/fileStorage/containers?$filter=containerTypeId eq {containerTypeId}
```

### Response
The following is an example of the response
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.fileStorageContainer)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/storage/fileStorage/containers",
  "@odata.count": 1,
  "value": [
    {
      "@odata.type": "#microsoft.graph.fileStorageContainer",
      "id": "b!ISJs1WRro0y0EWgkUYcktDa0mE8zSlFEqFzqRn70Zwp1CEtDEBZgQICPkRbil_5Z",
      "displayName": "My File Storage Container",
      "containerTypeId": "e2756c4d-fa33-4452-9c36-2325686e1082",
      "createdDateTime": "2021-11-24T15:41:52.347Z"
    }
  ]
}
```

