---
title: "delegatedAdminServiceManagementDetail resource type"
description: "Contains the management details of a delegated admin service."
author: "amharris1331"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: resourcePageType
---

# delegatedAdminServiceManagementDetail resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Contains the management details of a delegated admin service.

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List delegatedAdminServiceManagementDetails](../api/tenantrelationship-list-delegatedadminservicemanagementdetails.md)|[delegatedAdminServiceManagementDetail](delegatedadminservicemanagementdetail.md)|Get a list of the **delegatedAdminServiceManagementDetail** objects and their properties.|


## Properties
|Property|Type|Description|
|:---|:---|:---|
|serviceId|String|The service ID of a managed service.|
|serviceManagementUrl|String|The service name of a managed service.|
|serviceName|String|The URL of the management portal for the managed service.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.delegatedAdminServiceManagementDetail"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.delegatedAdminServiceManagementDetail",
  "serviceId": "M365 Lighthouse",
  "serviceName": "Microsoft 365 Lighthouse",
  "serviceManagementUrl": "https://lighthouse.microsoft.com"
}
```

