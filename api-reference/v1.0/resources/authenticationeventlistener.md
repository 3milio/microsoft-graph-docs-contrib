---
title: "authenticationEventListener resource type"
description: "Listener for taking action on events in the authentication process."
author: "soneff"
ms.localizationpriority: medium
ms.subservice: "entra-sign-in"
doc_type: resourcePageType
---

# authenticationEventListener resource type

Namespace: microsoft.graph

To customize the authentication process, listeners can be registered which specify that for some event, on some conditions, some custom logic can be invoked. This is an abstract type from which the following types are derived.

- [onInteractiveAuthFlowStartListener resource type](../resources/oninteractiveauthflowstartlistener.md) resource type
- [onAuthenticationMethodLoadStartListener resource type](../resources/onauthenticationmethodloadstartlistener.md) resource type
- [onAttributeCollectionListener resource type](../resources/onattributecollectionlistener.md) resource type
- [onUserCreateStartListener resource type](../resources/onusercreatestartlistener.md) resource type
- [onTokenIssuanceStartListener resource type](../resources/ontokenissuancestartlistener.md) resource type

> [!NOTE]
>
> You can have a maximum of 250 event listeners.

Inherits from [entity](../resources/entity.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List authenticationEventListener objects](../api/identitycontainer-list-authenticationeventlisteners.md)|[authenticationEventListener](../resources/authenticationeventlistener.md) collection|Get a list of the [authenticationEventListener](../resources/authenticationeventlistener.md) objects and their properties.|
|[Create authenticationEventListener](../api/identitycontainer-post-authenticationeventlisteners.md)|[authenticationEventListener](../resources/authenticationeventlistener.md)|Create a new [authenticationEventListener](../resources/authenticationeventlistener.md) object.|
|[Get authenticationEventListener](../api/authenticationeventlistener-get.md)|[authenticationEventListener](../resources/authenticationeventlistener.md)|Read the properties and relationships of an [authenticationEventListener](../resources/authenticationeventlistener.md) object.|
|[Update authenticationEventListener](../api/authenticationeventlistener-update.md)|[authenticationEventListener](../resources/authenticationeventlistener.md)|Update the properties of an [authenticationEventListener](../resources/authenticationeventlistener.md) object.|
|[Delete authenticationEventListener](../api/authenticationeventlistener-delete.md)|None|Delete an [authenticationEventListener](../resources/authenticationeventlistener.md) object.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|conditions|[authenticationConditions](../resources/authenticationconditions.md)|The conditions on which this authenticationEventListener should trigger.|
|id|String|Identifier for this authenticationEventListener. Inherited from [entity](../resources/entity.md).|
|authenticationEventsFlowId|String|Indicates the authenticationEventListener is associated with an [authenticationEventsFlow](../resources/authenticationeventsflow.md). Read-only.

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.authenticationEventListener",
  "baseType": "microsoft.graph.entity",
  "openType": true
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.authenticationEventListener",
  "id": "String (identifier)",
  "conditions": {
    "@odata.type": "microsoft.graph.authenticationConditions"
  },
  "authenticationEventsFlowId": "String"
}
```

