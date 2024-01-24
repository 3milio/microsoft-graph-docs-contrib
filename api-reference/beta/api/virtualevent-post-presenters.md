---
title: "Create virtualEventPresenter"
description: "Create a new virtualEventPresenter object."
author: "awang119"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
doc_type: apiPageType
---

# Create virtualEventPresenter

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a new virtualEventPresenter object to a virtual event. Currently the supported virtual event type is: [virtualEventTownhall](../resources/virtualeventtownhall.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "virtualevent-post-presenters-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/virtualevent-post-presenters-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /solutions/virtualEvents/townhalls/{townhallId}/presenters
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [virtualEventPresenter](../resources/virtualeventpresenter.md) object.

You can specify the following properties when creating a **virtualEventPresenter**.

|Property|Type|Description|
|:---|:---|:---|
|identity|[communicationsUserIdentity](../resources/communicationsuseridentity.md)|Identity information of the presenter.|

## Response

If successful, this method returns a `201 Created` response code and a [virtualEventPresenter](../resources/virtualeventpresenter.md) object in the response body.

## Examples

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "create_virtualeventpresenter_from_"
}
-->
``` http
POST https://graph.microsoft.com/beta/solutions/virtualEvents/townhalls/{virtualEventId}/presenters
Content-Type: application/json

{
  "identity": {
    "id": ""
  }
}
```


### Response
The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.virtualEventPresenter"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.virtualEventPresenter",
  "id": "831affc2-4c8a-9929-50e7-02964563b6e4",
  "identity": {
    "@odata.type": "microsoft.graph.communicationsUserIdentity"
  },
  "email": "String",
  "presenterDetails": {
    "@odata.type": "microsoft.graph.virtualEventPresenterDetails"
  },
  "profilePhoto": "Stream"
}
```

