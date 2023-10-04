---
title: "permissionsDefinitionAuthorizationSystem resource type"
description: "Represents the authorization system that the permissions will be requested on."
author: "mrudulahg01"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: resourcePageType
---

# permissionsDefinitionAuthorizationSystem resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents the authorization system that the permissions will be requested on.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|authorizationSystemId|String|The Authorization System Id.|
|authorizationSystemType|String|The Authorization System Type.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.permissionsDefinitionAuthorizationSystem"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.permissionsDefinitionAuthorizationSystem",
  "authorizationSystemId": "String",
  "authorizationSystemType": "String"
}
```

