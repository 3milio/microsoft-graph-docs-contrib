---
title: "Archive channel"
description: "Archive a channel in a team. "
author: "sumitgupta3"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: apiPageType
---

# Archive channel

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Archive a [channel](../resources/channel.md). When a channel is archived, users can’t send new messages or like existing messages on it. Also, users can't edit the channel's name, edit other settings, nor make almost any other changes to the channel.

You can delete an archived channel, or add and remove members from it. If you archive a team, its channels are archived for you.

Archiving is asynchronous; a channel is archived after the asynchronous archiving operation completes successfully, which might occur after the response returns.

A channel without an owner, or that belongs to a [group](../resources/group.md) that has no owner, can't be archived.

To restore a channel from its archived state, use the [unarchive](channel-unarchive.md) method. A channel can’t be archived or unarchived if its team is archived.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | ChannelSettings.ReadWrite.All |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | ChannelSettings.ReadWrite.All |

> **Note**: This API supports admin permissions. Global admins and Microsoft Teams service admins can access teams that they are not a member of.

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /teams/{team-id}/channels/{channel-id}/archive
POST /groups/{team-id}/team/channels/{channel-id}/archive
```
## Request headers
| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer {token}. Required.  |

## Request body
In the request, you can optionally include the `shouldSetSpoSiteReadOnlyForMembers` parameter in a JSON body, as follows.
```JSON
{
    "shouldSetSpoSiteReadOnlyForMembers": true
}
```
This optional parameter defines whether to set permissions for channel members to read-only on the SharePoint Online site associated with the team. Setting it to false or omitting the body altogether results in this step being skipped.

## Response

If archiving is started successfully, this method returns a `202 Accepted` response code. The response contains a `Location` header, which contains the location of the [teamsAsyncOperation](../resources/teamsasyncoperation.md) that was created to handle archiving of the channel in a team. Check the status of the archiving operation by making a GET request to this location.

## Examples

### Example 1:
The following is an example of a request for archiving a channel.

#### Request

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "archive_channel"
}-->
```http
POST https://graph.microsoft.com/beta/teams/5crrrtrd5-e41c-4f18-ab8awfd-f36ca7dd11231de/channels/5ceebed5-o45u-334o-sve3-f36ca7dd31de/archive
```

---

#### Response
The following is an example of a response.
<!-- {
  "blockType": "response",
  "name": "archive_channel"
}-->
```http
HTTP/1.1 202 Accepted
Location: /teams/5crrrtrd5-e41c-4f18-ab8awfd-f36ca7dd11231de/operations/5cr4f18ab8a238965287f36
Content-Type: text/plain
Content-Length: 0
```


### Example 2:
The following is an example of a request when **Team is archived**.

#### Request


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "archive_channel"
}-->
```http
POST https://graph.microsoft.com/beta/teams/5crrrtrd5-e41c-4f18-ab8awfd-f36ca7dd11231de/channels/5ceebed5-o45u-334o-sve3-f36ca7dd31de/archive
```

---

#### Response
The following example shows the `400` error response.
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
        "message": "Team has to be active, for channel to be archived or unarchived: 5ceebed5-o45u-334o-sve3-f36ca7dd31de",
        "innerError": {
            "message": "Team has to be active, for channel to be archived or unarchived: 5ceebed5-o45u-334o-sve3-f36ca7dd31de",
            "code": "Unknown",
            "innerError": {},
            "date": "2023-12-11T04:26:35",
            "request-id": "8f897345980-f6f3-49dd-83a8-a3064eeecdf8",
            "client-request-id": "50a0er33-4567-3f6c-01bf-04d144fc8bbe"
        }
    }
}

```

<!-- uuid: e848414b-4669-4484-ac36-1504c58a3fb8
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Archive Channel",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
