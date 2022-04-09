---
title: "contentLabel resource type"
description: "Describes the contentLabel object that defines Microsoft Information Protection metadata on an object."
author: "tommoser"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: resourcePageType
---

# contentLabel resource type

Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Describes the **contentLabel** object that defines Microsoft Information Protection metadata on an object. **contentLabel** is returned by the [extractContentLabel](../api/security-sensitivitylabel-extractcontentlabel.md) API resolve the **sensitivityLabel** that is currently applied to a file.

## Properties
| Property         | Type           | Description                                                                                                                                                                                                                                 |
| :--------------- | :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| assignmentMethod | String         | Describes whether the label was applied by a process or automation (`standard`) or a person (`privileged`). A `standard` assignment cannot override `privileged`. To override, set `auto`.                                                  |
| creationDateTime | DateTimeOffset | The Timestamp resprenting when the `contentLabel` was created. The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. |


## Relationships
| Relationship     | Type                                                          | Description                                                   |
| :--------------- | :------------------------------------------------------------ | :------------------------------------------------------------ |
| sensitivityLabel | [sensitivityLabel](../resources/security-sensitivitylabel.md) | The **sensitivityLabel** referred to by the content metadata. |

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.security.contentLabel"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.security.contentLabel",
  "assignmentMethod": "String",
  "creationDateTime": "String (timestamp)"
}
```
