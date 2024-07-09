---
title: "securityScoreHistory resource type"
description: "The security score history entity"
author: "evandontje-ms"
ms.localizationpriority: medium
ms.subservice: "partner-customer-administration"
doc_type: resourcePageType
---

# securityScoreHistory resource type

Namespace: microsoft.graph.partner.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a single history entry for the security score where the score or the requirements changed.


Inherits from [microsoft.graph.entity](../resources/entity.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List](../api/partner-security-partnersecurityscore-list-history.md)|[microsoft.graph.partner.security.securityScoreHistory](../resources/partner-security-securityscorehistory.md) collection|Get a list of the [microsoft.graph.partner.security.securityScoreHistory](../resources/partner-security-securityscorehistory.md) objects and their properties.|
|[Get](../api/partner-security-securityscorehistory-get.md)|[microsoft.graph.partner.security.securityScoreHistory](../resources/partner-security-securityscorehistory.md)|Read the properties and relationships of a [microsoft.graph.partner.security.securityScoreHistory](../resources/partner-security-securityscorehistory.md) object.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|compliantRequirementsCount|Int64|The count of compliant security requirements at the time.|
|createdDateTime|DateTimeOffset|The date the history entry was created.|
|id|String|Identifier for the history entry.|
|score|Single|The score recorded at this time.|
|totalRequirementsCount|Int64|The total count of requirements at the time.|

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.partner.security.securityScoreHistory",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.partner.security.securityScoreHistory",
  "id": "String (identifier)",
  "createdDateTime": "String (timestamp)",
  "score": "Single",
  "compliantRequirementsCount": "Integer",
  "totalRequirementsCount": "Integer"
}
```

