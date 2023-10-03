--- 
title: "communicationsApplicationInstanceIdentity resource type"
description: "Represents the identity of an instance of an application."
author: "rahulva-msft"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
doc_type: resourcePageType
---

# communicationsApplicationInstanceIdentity resource type

Namespace: microsoft.graph

Represents the identity of an instance of an application. An application instance is a resource account created by [New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance). For example, you might have multiple call queue application instances that are all backed by the same Azure Active Directory application. These application instances are represented in Azure Active Directory by disabled user accounts.

Inherits from [identity](identity.md).

## Properties

| Property                       | Type                        | Description                                                                                                                                       |
| :----------------------------- | :---------------------------| :-------------------------------------------------------------------------------------------------------------------------------------------------|
| id | String | The object ID of the resource account user in Azure Active Directory. Inherited from **identity**. |
| displayName | String | The display name associated with the resource account. Inherited from **identity**. |
| tenantId | String | The tenant ID of the application. |
| hidden | Boolean | `True` if the participant shouldn't be shown in other participants' rosters. |

## JSON representation

Here's a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.communicationsApplicationInstanceIdentity",
  "optionalProperties": [
    "displayName",
    "tenantId",
    "hidden"
  ],
} -->
```json
{
  "displayName": "String",
  "hidden": "Boolean",
  "id": "String",
  "tenantId": "String"
}
```
