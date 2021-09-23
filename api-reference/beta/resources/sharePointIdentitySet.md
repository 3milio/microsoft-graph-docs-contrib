---
author: tushar20
ms.date: 09/09/2021
title: sharePointIdentitySet
disclaimer: [!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]
ms.localizationpriority: medium
description: "The sharePointIdentitySet resource is a keyed collection of sharePointIdentity and identity resources."
ms.prod: ""
doc_type: resourcePageType
---
# sharePointIdentitySet resource type

The **sharePointIdentitySet** resource is a keyed collection of [sharePointIdentity](sharePointIdentity.md) resources. It extends from the **identitySet** resource to provide capability to expose SharePoint specific information to the user.

It is used to represent a set of identities associated with various events for an item, such as _created by_ or _last modified by_.

## JSON representation

Here is a JSON representation of the resource.

<!-- { "blockType": "resource", "@odata.type": "microsoft.graph.sharePointIdentitySet",
       "optionalProperties": ["user", "application", "group", "device", "siteUser", "siteGroup"],
       "openType": true } -->

```json
{
  /** inherited from IdentitySet **/
  "application": {"@odata.type": "microsoft.graph.identity"},
  "device": {"@odata.type": "microsoft.graph.identity"},
  "user": {"@odata.type": "microsoft.graph.identity"},
  
  "group": {"@odata.type": "microsoft.graph.identity"},
  "siteUser": {"@odata.type": "microsoft.graph.sharePointIdentity"},
  "siteGroup":{"@odata.type": "microsoft.graph.sharePointIdentity"}
}
```

## Properties

| Property    | Type                   | Description                                                 |
|:------------|:-----------------------|:----------------------------------------------------------- |
| application | [Identity][]           | The application associated with this action. Optional       |
| device      | [Identity][]           | The device associated with this action. Optional            |
| group       | [Identity][]           | The group associated with this action. Optional             |
| siteUser    | [SharePointIdentity][] | The SharePoint User associated with this action. Optional   |
| siteGroup   | [SharePointIdentity][] | The SharePoint Group associated with this action. Optional  |
| user        | [Identity][]           | The user associated with this action. Optional              |

## Remarks

See [DriveItem][] for usage of **sharePointIdentitySet** resources.

[DriveItem]: driveItem.md
[Identity]: identity.md
[SharePointIdentity]: sharePointIdentity.md

<!-- {
  "type": "#page.annotation",
  "description": "SharePointIdentity set is a collection of identities/sharePointIdentities",
  "section": "documentation",
  "tocPath": "Resources/SharePointIdentitySet"
} -->
