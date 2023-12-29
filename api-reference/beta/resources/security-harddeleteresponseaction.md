---
title: "hardDeleteResponseAction resource type"
description: "Describes a 'Hard Delete' email response action"
author: "mmekler"
ms.localizationpriority: medium
ROBOTS: NOINDEX
ms.prod: "security"
doc_type: resourcePageType
---

# hardDeleteResponseAction resource type

Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Describes a 'Hard Delete' email response action.
Deletes the email message.

Inherits from [microsoft.graph.security.responseAction](../resources/security-responseaction.md).

## Properties
| Property   | Type                                                                                                          | Description                                                                                                                                                                                   |
|:-----------|:--------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| identifier | [microsoft.graph.security.emailEntityIdentifier](../resources/enums-security.md#emailentityidentifier-values) | Unique identifier for the response action. Default is `networkMessageId`,`recipientEmailAddress`. The possible values are: `networkMessageId`, `recipientEmailAddress`, `unknownFutureValue`. |

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.security.hardDeleteResponseAction"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.security.hardDeleteResponseAction",
  "identifier": "String"
}
```

