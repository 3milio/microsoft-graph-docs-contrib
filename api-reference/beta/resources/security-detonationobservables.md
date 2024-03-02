---
title: "detonationObservables resource type"
description: Represents detonation details.
author: malvika-balaraj
ms.localizationpriority: medium
ms.prod: security
doc_type: resourcePageType
---

# detonationObservables resource type

Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents detonation details such exact events that took place and URLs, IPs, domains, and files that were found during detonation (and can either be problematic or benign). 

## Properties
|Property|Type|Description|
|:---|:---|:---|
|contactedIps|String collection|The list of all contacted IPs in the detonation.|
|contactedUrls|String collection|The list of all URLs found in the detonation.|
|droppedfiles|String collection|The list of all dropped files in the detonation.|

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.security.detonationObservables"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.security.detonationObservables",
  "droppedfiles": [
    "String"
  ],
  "contactedIps": [
    "String"
  ],
  "contactedUrls": [
    "String"
  ]
}
```

