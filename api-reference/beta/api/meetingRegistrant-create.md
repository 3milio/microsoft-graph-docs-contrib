---
title: "Enroll meeting registrant"
description: "Enroll a meeting registrant."
author: "mkhribech"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
ms.date: 09/30/2021
doc_type: apiPageType
---

# Enroll meeting registrant

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Enroll a registrant. This operation has two scenarios depending on the value of **allowedRegistrant** of the [registration](../resources/meetingRegistration.md).

`organization`

- Registrants will be required to sign in before registering for the meeting. The **firstName**, **lastName** and **email** must match the information stored in Azure Active Directory.

`everyone`

- Registrants will not be required to sign in and will be considered an anonymous.

In either scenario, the registrant will receive an email notification containing their registration information. See tips in following sections for more details.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type | Permissions (from least to most privileged) |
|:----------------|:--------------------------------------------|
| Delegated (work or school account) | OnlineMeetings.ReadWrite |
| Delegated (personal Microsoft account) | Not Supported. |
| Application | OnlineMeetings.Read.All |

> [!TIP]
>
> Different permissions are required for different value of **allowedRegistrant**.
>
> `organization`
>
>- Registrants will be reqired to sign in. In this scenario, use the registrant's delegated permission to enroll.
>
> `everyone`
>
>- Registrants will not be required to sign in. In this scenario, use application permission to enroll.

## HTTP request

To enroll a registrant in an online meeting with delegated or application permission:
<!-- { "blockType": "ignored" } -->
```http
POST /users/{userId}/onlineMeetings/{id}/registration/registrants
```

- `userId` is the objectID of the meeting organizer.

## Request headers

| Name            | Description               |
| :-------------- | :------------------------ |
| Authorization   | Bearer {token}. Required. |

## Request body

In the request body, supply a JSON representation of non-readonly properties of a [meetingRegistrant](../resources/meetingRegistrant.md) object.

## Response

If successful, this method returns a `200 OK` response code and a partial [meetingRegistrant](../resources/meetingRegistrant.md) object in the response body.

> [!TIP]
>
> Response body will contain different information depending on the value of **allowedRegistrant**.
>
> `organization`
>
> Only **id** and **joinWebUrl** will be returned in the [meetingRegistrant](../resources/meetingRegistrant.md) object. Registrants can use the **id** to cancel their registration or **joinWebUrl** to join the meeting.
>
> `everyone`
>
> An empty [meetingRegistrant](../resources/meetingRegistrant.md) object will be returned. Registrants need to use the links in the email they receive to cancel registration or join the meeting.

## Examples

### Example 1: Enroll a signed-in registrant

This example shows how to enroll a signed-in registrant with the registrant's delegated permission when the meeting has **allowedRegistrant** set to `organization`.

#### Request

<!-- {
  "blockType": "request",
  "name": "add-registratrant-user"
}-->

```http
POST https://graph.microsoft.com/beta/users/16664f75-11dc-4870-bec6-38c1aaa81431/onlineMeetings/MSpkYzE3Njc0Yy04MWQ5LTRhZGItYmZ/registration/registrants
Content-Type: application/json

{
  "firstName": "Foo",
  "lastName": "Bar",
  "email": "foo.bar@contoso.com",
  "customQuestionAnswers": [
    {
      "questionId": "MSM5YjlmM2Q4ZS03ZmVkLTRmN3gwMDIw94MDAyMF9hX3gwMDIwX2RldmU=",
      "value": "No"
    },
    {
      "questionId": "MSM5M2E2OWQ1Ni1jZTc4LTQDAwMjBfZGlkX3gwMDIwX3lvdV94MDAyMF8=",
      "value": "Internet"
    }
  ]
}
```

#### Response

<!-- {
  "blockType": "response",
  "name": "add-registratrant-user",
  "@odata.type": "microsoft.graph.meetingRegistrant"
}-->

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#users('16664f75-11dc-4870-bec6-38c1aaa81431')/onlineMeetings('MSpkYzE3Njc0Yy04MWQ5LTRhZGItYmZ')/registration/registrants/$entity",
  "id": "gWWckDBR6UOI8_yzWCzeNw,6pAAiSU1bkGqzLnbHG_muA,bzLh6uR-5EGYsCvtvIvs6Q,E4jbleVFdE6BDf6ei3YBOA,KvXQzK4zfU-5LQj_ZLWgow,A7_SArco00S-Qr707l0vBA,UFakyZrk1K9vBacExW1muA",
  "registrationDateTime": null,
  "joinWebUrl": "https://teams.microsoft.com/l/meetup-join/19%3ameeting_MmE4Mzg1OTItYjg2Ni00ZmNmLWI5NjMtODNkZDJiMWNlNTVi%40thread.v2/0?context=%7b%22Tid%22%3a%22909c6581-5131-43e9-88f3-fcb3582cde37%22%2c%22Oid%22%3a%22dc17674c-81d9-4adb-bfb2-8f6a442e4622%22%2c%22prid%22%3a%22gWWckDBR6UOI8_yzWCzeNw%2c6pAAiSa1bkGqzLnbHG_muA%2cbzLh6uR-5EGdsCvtvIvs6Q%2cE4jbleVFdE6BDf6ei3YBOA%2cKvXQzK4zfU-5LQj_ZLWgow%2cA7_SArco00S-Qr707l0vBA%2cUFaiyZrk1K9vBacExW1muA%22%2c%22isPublic%22%3afalse%7d",
  "firstName": null,
  "lastName": null,
  "email": null,
  "status": null,
  "customQuestionAnswers": []
}
```

### Example 2: Enroll an anonymous registrant

This example shows how to enroll an anonymous registrant with application permission when the meeting has **allowedRegistrant** set to `everyone`.

#### Request

<!-- {
  "blockType": "request",
  "name": "add-registratrant-app"
}-->

```http
POST https://graph.microsoft.com/beta/users/dc17674c-81d9-4adb-bfb2-8f6a442e4622/onlineMeetings/MSpkYzE3Njc0Yy04MWQ5LTRhZGItYmZ/registration/registrants
Content-Type: application/json

{
  "firstName": "Foo",
  "lastName": "Bar",
  "email": "foo.bar@contoso.com",
  "customQuestionAnswers": [
    {
      "questionId": "MSM5YjlmM2Q4ZS03ZmVkLTRmN3gwMDIw94MDAyMF9hX3gwMDIwX2RldmU=",
      "value": "No"
    },
    {
      "questionId": "MSM5M2E2OWQ1Ni1jZTc4LTQDAwMjBfZGlkX3gwMDIwX3lvdV94MDAyMF8=",
      "value": "Internet"
    }
  ]
}
```

#### Response

<!-- {
  "blockType": "response",
  "name": "add-registratrant-app",
  "@odata.type": "microsoft.graph.meetingRegistrant"
}-->

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#users('16664f75-11dc-4870-bec6-38c1aaa81431')/onlineMeetings('MSpkYzE3Njc0Yy04MWQ5LTRhZGItYmZ')/registration/registrants/$entity",
    "id": "",
    "registrationDateTime": null,
    "joinWebUrl": "",
    "firstName": null,
    "lastName": null,
    "email": null,
    "status": null,
    "customQuestionAnswers": []
}
```
