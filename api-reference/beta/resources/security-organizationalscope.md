---
title: "organizationalScope resource type"
description: "The scope to specify which devices are covered by a custom detection rule's detection action"
author: "mmekler"
ms.localizationpriority: medium
ROBOTS: NOINDEX
ms.prod: "security"
doc_type: resourcePageType
---

# organizationalScope resource type

Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The scope to specify which devices are covered by a [custom detection rule's](../resources/security-detectionrule.md) [detection action](../resources/security-detectionaction.md).

## Properties
| Property   | Type                                                                                  | Description                                                                                         |
|:-----------|:--------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------|
| scopeNames | String collection                                                                     | List of groups to which the custom detection rule applies.                                          |
| scopeType  | [microsoft.graph.security.scopeType](../resources/enums-security.md#scopetype-values) | The type of the organizational scope. The possible values are: `deviceGroup`, `unknownFutureValue`. |

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.security.organizationalScope"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.security.organizationalScope",
  "scopeType": "String",
  "scopeNames": [
    "String"
  ]
}
```

