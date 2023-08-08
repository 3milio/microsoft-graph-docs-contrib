---
title: "Get virtualEventRegistration"
description: "Read the properties and relationships of a virtualEventRegistration object."
author: "awang119"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
doc_type: apiPageType
---

# Get virtualEventRegistration

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of a [virtualEventRegistration](../resources/virtualEventRegistration.md) object.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|VirtualEvent.Read|
|Delegated (personal Microsoft account)|Not supported.|
|Application|VirtualEvent.Read.All|

> [!NOTE]
>
> To use application permissions for this API, tenant administrators must create an [application access policy](/graph/cloud-communication-online-meeting-application-access-policy) and assign it to a user.The authorized application will access registration records from virtual events created by that specific user.

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /solutions/virtualEvents/webinars/{webinarId}/registrations/{registrationId}
```

## Optional query parameters

This method does not support the OData query parameters. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [virtualEventRegistration](../resources/virtualEventRegistration.md) object in the response body.

## Examples

### Request

The following is an example of a request.
# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_virtualEventRegistration"
}
-->
``` http
GET https://graph.microsoft.com/beta/solutions/virtualEvents/webinars/f4b39f1c-520e-4e75-805a-4b0f2016a0c6@a1a56d21-a8a6-4a6b-97f8-ced53d30f143/registrations/127962bb-84e1-7b62-fd98-1c9d39def7b6
```

### Response

The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.virtualEventRegistration"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.virtualEventRegistration",
  "id": "127962bb-84e1-7b62-fd98-1c9d39def7b6",
  "userId": "String",
  "firstName": "Emilee",
  "lastName": "Pham",
  "email": "EmileeMPham@contoso.com",
  "status": "registered",
  "registrationDateTime": "2023-03-07T22:04:17",
  "cancelationDateTime": null,
  "registrationQuestionAnswers": [
    {
      "questionId": "95320781-96b3-4b8f-8cf8-e6561d23447a",
      "displayName": null,
      "value": null,
      "booleanValue": null,
      "multiChoiceValues": [
        "Seattle"
      ]
    },
    {
      "questionId": "4577afdb-8bee-4219-b482-04b52c6b855c",
      "displayName": null,
      "value": null,
      "booleanValue": true,
      "multiChoiceValues": []
    },
    {
      "questionId": "80fefcf1-caf7-4cd3-b8d7-159e17c47f20",
      "displayName": null,
      "value": null,
      "booleanValue": null,
      "multiChoiceValues": [
        "Cancun",
        "Hoboken",
        "Beijing"
      ]
    }
  ]
}
```
