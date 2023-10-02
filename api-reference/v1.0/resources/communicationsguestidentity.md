--- 
title: "communicationsGuestIdentity resource type"
description: "Represents the identity of a participant who joined the communication without authentication."
author: "rahulva-msft"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
doc_type: resourcePageType
---

# communicationsGuestIdentity resource type

Namespace: microsoft.graph

Represents the identity of a participant who joined the communication without authentication.

Inherits from [identity](identity.md).

## Properties

| Property                       | Type                        | Description                                                                                                                                       |
| :----------------------------- | :---------------------------| :-------------------------------------------------------------------------------------------------------------------------------------------------|
| id | String | Inherited from **identity**. A unique guid identifying the guest user. |
| displayName | String | Inherited from **identity**. The display name associated with the guest user. |

## JSON representation

Here's a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.communicationsGuestIdentity",
  "optionalProperties": [
    "displayName"
  ],
} -->
```json
{
  "id": "String",
  "displayName": "String"
}
```
