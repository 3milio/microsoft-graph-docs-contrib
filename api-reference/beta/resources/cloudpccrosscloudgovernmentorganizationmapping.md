---
title: "cloudPcCrossCloudGovernmentOrganizationMapping resource type"
description: "**TODO: Add Description**"
author: "SuyliuMS"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: resourcePageType
---

# cloudPcCrossCloudGovernmentOrganizationMapping resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents Cloud PC organization mapping between public cloud organization and US government cloud organization.
For GCC (US Government Community Cloud) customers, the Azure Active Directory for tenant is in public cloud, but the Azure resources and Windows 365 Cloud PCs are in US government cloud. This mapping is required for customer administrators to setup & config Windows 365 and for the end users at GCC customers to access their Windows 365 Cloud PCs. The setup and maintenance of the tenant mapping must be done while maintaining the security and compliance requirements for the FedRAMP certification and onboarding to the US Government cloud.

Inherits from [entity](../resources/entity.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[Create cloudPcCrossCloudGovernmentOrganizationMapping](../api/virtualendpoint-post-crosscloudgovernmentorganizationmapping.md)|[cloudPcCrossCloudGovernmentOrganizationMapping](../resources/cloudpccrosscloudgovernmentorganizationmapping.md)|Create a new [cloudPcCrossCloudGovernmentOrganizationMapping](../resources/cloudpccrosscloudgovernmentorganizationmapping.md) object.|
|[Get cloudPcCrossCloudGovernmentOrganizationMapping](../api/cloudpccrosscloudgovernmentorganizationmapping-get.md)|[cloudPcCrossCloudGovernmentOrganizationMapping](../resources/cloudpccrosscloudgovernmentorganizationmapping.md)|Read the properties and relationships of a [cloudPcCrossCloudGovernmentOrganizationMapping](../resources/cloudpccrosscloudgovernmentorganizationmapping.md) object.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|id|String|The tenant ID of the GCC (US Government Community Cloud) tenant in public cloud. Inherited from [entity](../resources/entity.md).|
|organizationIdsInUSGovCloud|String collection|The ID of the tenant in Azure Government corresponding to the GCC (US Government Community Cloud) tenant in public cloud. We only support 1:1 mapping for now, so this collection can only contains 1 tenant ID.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.cloudPcCrossCloudGovernmentOrganizationMapping",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.cloudPcCrossCloudGovernmentOrganizationMapping",
  "id": "String (identifier)",
  "organizationIdsInUSGovCloud": [
    "String"
  ]
}
```

