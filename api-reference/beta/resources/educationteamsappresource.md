---
title: "educationTeamsAppResource resource type"
description: "Represents a Microsoft Teams application to submit to an assignment."
author: "adarshgh"
ms.localizationpriority: medium
ms.prod: "education"
doc_type: resourcePageType
---

# educationTeamsAppResource resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a Microsoft Teams application to submit to an [assignment](educationassignment.md). This resource allows users to use those resources through the governing application; for example, YouTube or FlipGrid.

Inherites from [educationResource](educationresource.md).

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|displayName|string|The display name of the resource.|
|appId|string|Teams App ID of the application|
|appIconWebUrl|string|URL that points to the app's icon|
|teamsEmbeddedContentUrl|string|URL for the app resource that will be opened by Teams|
|webUrl|string|URL for the app resource that can be opened in the browser|
|createdBy|String|The display name of the user that created this resource. Inherited from **educationResource**.|
|createdDateTime|DateTimeOffset|Date time the resoruce was added. Inherited from **educationResource**.|
|lastModifiedBy|[identitySet](identityset.md)|The last user to modify the resource. Inherited from **educationResource**.|
|lastModifiedDateTime|DateTimeOffset|The date and time when the resource was last modified. The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Inherited from **educationResource**.|


## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.educationTeamsAppResource"
}-->

```json
{
  "displayName": "String",
  "appId": "Unique String",
  "appIconWebUrl": "String URL",
  "teamsEmbeddedContentUrl": "String URL",
  "webUrl": "String URL",
  "createdBy": {"@odata.type": "microsoft.graph.identitySet"},
  "createdDateTime": "String (timestamp)",
  "lastModifiedBy": {"@odata.type": "microsoft.graph.identitySet"},
  "lastModifiedDateTime": "String (timestamp)"  
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "educationExcelResource resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


