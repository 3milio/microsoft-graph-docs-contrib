---
title: "What's new in Microsoft Graph"
description: "Find out what's new in Microsoft Graph APIs, SDKs, documentation, and other resources."
author: "lauragra"
ms.localizationpriority: high
---

# What's new in Microsoft Graph

Microsoft Graph provides a unified programmability model that you can use to access data in Microsoft 365, Windows, and Enterprise Mobility + Security. This topic provides information about what's new in Microsoft Graph APIs, documentation, SDKs, and more.

For more detailed API-level updates, see the [Microsoft Graph API changelog](https://developer.microsoft.com/graph/changelog/).

For details about previous updates to Microsoft Graph, see [Microsoft Graph what's new history](whats-new-earlier.md). 

> [!IMPORTANT]
> Features in _preview_ status are subject to change without notice, and might not be promoted to generally available (GA) status. Do not use preview features in production apps.

## February 2024: New and generally available

Microsoft Graph Toolkit v4 is now available. For details about changes in the latest release, see [Upgrade to the latest version of Microsoft Graph Toolkit](/graph/toolkit/upgrade).

## February 2024: New in preview only

### Teamwork and communications | Calls and online meetings

Microsoft Teams custom meeting templates allow you to specify values for many of the meeting options available to meeting organizers. Use the **meetingTemplateId** property on [onlineMeeting](/graph/api/resources/onlinemeeting?view=graph-rest-beta&preserve-view=true) to create an online meeting with a meeting template.

### Teamwork and communications | Shift management

Added the ability to [get shifts](/graph/api/team-getshifts?view=graph-rest-beta&preserve-view=true) and [get time offs](/graph/api/team-gettimesoff?view=graph-rest-beta&preserve-view=true) across all teams that a user is a direct member of.

### Identity and access | Directory management

Updated the descriptions of the **model** and **manufacturer** properties in the [device](/graph/api/resources/device?view=graph-rest-beta&preserve-view=true) resource to clarify their read-only status, replacing the outdated descriptions related to Project Rome sign-ins.

## January 2024: New and generally available

### Device and app management | Cloud PC

The [virtualEndpoint](/graph/api/resources/virtualendpoint) resource is generally available, laying the foundation for future Cloud PC updates to the `v1.0` path.

### Education

Use the **webURL** property to get the deep link URL of an [educationSubmission](/graph/api/resources/educationsubmission).

### Identity and access | Governance

Through the **attributes** property of the [accessPackageResource resource type](/graph/api/resources/accesspackageresource), you can now view details of the attributes that are collected from the requestor and sent to the resource application.

### Reports | Partner billing reports

The new partner billing API in Microsoft Graph offers Microsoft direct partners a faster, more efficient way to export their high-volume billed and unbilled Azure usage data. Partners can quickly create export operations, monitor their status, and retrieve manifests using the following APIs:

- [billedUsage: export](/graph/api/partners-billing-billedusage-export)
- [unbilledUsage: export](/graph/api/partners-billing-unbilledusage-export)
- [Get operation](/graph/api/partners-billing-operation-get)
- [Get manifest](/graph/api/partners-billing-manifest-get)

### Teamwork and communications | Calls and online meetings
Communications servers can publish [deltaParticipants](/graph/api/resources/deltaParticipants) notifications for the creation, update, or deletion of a [participant](/graph/api/resources/participant) in a [call](/graph/api/resources/call). For more information, see [JSON payload examples](/graph/api/application-post-calls#notification---roster) of notifications with delta roster disabled or enabled.

## January 2024: New in preview only

### Applications

For Azure AD Connect cloud sync scenarios, you can now specify organizational units and groups that are in scope of a [synchronizationRule](/graph/api/resources/synchronization-synchronizationrule?view=graph-rest-beta&preserve-view=true). For details, see the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=d9c34227-2a99-49e5-ac9c-e8444f685ce5).

### Device and app management | Cloud PC

- Use the **errorMessage** property in the [cloudPcPartnerAgentInstallResult](/graph/api/resources/cloudpcpartneragentinstallresult) to access a detailed error message for instances where the installation of a partner agent on a Cloud PC fails.
- [Get the device recommendation reports for Cloud PCs](/graph/api/cloudpcreports-getcloudpcrecommendationreports?view=graph-rest-beta&preserve-view=true), such as the usage category report.
- [Get the remote action status reports](/graph/api/cloudpcreports-getactionstatusreports?view=graph-rest-beta&preserve-view=true), including data such as the Cloud PC ID, Cloud PC device display name, action taken, and action state.

The following properties are deprecated:

- **recommendedSku** property on [cloudPcGalleryImage](/graph/api/resources/cloudpcgalleryimage?view=graph-rest-beta&preserve-view=true).
- **offer** and **offerDisplayName** properties on [cloudPcGalleryImage](/graph/api/resources/cloudpcgalleryimage?view=graph-rest-beta&preserve-view=true) in favor of the **offerName** property.
- **publisher** property on [cloudPcGalleryImage](/graph/api/resources/cloudpcgalleryimage?view=graph-rest-beta&preserve-view=true) in favor of the **publisherName** property.
- **sku** and **skuDisplayName** properties on [cloudPcGalleryImage](/graph/api/resources/cloudpcgalleryimage?view=graph-rest-beta&preserve-view=true) in favor of the **skuName** property.
- **statusDetails** property on [cloudPcDeviceImage](/graph/api/resources/cloudpcdeviceimage?view=graph-rest-beta&preserve-view=true) in favor of the  **errorCode** property, to identify why an upload failed. The **errorCode** property is of type [cloudPcDeviceImageErrorCode](/graph/api/resources/cloudpcdeviceimage#cloudpcdeviceimageerrorcode-values?view=graph-rest-beta&preserve-view=true).
- **id** property on [cloudPcSourceDeviceImage](/graph/api/resources/cloudpcsourcedeviceimage?view=graph-rest-beta&preserve-view=true) in favor of the **resourceId** property, to get the fully qualified unique identifier of the source image resource in Azure.
- **windowsSettings** property on [cloudPcProvisioningPolicy](/graph/api/resources/cloudpcprovisioningpolicy?view=graph-rest-beta&preserve-view=true) in favor of the **windowsSetting** property.
- **type** property on [cloudPcDomainJoinConfiguration](/graph/api/resources/cloudpcdomainjoinconfiguration?view=graph-rest-beta&preserve-view=true) in favor of the **domainJoinType** property.
- **type** property on [microsoftManagedDesktop](/graph/api/resources/microsoftmanageddesktop?view=graph-rest-beta&preserve-view=true) in favor of the **managedType** property.
- **frequencyInHours** property on [cloudPcRestorePointSetting](/graph/api/resources/cloudpcrestorepointsetting?view=graph-rest-beta&preserve-view=true) in favor of the **frequencyType** property.

### Identity and access | Governance

- You can [refresh an access package resource request](/graph/api/accesspackageresource-refresh?view=graph-rest-beta&preserve-view=true) to fetch the latest information for an access package resource from the origin system.
- Added the **assignmentRequests** relationship to the **entitlementManagement** resource type and updated the API endpoints for the managing [access package assignment requests](/graph/api/resources/accesspackageassignmentrequest?view=graph-rest-beta&preserve-view=true) from `/identityGovernance/entitlementManagement/accessPackageAssignmentRequests/` which will be retired soon to `/identityGovernance/entitlementManagement/assignmentRequests/`. Inspect the API paths in your code and update to the new request paths for the Create, Delete, Get, and List operations.

### Identity and access | Identity and sign-in

Added the [x509CertificateCombinationConfiguration resource type](/graph/api/resources/x509certificatecombinationconfiguration) as a new derived type for [authenticationCombinationConfiguration resource type](/graph/api/resources/authenticationcombinationconfiguration) which helps you set restrictions on specific types, modes, or versions of an authentication method used in an [authentication strength](/graph/api/resources/authenticationstrengths-overview). Previously, you could only restrict the allowed FIDO2 key types. The **x509CertificateCombinationConfiguration** type allows you to configure the list of allowed values for specific certificate properties.

### Reports | Partner billing reports

The new partner billing API in Microsoft Graph offers Microsoft direct partners a faster, more efficient way to export their high-volume billed and unbilled Azure usage data. Partners can quickly create export operations, monitor their status, and retrieve manifests using the following APIs:

- [billedUsage: export](/graph/api/partners-billing-billedusage-export?view=graph-rest-beta&preserve-view=true)
- [unbilledUsage: export](/graph/api/partners-billing-unbilledusage-export?view=graph-rest-beta&preserve-view=true)
- [Get operation](/graph/api/partners-billing-operation-get?view=graph-rest-beta&preserve-view=true)
- [Get manifest](/graph/api/partners-billing-manifest-get?view=graph-rest-beta&preserve-view=true)

### Users

Added the [deletePasswordSingleSignOnCredentials](/graph/api/user-deletepasswordsinglesignoncredentials?view=graph-rest-beta&preserve-view=true) and [getPasswordSingleSignOnCredentials](/graph/api/user-getpasswordsinglesignoncredentials?view=graph-rest-beta&preserve-view=true) methods to the [user](/graph/api/resources/user?view=graph-rest-beta&preserve-view=true) resource for deleting and retrieving the password-based single sign-on credentials for a user to a given service principal.


## Contribute to Microsoft Graph

Are there scenarios you'd like Microsoft Graph to support? 

- Suggest and vote for new features by using the [Microsoft Graph Feedback Portal](https://aka.ms/graphfeedback). Some new features originate as popular requests from the developer community. The Microsoft Graph team regularly evaluates customer needs and releases new features to the beta (`https://graph.microsoft.com/beta`) and v1.0 (`https://graph.microsoft.com/v1.0`) endpoints.

- [Join](https://aka.ms/m365-dev-call) the weekly Microsoft 365 platform community call and become an active member of the Microsoft Graph community.

- [Join](https://ux.microsoft.com/Panel/M365Devs?utm_source=graphDocs) our research panel to provide your input on our developer experiences.

## Related content
- [Microsoft Graph developer blog](https://devblogs.microsoft.com/microsoft365dev/category/microsoft-graph/)
- [Microsoft Graph API changelog](https://developer.microsoft.com/graph/changelog/).
- [Microsoft Graph what's new history](whats-new-earlier.md).
