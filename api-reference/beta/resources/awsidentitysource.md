---
title: "awsIdentitySource resource type"
description: "Represents an permissionsDefinitionIdentitySource for when the user is a cross account user in AWS."
author: "mrudulahg01"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: resourcePageType
---

# awsIdentitySource resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents an permissionsDefinitionIdentitySource for when the user is a cross account user in AWS.

Inherits from [permissionsDefinitionIdentitySource](../resources/permissionsdefinitionidentitysource.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|authorizationSystemInfo|[permissionsDefinitionAuthorizationSystem](../resources/permissionsdefinitionauthorizationsystem.md)|Authorization System Info of the source of the user.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.awsIdentitySource"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.awsIdentitySource",
  "authorizationSystemInfo": {
    "@odata.type": "microsoft.graph.permissionsDefinitionAuthorizationSystem"
  }
}
```

