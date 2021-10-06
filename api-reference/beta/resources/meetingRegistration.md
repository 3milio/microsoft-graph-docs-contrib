---
title: "meetingRegistration resource type"
description: "Contains information about online meeting registration."
author: "mkhribech"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
ms.date: 09/30/2021
doc_type: resourcePageType
---

# meetingRegistration resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Registration of an online meeting. One applicable scenario is [Teams webinar](https://support.microsoft.com/en-us/office/get-started-with-teams-webinars-42f3f874-22dc-4289-b53f-bbc1a69013e3).

## Methods

| Method | Return Type | Description |
| :----- | :---------- | :---------- |
|[Create](../api/meetingRegistration-create.md) | [meetingRegistration](meetingRegistration.md) | Create and enable registration for an online meeting. |
|[Get](../api/meetingRegistration-get.md) | [meetingRegistration](meetingRegistration.md) | Retrieve the details of a meeting registration. |
|[Update](../api/meetingRegistration-update.md) | [meetingRegistration](meetingRegistration.md) | Update the details of a meeting registration. |
|[Delete](../api/meetingRegistration-delete.md) | [meetingRegistration](meetingRegistration.md) | Disable and delete registration for an online meeting. |

## Properties

| Property | Type | Description |
| :------- | :--- | :---------- |
| allowedRegistrant | [meetingAudience](#meetingaudience-values) | Specify who can register for the meeting. |
| description | String | The description of the meeting. |
| endDateTime | DateTime | The meeting end time in UTC. |
| registrationPageViewCount | Int32 | Indicate how mant times the registration page has been visited. Read-only. |
| registrationPageWebUrl | String | The URL of the registration page. Read-only. |
| speakers | [meetingSpeaker](meetingSpeaker.md) collection | The speakers information of the meeting. |
| startDateTime | DateTime | The meeting start time in UTC. |
| subject | String | The subject of the meeting. |

### meetingAudience values

| Value              | Description |
| ------------------ | ----------- |
| everyone           | Everyone can register for the meeting. |
| organization       | Everyone in organizer’s organization can register for the meeting. |
| unknownFutureValue | Unknown future value. |

## Relationships

| Relationship | Type | Description |
| ------------ | ---- | ----------- |
| customQuestions | [meetingRegistrationQuestion](meetingRegistrationQuestion.md) collection| The custom registration questions. Navigation property. |
| registrants | [meetingRegistrant](meetingRegistrant.md) collection | Registrants of the online meeting. Navigation property. |

## JSON representation

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.meetingRegistration"
}-->

```json
{
  "allowedRegistrant": { "@odata.type": "microsoft.graph.meetingAudience" },
  "description": "String",
  "endDateTime": "String (timestamp)",
  "registrationPageViewCount": "Int32",
  "registrationPageWebUrl": "String",
  "speakers": [{ "@odata.type": "microsoft.graph.meetingSpeaker" }],
  "startDateTime": "String (timestamp)",
  "subject": "String",

  "customQuestions": [{ "@odata.type": "microsoft.graph.meetingRegistrationQuestion" }],
  "registrants": [{ "@odata.type": "microsoft.graph.meetingRegistrant" }]
}
```
