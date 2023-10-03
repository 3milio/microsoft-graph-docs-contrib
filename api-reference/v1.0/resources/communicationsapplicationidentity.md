--- 
title: "communicationsApplicationIdentity resource type"
description: "Represents the identity of an application used for communications such as calling."
author: "rahulva-msft"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
doc_type: resourcePageType
---

# communicationsApplicationIdentity resource type

Namespace: microsoft.graph

Represents the identity of an application used for communications such as calling. These should be registered as enterprise applications in [Azure Active Directory](/azure/active-directory/).

Inherits from [identity](identity.md).

## Properties

| Property                       | Type                        | Description                               |
| :----------------------------- | :---------------------------| :-----------------------------------------|
| applicationType | String | First-party Microsoft application that presents this **identity**. |
| displayName | String | The display name associated with the application. Inherited from **identity**. |
| hidden | Boolean | `True` if the participant shouldn't be shown in other participants' rosters. |
| id | String | The client ID of the application from Azure Active Directory. Inherited from **identity**. |

## JSON representation

Here's a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.communicationsApplicationIdentity",
  "optionalProperties": [
    "displayName",
    "applicationType",
    "hidden"
  ],
} -->
```json
{
  "applicationType": "String",
  "displayName": "String",
  "hidden": "Boolean",
  "id": "String"
}
```
