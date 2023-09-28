---
title: "List fileStorageContainer custom property"
description: "List the custom properties on a fileStorageContainer"
author: "tonchan-msft"
ms.localizationpriority: medium
ms.prod: "files"
doc_type: apiPageType
---

# List fileStorageContainer custom property
Namespace: microsoft.graph

List the custom properties on a fileStorageContainer. Caller can either retrieve all custom properties or get specific property by name.

The application calling this API must have permissions to access the contents of containers of the containerType the container belongs to.

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
GET /storage/fileStorage/containers/{containerId}/customProperties
GET /storage/fileStorage/containers/{containerId}/customProperties/{propertyName}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|


## Response

If successful, this action returns a `200 OK` response code.

## Examples

### Request
The following is an example of getting a custom propety names "clientUniquieId".
<!-- {
  "blockType": "request",
  "name": "filestoragecontainerthis.list-customproperty"
}
-->
``` http
GET /storage/fileStorage/containers/{containerId}/customProperties/clientUniqueId
```


### Response
The following is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 200 Ok
Content-type: application/json

{
  "value": "c5d88310-1fc7-49be-80ca-e7d7a11e638b",
  "isSearchable": true
}

```
### Request
The following is an example of getting all custom properties of a fileStorageContainer.
<!-- {
  "blockType": "request",
  "name": "filestoragecontainerthis.list-customproperty"
}
-->
``` http
GET /storage/fileStorage/containers/{containerId}/customProperties/
```


### Response
The following is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 200 Ok
Content-type: application/json

{
  "clientUniqueId": {
    "value": "c5d88310-1fc7-49be-80ca-e7d7a11e638b",
    "isSearchable": true
  },
  "color": {
    "value": "purple"
  }
}
```
