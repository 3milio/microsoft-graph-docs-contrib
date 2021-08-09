---
title: "sourceCollection resource type"
description: "**TODO: Add Description**"
author: "**TODO: Provide Github Name. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
localization_priority: Normal
ms.prod: "**TODO: Add MS prod. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
doc_type: resourcePageType
---

# sourceCollection resource type

Namespace: microsoft.graph.ediscovery

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

**TODO: Add Description**


Inherits from [entity](../resources/ediscovery-entity.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List sourceCollections](../api/ediscovery-sourcecollection-list.md)|[microsoft.graph.ediscovery.sourceCollection](../resources/ediscovery-sourcecollection.md) collection|Get a list of the [sourceCollection](../resources/ediscovery-sourcecollection.md) objects and their properties.|
|[Create sourceCollection](../api/ediscovery-sourcecollection-create.md)|[microsoft.graph.ediscovery.sourceCollection](../resources/ediscovery-sourcecollection.md)|Create a new [sourceCollection](../resources/ediscovery-sourcecollection.md) object.|
|[Get sourceCollection](../api/ediscovery-sourcecollection-get.md)|[microsoft.graph.ediscovery.sourceCollection](../resources/ediscovery-sourcecollection.md)|Read the properties and relationships of a [sourceCollection](../resources/ediscovery-sourcecollection.md) object.|
|[Update sourceCollection](../api/ediscovery-sourcecollection-update.md)|[microsoft.graph.ediscovery.sourceCollection](../resources/ediscovery-sourcecollection.md)|Update the properties of a [sourceCollection](../resources/ediscovery-sourcecollection.md) object.|
|[Delete sourceCollection](../api/ediscovery-sourcecollection-delete.md)|None|Deletes a [sourceCollection](../resources/ediscovery-sourcecollection.md) object.|
|[List noncustodialSources](../api/ediscovery-sourcecollection-list-noncustodialsources.md)|[microsoft.graph.ediscovery.dataSource](../resources/ediscovery-datasource.md) collection|Get the dataSource resources from the noncustodialSources navigation property.|
|[Add dataSource](../api/ediscovery-sourcecollection-post-noncustodialsources.md)|[microsoft.graph.ediscovery.dataSource](../resources/ediscovery-datasource.md)|Add noncustodialSources by posting to the noncustodialSources collection.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|contentQuery|String|**TODO: Add Description**|
|createdBy|[microsoft.graph.identitySet](../resources/ediscovery-identityset.md)|**TODO: Add Description**|
|createdDateTime|DateTimeOffset|**TODO: Add Description**|
|dataSourceScopes|dataSourceScopes|**TODO: Add Description**. Possible values are: `none`, `allTenantMailboxes`, `allTenantSites`, `allCaseCustodians`, `allCaseNoncustodialDataSources`, `unknownFutureValue`.|
|description|String|**TODO: Add Description**|
|displayName|String|**TODO: Add Description**|
|id|String|**TODO: Add Description** Inherited from [entity](../resources/ediscovery-entity.md).|
|lastModifiedBy|[microsoft.graph.identitySet](../resources/ediscovery-identityset.md)|**TODO: Add Description**|
|lastModifiedDateTime|DateTimeOffset|**TODO: Add Description**|
|tenantSources|tenantSources|**TODO: Add Description**. Possible values are: `allMailboxes`, `allSites`, `unknownFutureValue`.|

## Relationships
|Relationship|Type|Description|
|:---|:---|:---|
|additionalSources|[microsoft.graph.ediscovery.dataSource](../resources/ediscovery-datasource.md) collection|**TODO: Add Description**|
|addToReviewSetOperation|[addToReviewSetOperation](../resources/ediscovery-addtoreviewsetoperation.md)|**TODO: Add Description**|
|custodianSources|[microsoft.graph.ediscovery.dataSource](../resources/ediscovery-datasource.md) collection|**TODO: Add Description**|
|lastEstimateStatisticsOperation|[estimateStatisticsOperation](../resources/ediscovery-estimatestatisticsoperation.md)|**TODO: Add Description**|
|noncustodialSources|[microsoft.graph.ediscovery.dataSource](../resources/ediscovery-datasource.md) collection|**TODO: Add Description**|

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.ediscovery.sourceCollection",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.ediscovery.sourceCollection",
  "id": "String (identifier)",
  "displayName": "String",
  "description": "String",
  "createdBy": {
    "@odata.type": "microsoft.graph.identitySet"
  },
  "createdDateTime": "String (timestamp)",
  "lastModifiedBy": {
    "@odata.type": "microsoft.graph.identitySet"
  },
  "lastModifiedDateTime": "String (timestamp)",
  "contentQuery": "String",
  "tenantSources": "String",
  "dataSourceScopes": "String"
}
```

