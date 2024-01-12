---
title: "channel: unarchive"
description: "Restore an archived channel in a team. Unarchiving restores the ability for users to send messages and edit the channel."
ms.localizationpriority: medium
author: "sumitgupta3"
ms.prod: "microsoft-teams"
doc_type: apiPageType
---

# Channel: unarchive

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Restore an archived [channel](../resources/channel.md). Unarchiving restores the ability for users to send messages and edit the channel. Channels are archived via the [archive](channel-archive.md) API.

Unarchiving is an asynchronous operation; a channel is unarchived when the asynchronous unarchive operation completes successfully, which might occur after this method responds.

> **Note**: An archived channel that belongs to an archived team cannot be unarchived. Unarchive the team before you unarchive the channel; otherwise, an error will occur.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | ChannelSettings.ReadWrite.All | 
|Delegated (personal Microsoft account) | Not supported.    |
|Application | ChannelSettings.ReadWrite.All | 

[!INCLUDE [teamwork-permissions-note](../../../includes/teamwork-permissions-note.md)]

> **Note**: This API supports admin permissions. Global admins and Microsoft Teams service admins can access teams that they are not a member of.

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /teams/{team-id}/channels/{channel-id}/unarchive
POST /groups/{team-id}/team/channels/{channel-id}/unarchive
```

## Request headers

| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer {token}. Required.  |

## Request body

Don't supply a request body for this method.

## Response

If unarchiving is started successfully, this method returns a `202 Accepted` response code. The response contains a `Location` header, which contains the location of the [teamsAsyncOperation](../resources/teamsasyncoperation.md) that was created to handle unarchiving of the channel of the team. Check the status of the unarchiving operation by making a GET request to this location.

## Example

### Example 1: Unarchive a channel
The following is an example of a request to unarchive a channel.

#### Request

<!-- {
  "blockType": "request",
  "name": "unarchive_channel"
}-->
```http
POST https://graph.microsoft.com/beta/teams/{team-id}/channels/{channel-id}/unarchive
```

#### Response

The following example shows the response.
<!-- {
  "blockType": "response",
  "name": "unarchive_channel"
}-->
```http
HTTP/1.1 202 Accepted
Location: /teams/{team-id}/operations/{operation-id}
Content-Type: text/plain
Content-Length: 0
```

### Example 2: Unarchive a channel when the team is archived team

The following is an example of a request when **Team is archived**.

#### Request

<!-- {
  "blockType": "request",
  "name": "archive_channel"
}-->
```http
POST https://graph.microsoft.com/beta/teams/{team-id}/channels/{channel-id}/unarchive
```

#### Response
The following is an example of the `400` error response.

<!-- {
  "blockType": "response",
  "name": "archive_channel"
}-->
```http
http/1.1 400 Bad Request
Content-Type: application/json
Content-Length: 193

{
    "error": {
        "code": "BadRequest",
        "message": "Team has to be active, for channel to be archived or unarchived: {channel-id}",
        "innerError": {
            "message": "Team has to be active, for channel to be archived or unarchived: {channel-id}",
            "code": "Unknown",
            "innerError": {},
            "date": "2023-12-11T04:26:35",
            "request-id": "8f897345980-f6f3-49dd-83a8-a3064eeecdf8",
            "client-request-id": "50a0er33-4567-3f6c-01bf-04d144fc8bbe"
        }
    }
}

```
<!-- uuid: 9a9bb83f-6f35-4426-bb04-73ca43ad6cc8
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Unarchive channel",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
