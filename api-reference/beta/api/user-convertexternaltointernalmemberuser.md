---
title: "user: convertExternalToInternalMemberUser"
description: "Convert an external user to an internal member."
author: "yyuank"
ms.localizationpriority: medium
ms.prod: "users"
doc_type: apiPageType
---

# user: convertExternalToInternalMemberUser

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Convert an externally authenticated user into an internal user. The user is able to sign into the host tenant as an internal user and access resources as a member. <!--For more information about how the two user types differ, see [What are the default user permissions in Microsoft Entra ID?](/entra/fundamentals/users-default-permissions?context=graph%2Fcontext).-->

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "user-convertexternaltointernalmemberuser-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/user-convertexternaltointernalmemberuser-permissions.md)]

In delegated scenarios, the calling user must have at least the *User Administrator* [Microsoft Entra roles](/entra/identity/role-based-access-control/permissions-reference?toc=%2Fgraph%2Ftoc.json).

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /users/{usersId}/convertExternalToInternalMemberUser
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body

In the request body, supply a JSON representation of the parameters.

The following table lists the parameters that are required when you call this action.

|Parameter|Type|Description|
|:---|:---|:---|
|mail|String|Optional. |
|passwordProfile|[passwordProfile](../resources/passwordprofile.md)|Required for users whose authentication is managed in the cloud.|
|userPrincipalName|String|Required for cloud users to change the **userPrincipalName**. Not required for on-premises synced users, as their **userPrincipalName** is managed on-premises.|


## Response

If successful, this method returns a `200 OK` response code and a [user](../resources/user.md) object with the default properties, including the **convertedToInternalUserDateTime** property in the response. 

## Examples

### Example 1: Convert a cloud user and require them to reset their password on next sign in

#### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "userthis.convertexternaltointernalmemberuser-cloudonly"
}
-->
```http
POST https://graph.microsoft.com/beta/users/0b8cc234-ef87-4015-9785-cbb42000d41c/convertExternalToInternalMemberUser
Content-type: application/json

{
    "userPrincipalName": "AdeleVance@contoso.com",
    "passwordProfile": {
        "password": "Zdi087#2jhkahf",
        "forceChangePasswordNextSignIn": "true"
    }
}
```

#### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.user"
}
-->
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#users/$entity",
    "id": "0b8cc234-ef87-4015-9785-cbb42000d41c",
    "accountEnabled": true,
    "displayName": "Adele Vance",
    "mail": "AdeleV@woodgrove.com",
    "mailNickname": "AdeleV_woodgrove.com#EXT#",
    "otherMails": [
        "AdeleV@woodgrove.com"
    ],
    "proxyAddresses": [
        "SMTP:AdeleV@woodgrove.com",
        "smtp:AdeleVance@contoso.com",
        "smtp:AdeleV_woodgrove.com#EXT#@contoso.com"
    ],
    "userPrincipalName": "AdeleVance@contoso.com",
    "convertedToInternalUserDateTime": "2024-02-05T20:16:37.5012924Z",
    "externalUserState": null,
    "externalUserStateChangeDateTime": "2019-10-31T18:10:01Z",
    "userType": "Member",
    "identities": [
        {
            "signInType": "userPrincipalName",
            "issuer": "contoso.com",
            "issuerAssignedId": "AdeleVance@contoso.com"
        }
    ],
    "passwordProfile": {
        "password": null,
        "forceChangePasswordNextSignIn": true,
        "forceChangePasswordNextSignInWithMfa": false
    }
}
```

### Example 2: Convert a cloud user, change their mail address, and require password reset on next sign in

#### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "userthis.convertexternaltointernalmemberuser-cloudonly-with-mail"
}
-->
```http
POST https://graph.microsoft.com/beta/users/0b8cc234-ef87-4015-9785-cbb42000d41c/convertExternalToInternalMemberUser
Content-type: application/json

{
    "userPrincipalName": "AdeleVance@contoso.com",
    "passwordProfile": {
        "password": "Zdi087#2jhkahf",
        "forceChangePasswordNextSignIn": "true"
    },
    "mail": "AdeleV@contoso.com"
}
```

#### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.user"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#users/$entity",
    "id": "0b8cc234-ef87-4015-9785-cbb42000d41c",
    "displayName": "Adele Vance",
    "mail": "AdeleV@contoso.com",
    "userPrincipalName": "AdeleVance@contoso.com"
}
```

### Example 3: Convert external User to internal for a user synchronized from on-premises AD

#### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "userthis.convertexternaltointernalmemberuser-synceduser"
}
-->
```http
POST https://graph.microsoft.com/beta/users/0b8cc234-ef87-4015-9785-cbb42000d41c/convertExternalToInternalMemberUser
```

#### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.user"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "id": "0b8cc234-ef87-4015-9785-cbb42000d41c",
    "displayName" : "user1Name",
    "userPrincipalName" : "newUpn@contoso.com",
    "convertedToInternalUserDateTime" : "2024-12-31T23:59:59.9999999"
}
```


