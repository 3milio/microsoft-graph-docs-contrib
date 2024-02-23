---
title: "Update trainingCampaign"
description: "Update the properties of a trainingCampaign object."
author: "akgraph"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: apiPageType
---

# Update trainingCampaign

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [trainingCampaign](../resources/trainingcampaign.md) object.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "trainingcampaign-update-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/trainingcampaign-update-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /security/attackSimulation/trainingCampaigns/{trainingCampaignId}
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
|Content-Type|application/json. Required.|

## Request body

[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]

|Property|Type|Description|
|:---|:---|:---|
|createdBy|[emailIdentity](../resources/emailidentity.md)|Identity of the user who created the training campaign. Optional.|
|createdDateTime|DateTimeOffset|Date and time of creation of the training campaign. Optional.|
|description|String|Description of the training campaign. Optional.|
|displayName|String|Display name of the training campaign. Required.|
|endUserNotificationSetting|[endUserNotificationSetting](../resources/endusernotificationsetting.md)|Details about the end user notification setting. Required.|
|excludedAccountTarget|[accountTargetContent](../resources/accounttargetcontent.md)|Users excluded from the training campaign. Optional.|
|includedAccountTarget|[accountTargetContent](../resources/accounttargetcontent.md)|Users targeted in the training campaign. Required.|
|lastModifiedDateTime|DateTimeOffset|Identity of the user who most recently modified the training campaign. Optional.|
|trainingSetting|[trainingSetting](../resources/trainingsetting.md)|Details about the training settings for a training campaign. Required.|
|campaignSchedule|[campaignSchedule](../resources/campaignschedule.md)|Details about the schedule and current status for a training campaign. Required.|

## Response

If successful, this method returns a `202 Accepted` response code and a tracking header named `location` in the response.

## Example

The following example shows how to update the status of the training campaign. In this case a scheduled training campaign is cancelled

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "update_trainingcampaign"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/security/attackSimulation/trainingCampaigns/{trainingCampaignId}
Content-Type: application/json

{
    "displayName": "Graph Training Campaign",
    "description": "Graph Training Campaign Description",
    "createdBy": {
        "email": "john@contoso.com"
    },
    "lastModifiedBy": {
        "email": "john@contoso.com"
    },
    "includedAccountTarget": {
        "type": "addressBook",
        "accountTargetEmails": [
            "john@contoso.com"
        ]
    },
    "endUserNotificationSetting": {
        "notificationPreference": "microsoft",
        "settingType": "trainingSelected",
        "trainingReminder": {
            "deliveryFrequency": "weekly",
            "endUserNotification@odata.bind": "https://graph.microsoft.com/beta/security/attackSimulation/endUserNotifications('fe521249-9901-4584-a987-026a9980c58e')",
            "defaultLanguage": "en"
        },
        "trainingAssignment": {
            "endUserNotification@odata.bind": "https://graph.microsoft.com/beta/security/attackSimulation/endUserNotifications('36fb4dc1-7c37-4b96-9096-12e6d6014fae')",
            "defaultLanguage": "en"
        }
    },
    "trainingSetting": {
        "settingType": "microsoftCustom",
        "trainingAssignmentMappings": [
            {
                "assignedTo": [
                    "allUsers"
                ],
                "training@odata.bind": "https://graph.microsoft.com/beta/security/attackSimulation/trainings('40454905-dc26-4f36-b854-3042a5362cb3')"
            },
            {
                "assignedTo": [
                    "allUsers"
                ],
                "training@odata.bind": "https://graph.microsoft.com/beta/security/attackSimulation/trainings('ea70ae06-3859-4818-be9d-270ee81d80a4')"
            },
            {
                "assignedTo": [
                    "allUsers"
                ],
                "training@odata.bind": "https://graph.microsoft.com/beta/security/attackSimulation/trainings('d733d88c-1b5a-48e3-a588-9910e41ac21d')"
            }
        ]
    },
    "campaignSchedule": {
        "launchDateTime": "2024-02-15T07:59:44Z",
        "completionDateTime": "2024-02-18T07:59:44Z",
        "status": "Cancelled"
    }
}
```

### Response

The following example shows the response.

<!-- {
  "blockType": "response",
  "truncated": true
}
-->

```http
HTTP/1.1 202 Accepted 
```

