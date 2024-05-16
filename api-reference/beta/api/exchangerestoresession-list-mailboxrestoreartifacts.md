---
title: "List mailboxRestoreArtifact"
description: "Get a list of the mailboxRestoreArtifact and their properties for an exchangeRestoreSession"
author: "tushar20, manikantsinghms"
ms.localizationpriority: medium
ms.subservice: "m365-backup-storage"
doc_type: apiPageType
---

# List mailboxRestoreArtifact

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

List all the [mailboxRestoreArtifact](../resources/mailboxrestoreartifact.md) for an [exchangeRestoreSession](../resources/exchangerestoresession.md) for the tenant.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "exchangerestoresession-list-mailboxrestoreartifacts-permissions"
}
-->
<!-- [!INCLUDE [permissions-table](../includes/permissions/exchangerestoresession-list-mailboxrestoreartifacts-permissions.md)] -->

|Permission type|Least privileged permission|Higher privileged permissions|
|:---|:---|:---|
|Delegated (work or school account)|BackupRestore-Restore.Read.All|BackupRestore-Restore.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|Not supported.|
|Application|BackupRestore-Restore.Read.All|BackupRestore-Restore.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /solutions/backupRestore/exchangeRestoreSessions/{exchangeRestoreSessionId}/mailboxRestoreArtifacts
```

## Optional query parameters

This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [mailboxRestoreArtifact](../resources/mailboxrestoreartifact.md) in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "mailboxrestoreartifact_list"
}
-->
``` http
GET https://graph.microsoft.com/beta/solutions/backupRestore/exchangeRestoreSessions/{exchangeRestoreSessionId}/mailboxRestoreArtifacts
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.backupRestore.mailboxRestoreArtifact)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.backupRestore.mailboxRestoreArtifact",
      "id": "90511b62-94fa-a267-c848-fa9d58af8af2",
      "destinationType": "String",
      "status": "String",
      "startDateTime": "String (timestamp)",
      "completionDateTime": "String (timestamp)",
      "error": {
        "@odata.type": "microsoft.graph.publicError"
      },
      "restoredFolderId": "String",
      "restoredFolderName": "String"
    }
  ]
}
```

