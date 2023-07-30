---
title: "connectivityConfigurationLink resource type"
description: "Represents the link or association between a branch, and its corresponding connectivity configuration."
author: "Moti-ba"
ms.localizationpriority: medium
ms.prod: identity-and-access
doc_type: resourcePageType
---

# connectivityConfigurationLink resource type

Namespace: microsoft.graph.networkaccess

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents the link or association between a branch, and its corresponding connectivity configuration.

## Methods
No methods available.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|displayName|String|Specifies the name of the link.|
|id|String|A unique identifier for each link.|
|localConfigurations|[microsoft.graph.networkaccess.localConnectivityConfiguration](../resources/networkaccess-localconnectivityconfiguration.md) collection|Specifies configuration of Microsoft’s end of the tunnel(s) for a device link.|
|peerConfiguration|[microsoft.graph.networkaccess.peerConnectivityConfiguration](../resources/networkaccess-peerconnectivityconfiguration.md)|Specifies configuration of customer’s end of the tunnel(s) for a device link.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.networkaccess.connectivityConfigurationLink",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.networkaccess.connectivityConfigurationLink",
  "id": "String (identifier)",
  "displayName": "String",
  "localConfigurations": [
    {
      "@odata.type": "microsoft.graph.networkaccess.localConnectivityConfiguration"
    }
  ],
  "peerConfiguration": {
    "@odata.type": "microsoft.graph.networkaccess.peerConnectivityConfiguration"
  }
}
```

