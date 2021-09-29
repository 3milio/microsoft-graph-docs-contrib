---
title: "cloudPcGalleryImage resource type"
description: "Represents the gallery image resource on Cloud PC."
author: "AshleyYangSZ"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: resourcePageType
---

# cloudPcGalleryImage resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents the gallery image resource on Cloud PC.

## Methods

|Method|Return type|Description|
|:---|:---|:---|
|[List galleryImages](../api/virtualendpoint-list-deviceimages.md)|[cloudPcDeviceImage](../resources/cloudpcgalleryimage.md) collection|List the properties and relationships of [cloudPcDeviceImage](../resources/cloudpcgalleryimage.md) objects.|
|[Get cloudPcGalleryImage](../api/cloudpcgalleryimage-get.md)|[cloudPcDeviceImage](../resources/cloudpcgalleryimage.md)|Read the properties and relationships of a [cloudPcDeviceImage](../resources/cloudpcgalleryimage.md) object.|

## Properties

|Property|Type|Description|
|:---|:---|:---|
|id|String|Unique identifier for the gallery image resource on the Cloud PC. Read-only.|
|displayName|String|The official display name of the gallery image. Read-only.|
|offerDisplayName|String|The official display offer name of the gallery image. For example: Windows 10 Enterprise + OS Optimizations. Read-only.|
|skuDisplayName|String|The official display SKU name of this gallery image. For example: 2004. Read-only.|
|publisher|String|Ths publisher name of the gallery image, this value will be passed to Azure to get image resource. Read-only.|
|offer|String|Ths offer name of the gallery image, this value will be passed to Azure to get image resource. Read-only.|
|sku|String|Ths SKU name of the gallery image, this value will be passed to Azure to get image resource. Read-only.|
|recommendedSku|String|Recommended Cloud PC SKU for this gallery image. Read-only.|
|status|cloudPcGalleryImageStatus|The status of the gallery image on Cloud PC. Possible values are: `supported`, `supportedWithWarning`, `notSupported`. Read-only.|
|sizeInGB|Int32|The size of this image in gigabytes. Read-only.|
|startDate|Date|The date when image becomes available. Read-only.|
|endDate|Date|The date in which this image is no longer within long term support. Cloud PC will continue to support it short term. Read-only.|
|expirationDate|Date|The date when image is no longer available. Read-only.|

### CloudPcGalleryImageStatus values

|Member|Description|
|:---|:---|
|supported|The gallery image is active and ready to be used for provisioning.|
|supportedWithWarning|The gallery image has expired, but Cloud PC will continue support for 6 months, after which it will be unsupported and cannot be used.|
|notSupported|The gallery image is out of support. |
|unknownFutureValue|Evolvable enumeration sentinel value. Do not use. |

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.cloudPcGalleryImage",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->

``` json
{
  "@odata.type": "#microsoft.graph.cloudPcDeviceImage",
  "id": "String (identifier)",
  "displayName":"String",
  "offerDisplayName":"String",
  "skuDisplayName":"String",
  "publisher":"String",
  "offer":"String",
  "sku":"String",
  "recommendedSku":"String",
  "status":"String",
  "sizeInGB":"Integer",
  "startDate":"String (Date)",
  "endDate":"String (Date)",
  "expiredDate":"String (Date)"
}
```
