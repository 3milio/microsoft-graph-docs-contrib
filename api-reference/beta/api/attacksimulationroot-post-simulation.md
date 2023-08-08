---
title: "Create simulation"
description: "Create an attack simulation campaign for a tenant."
author: "stuartcl"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: apiPageType
---

# Create simulation

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create an attack simulation campaign for a tenant.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | AttackSimulation.ReadWrite.All              |
| Delegated (personal Microsoft account) | Not supported.                              |
| Application                            | AttackSimulation.ReadWrite.All              |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
```http
POST /security/attackSimulation/simulations
```

## Request headers

|Header         |Value                    |
|---------------|-------------------------|
|Authorization  |Bearer {token}. Required.|
|Content-Type   |application/json         |

## Request body

In the request body, supply a JSON representation of a [simulation](../resources/simulation.md) object.

The following table shows the properties that are required when you create the simulation.

| Property | Type        | Description |
|:-------------|:------------|:------------|
|attackTechnique|[simulationAttackTechnique](../resources/simulation.md#simulationattacktechnique-values)|The social engineering technique used in the attack simulation and training campaign. Supports `$filter` and `$orderby`. Possible values are: `unknown`, `credentialHarvesting`, `attachmentMalware`, `driveByUrl`, `linkInAttachment`, `linkToMalwareFile`, `unknownFutureValue`, `oAuthConsentGrant`. Note that you must use the `Prefer: include-unknown-enum-members` request header to get the following values from this [evolvable enum](/graph/best-practices-concept#handling-future-members-in-evolvable-enumerations): `oAuthConsentGrant`. For more information on the types of social engineering attack techniques, see [simulations](/microsoft-365/security/office-365-security/attack-simulation-training-get-started?view=o365-worldwide&preserve-view=true#simulations).|
|attackType|[simulationAttackType](../resources/simulation.md#simulationattacktype-values)|Attack type of the attack simulation and training campaign. Supports `$filter` and `$orderby`. Possible values are: `unknown`, `social`, `cloud`, `endpoint`, `unknownFutureValue`.|
|createdBy|[emailIdentity](../resources/emailidentity.md)|Identity of the user who created the attack simulation and training campaign.|
|displayName|String|Display name of the attack simulation and training campaign. Supports `$filter` and `$orderby`.|
|durationInDays|Int32|Simulation duration in days. Optional.|
|endUserNotificationSetting|[endUserNotificationSetting](../resources/endusernotificationsetting.md)|End user notification setting detail.|
|includedAccountTarget|[accountTargetContent](../resources/accounttargetcontent.md)|Users targeted in the simulation.|
|landingPage|[landingPage](../resources/landingpage.md)|The landing page associated with the attack simulation and training campaign.|
|lastModifiedBy|[emailIdentity](../resources/emailidentity.md)|Identity of the user who most recently modified the attack simulation and training campaign.|
|launchDateTime|DateTimeOffset|Date and time of the launch/start of the attack simulation and training campaign. Supports `$filter` and `$orderby`.|
|loginPage|[loginPage](../resources/loginpage.md)|The login page associated with the attack simulation and training campaign.|
|oAuthConsentAppDetail|[oAuthConsentAppDetail](../resources/oauthconsentappdetail.md)|Details required for the `oAuthConsentGrant` technique.|
|payload|[payload](../resources/payload.md)|The payload associated with the attack simulation and training campaign.|
|status|[simulationStatus](../resources/simulation.md#simulationstatus-values)|Status of the attack simulation and training campaign. Supports `$filter` and `$orderby`. Possible values are: `unknown`, `draft`, `running`, `scheduled`, `succeeded`, `failed`, `cancelled`, `excluded`, `unknownFutureValue`.|
|trainingSetting|[trainingSetting](../resources/trainingsetting.md)|Training setting detail.|

## Response

If successful, this method returns a `202 Accepted` response code and a tracking header named `location` in the response.

## Examples

### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "create_simulations"
}
-->

```http
POST https://graph.microsoft.com/beta/security/attackSimulation/simulations
Content-type: application/json

{
  "displayName": "Graph Simulation",
  "payload@odata.bind": "https://graph.microsoft.com/beta/security/attacksimulation/payloads/12345678-9abc-def0-123456789a",
  "loginPage@odata.bind": "https://graph.microsoft.com/beta/security/attacksimulation/loginPages/1w345678-9abc-def0-123456789a",
  "landingPage@odata.bind": "https://graph.microsoft.com/beta/security/attacksimulation/landingPages/1c345678-9abc-def0-123456789a",
  "durationInDays": "3",
  "attackTechnique": "credentialHarvesting",
  "status": "scheduled",
  "includedAccountTarget": {
    "@odata.type": "#microsoft.graph.addressBookAccountTargetContent",
    "type": "addressBook",
    "accountTargetEmails": [
      "john@contoso.com"
    ]
  },
  "trainingSetting": {
    "settingType": "noTraining"
  },
  "endUserNotificationSetting": {
    "notificationPreference": "microsoft",
    "settingType": "noTraining",
    "positiveReinforcement": {
      "deliveryPreference": "deliverAfterCampaignEnd",
      "endUserNotification": "https://graph.microsoft.com/beta/security/attacksimulation/endUserNotifications/1ewer3678-9abc-def0-123456789a",
      "defaultLanguage": "en"
    },
    "simulationNotification": {
      "targettedUserType": "compromised",
      "endUserNotification@odata.bind": "https://graph.microsoft.com/beta/security/attacksimulation/endUserNotifications/12wer3678-9abc-def0-123456789a",
      "defaultLanguage": "en"
    }
  }
}
```

### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true
}
-->

```http
HTTP/1.1 202 Accepted 
```
