---
title: "Update multiTenantOrganizationPartnerConfigurationTemplate"
description: "Update the inbound and outbound partner configuration settings of the multi-tenant organization template."
author: "rolyon"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# Update multiTenantOrganizationPartnerConfigurationTemplate
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the inbound and outbound partner configuration settings of the multi-tenant organization template.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|Policy.ReadWrite.CrossTenantAccess|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Policy.ReadWrite.CrossTenantAccess|

The signed-in user must also be assigned the following minimum [directory role](/azure/active-directory/roles/permissions-reference):

* Security Administrator

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /policies/crossTenantAccessPolicy/templates/multiTenantOrganizationPartnerConfiguration
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body

[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]

|Property|Type|Description|
|:---|:---|:---|
|inboundTrust|[crossTenantAccessPolicyInboundTrust](../resources/crosstenantaccesspolicyinboundtrust.md)|Determines the partner-specific configuration for trusting other Conditional Access claims from external Azure Active Directory (Azure AD) organizations. Optional.|
|b2bCollaborationOutbound|[crossTenantAccessPolicyB2BSetting](../resources/crosstenantaccesspolicyb2bsetting.md)|Defines your partner-specific configuration for users in your organization going outbound to access resources in another organization via Azure AD B2B collaboration. Optional.|
|b2bCollaborationInbound|[crossTenantAccessPolicyB2BSetting](../resources/crosstenantaccesspolicyb2bsetting.md)|Defines your partner-specific configuration for users from other organizations accessing your resources via Azure AD B2B collaboration. Optional.|
|b2bDirectConnectOutbound|[crossTenantAccessPolicyB2BSetting](../resources/crosstenantaccesspolicyb2bsetting.md)|Defines your partner-specific configuration for users in your organization going outbound to access resources in another organization via Azure AD B2B direct connect. Optional.|
|b2bDirectConnectInbound|[crossTenantAccessPolicyB2BSetting](../resources/crosstenantaccesspolicyb2bsetting.md)|Defines your partner-specific configuration for users from other organizations accessing your resources via Azure AD B2B direct connect. Optional.|
|automaticUserConsentSettings|[inboundOutboundPolicyConfiguration](../resources/inboundoutboundpolicyconfiguration.md)|Determines the partner-specific configuration for automatic user consent settings. Optional.|



## Response

If successful, this method returns a `204 No Content` response code.

## Examples

The following example configures the inbound trust settings to accept MFA, compliant, and Hybrid Azure AD Joined devices from the partner tenant. It also configures automatic redemption on behalf of your users and accepting admin consent for the users of the partner. For more information, see [crossTenantAccessPolicyConfigurationPartner resource type](../resources/crosstenantaccesspolicyconfigurationpartner.md).

### Request

<!-- {
  "blockType": "request",
  "name": "update_multitenantorganizationpartnerconfigurationtemplate"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/policies/crossTenantAccessPolicy/templates/multiTenantOrganizationPartnerConfiguration
Content-Type: application/json

{
    "inboundTrust":  {
        "isMfaAccepted": true,
        "isCompliantDeviceAccepted": true,
        "isHybridAzureADJoinedDeviceAccepted": true
    },
    "automaticUserConsentSettings": {
        "inboundAllowed": true,
        "outboundAllowed": true
    }
}

```

### Response

<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```

