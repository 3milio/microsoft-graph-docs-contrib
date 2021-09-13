---
title: "crossTenantAccessPolicyInboundTrust resource type"
description: "Used to define which conditional access claims you want to accept from other organizations via your cross-tenant access policy configuration."
author: "jkdouglas"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# crossTenantAccessPolicyInboundTrust resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Used to define which conditional access claims you want to accept from other Azure AD organizations via your cross-tenant access policy configuration. These can be configured in either your default configuration, partner-specific configuration, or in both configurations.

## Properties

|Property|Type|Description|
|:---|:---|:---|
| isCompliantDeviceAccepted | Boolean | Specifies whether compliant devices from external Azure AD organizations are trusted. |
| isHybridAzureADJoinedDeviceAccepted | Boolean | Specifies whether hybrid Azure AD joined devices from external Azure AD organizations are trusted. |
| isMfaAccepted | Boolean | Specifies whether MFA from external Azure AD organizations is trusted.|

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.crossTenantAccessPolicyInboundTrust"
}
-->

``` json
{
  "@odata.type": "#microsoft.graph.crossTenantAccessPolicyInboundTrust",
  "isMfaAccepted": "Boolean",
  "isCompliantDeviceAccepted": "Boolean",
  "isHybridAzureADJoinedDeviceAccepted": "Boolean"
}
```
