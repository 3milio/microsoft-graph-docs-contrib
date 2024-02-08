---
title: "validatingDomains resource type"
description: "**TODO: Add Description**"
author: "rahul-nagraj"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# validatingDomains resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Defines the types of domains to which the federated token validation applies.
This is an abstract type.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|rootDomains|rootDomains|Defines the types of domains to which the validation will apply. The possible values are: `none`, `all`, `allFederated`, `allManaged`, `enumerated`, `allManagedAndEnumeratedFederated`, `unknownFutureValue`.|

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.validatingDomains"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.validatingDomains",
  "rootDomains": "String"
}
```

