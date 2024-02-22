---
title: "authenticationConditionsApplications resource type"
description: "The applications on which an authenticationEventListener should trigger."
author: "soneff"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# authenticationConditionsApplications resource type

Namespace: microsoft.graph

The applications on which an authenticationEventListener should trigger.

## Properties
|Property|Type|Description|
|:---|:---|:---|

## Relationships
|Relationship|Type|Description|
|:---|:---|:---|
|includeApplications|[authenticationConditionApplication](../resources/authenticationconditionapplication.md) collection|Collection of the application conditions on which an authenticationEventListener should trigger.|

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.authenticationConditionsApplications"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.authenticationConditionsApplications",
}
```

