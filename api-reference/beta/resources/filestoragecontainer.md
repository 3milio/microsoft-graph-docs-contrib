---
title: "fileStorageContainer resource type"
description: "fileStorageContainer resource type"
author: "tonchan-msft"
ms.localizationpriority: medium
ms.prod: "files"
doc_type: resourcePageType
---

# fileStorageContainer resource type

Namespace: microsoft.graph


The **fileStorageContainer** resource represents a file storage container. A file storeage container is a shared file storage space that can be used by a user or a group of users via an application. All file system objects in a fileStorageContainer are returned as |[driveItem](../resources/driveItem.md)| resources. 

**FileStorageContainer** resources have properties that provide data about the fileStorageContainer's status and access setting. This includes:
* **ContainerType** specifies the application workload that owns or can access of all containers of that container type. Each container must have only one container type. 
* **Permissions** specifies the users who own or can access the container. 
* **Status** specifies the current state of the container. Containers are created as inactive and require activation. Inactive containers are subjected to automatic deletion in 24 hours.

##Permission roles enumeration

|Role|Details|
|:---|:---|
|reader|Provides the abililty to read the contents inside a storage container.|
|writer|Proviodes the ability to read and modify the content inside a storage container.|
|manager|Provides the ability to read and modify the content inside a storage container, and manage the permissions to the container.|
|owner|Provides the ability to read and modify the content inside a storage container, manage the permission to the container, and delete and restore the container.|
|principalOwner|Provides same ability as owner role. Container's lifecycle is tied to the principalOwner.|

FileStorageContainer can be either user-owned (in Consumer space only) and tenant-owned (in Enterprise space only). The following applies to user-owned containers:
* Each container must have one and only one principalOwner.
* The principalOwner is assigned at container creation time and is immutable.
* A user can be the principalOwner for multiple containers.
* Only principalOwners can delete their containers.
* PrincipalOwners cannot resign from the containers.

##Container status enumeration

|Status|Details|
|:---|:---|
|inactive|The container is inactive.|
|active|The container is active.|

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List fileStorageContainers](../api/filestorage-list-containers.md)|[fileStorageContainer](../resources/filestoragecontainer.md) collection|Get a list of the [fileStorageContainer](../resources/filestoragecontainer.md) objects and their properties.|
|[Create fileStorageContainer](../api/filestoragecontainer-post-filestoragecontainers.md)|[fileStorageContainer](../resources/filestoragecontainer.md)|Create a new [fileStorageContainer](../resources/filestoragecontainer.md) object.|
|[Get fileStorageContainer](../api/filestoragecontainer-get.md)|[fileStorageContainer](../resources/filestoragecontainer.md)|Read the properties and relationships of a [fileStorageContainer](../resources/filestoragecontainer.md) object.|
|[Update fileStorageContainer](../api/filestoragecontainer-update.md)|[fileStorageContainer](../resources/filestoragecontainer.md)|Update the properties of a [fileStorageContainer](../resources/filestoragecontainer.md) object.|
|[Delete fileStorageContainer](../api/filestorage-delete-containers.md)|None|Delete a [fileStorageContainer](../resources/filestoragecontainer.md) object.|
|[Activate fileStorageContainer](../api/filestoragecontainer-activate.md)|None|Activate a [fileStorageContainer](../resources/filestoragecontainer.md) object.|
|[List drive](../api/filestoragecontainer-list-drive.md)|[drive](../resources/drive.md) collection|Get the drive resources from the drive navigation property.|
|[List permissions](../api/filestoragecontainer-list-permissions.md)|[permission](../resources/permission.md) collection|Retreive the list of permissions on a fileStorageContainer.|
|[Create permissions](../api/filestoragecontainer-post-permissions.md)|[permission](../resources/permission.md)|Add the permission to a fileStorageContainer.|
|[Update permissions](../api/filestoragecontainer-post-permissions.md)|[permission](../resources/permission.md)|Update the permission on a fileStorageContainer.|
|[Delete permissions](../api/filestoragecontainer-post-permissions.md)|[permission](../resources/permission.md)|Delete fhte permission from a fileStorageContainer.|
|[List fileStorageContainer custom property](../api/filestoragecontainer-list-customproperty.md)|[filestoragecontainercustompropertyvalue](../resources/filestoragecontainercustompropertyvalue.md)|List the custom properties of the fileStorageContainer.|
|[Create fileStorageContainer custom property](../api/filestoragecontainer-add-customproperty.md)|[filestoragecontainercustompropertyvalue](../resources/filestoragecontainercustompropertyvalue.md)|Create a new custom property to the fileStorageContainer.|
|[Update fileStorageContainer custom property](../api/filestoragecontainer-update-customproperty.md)|[filestoragecontainercustompropertyvalue](../resources/filestoragecontainercustompropertyvalue.md)|Update custom property on a fileStorageContainer.|
|[Delete fileStorageContainer custom property](../api/filestoragecontainer-delete-customproperty.md)|[filestoragecontainercustompropertyvalue](../resources/filestoragecontainercustompropertyvalue.md)|Delete custom property from a fileStorageContainer.|

## Properties

|Property|Type|Description|
|:---|:---|:---|
|containerTypeId|Guid|Container type of the fileStorageContainer. Read-only.|
|createdDateTime|DateTimeOffset|Date and time of fileStorageContainer creation. Read-only.|
|customProperties|[fileStorageContainerCustomPropertyDictionary](../resources/filestoragecontainercustompropertydictionary.md)|Custom property collection for the fileStorageContainer. Read-write.|
|description|String|Provides a user-visible description of the fileStorageContainer. Read-write.|
|displayName|String|The display name of the fileStorageContainer. Read-write.|
|externalGroupId|Guid|The group associated with the fileStorageContainer. Optional and for Consumer space only. Immutable once set.|
|id|String|The unique stable identifier of the filerStorageContainer. Read-only.|
|status|fileStorageContainerStatus|Status of the fileStorageContainer. Read-only.|
|viewpoint|[fileStorageContainerViewpoint](../resources/filestoragecontainerviewpoint.md)|Data specific to the current user. Read-Write.|

## Relationships

|Relationship|Type|Description|
|:---|:---|:---|
|drive|[drive](../resources/drive.md)|The fileStorageContainer's drive resource. Read-only.|
|permissions|[permission](../resources/permission.md) collection|Permissions of users in the fileStorageContainer. Read-write.|

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.fileStorageContainer",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.fileStorageContainer",
  "id": "String (identifier)",
  "displayName": "String",
  "description": "String",
  "containerTypeId": "Guid",
  "externalGroupId": "Guid",
  "customProperties": {
    "@odata.type": "microsoft.graph.fileStorageContainerCustomPropertyDictionary"
  },
  "viewpoint": {
    "@odata.type": "microsoft.graph.fileStorageContainerViewpoint"
  },
  "status": "String",
  "createdDateTime": "String (timestamp)"
}
```

