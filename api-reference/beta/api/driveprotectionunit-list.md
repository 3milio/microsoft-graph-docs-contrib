---
title: "List driveProtectionUnits"
description: "List all Drive Protection Units."
author: tushar20, manikantsinghms
ms.author: tkanaujia, maniksingh
ms.localizationpriority: medium
ms.subservice: "m365-backup-storage"
doc_type: apiPageType
---
# List driveProtectionUnits

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

List all Drive Protection Units. Read the properties and relationships of a [driveProtectionUnit](../resources/driveprotectionunit.md).

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "driveprotectionunits-list-permissions"
}
-->
<!--[!INCLUDE [permissions-table](../includes/permissions/driveprotectionunits-list-permissions.md)]-->
|Permission type|Least privileged permission|Higher privileged permissions|
|:---|:---|:---|
|Delegated (work or school account)|BackupRestore-Configuration.Read.All|BackupRestore-Configuration.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|Not supported.|
|Application|BackupRestore-Configuration.Read.All|BackupRestore-Configuration.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /solutions/backupRestore/driveProtectionUnits
GET /solutions/backupRestore/oneDriveForBusinessProtectionPolicies/{oneDriveForBusinessProtectionPolicyId}/driveProtectionUnits
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

If successful, this method returns a `200 OK` response code and a [driveProtectionUnit](../resources/driveprotectionunit.md) in the response body.

## Examples

### Example 1

List all driveProtectionUnits in a oneDriveForBusinessProtectionPolicy.

#### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_driveprotectionunit"
}
-->
``` http
GET /solutions/backupRestore/oneDriveForBusinessProtectionPolicies/845457dc-4bb2-4815-bef3-8628ebd1952e/driveProtectionUnits
```

#### Response

The following example shows the response.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.driveProtectionUnit"
}
-->
``` http
HTTP/1.1 200 OK

{
  "@odata.nextLink": "/solutions/backupRestore/oneDriveForBusinessProtectionPolicies/845457dc-4bb2-4815-bef3-8628ebd1952e/driveProtectionUnits?$skiptoken=M2UyZDAwMDAwMDMxMzkzYTMyNjQ2MTM0NjMzMjM5NjYzNjY0MzczMDM0MzE2NTYzNjEzNzMwNjIzNjMzMzg2MjM0MzM2NDM0MzUzNDMzMzc0MDc0Njg3MjY1NjE2NDJlNzYzMjAxZThmYjY4M2Y3ODAxMDAwMDg4NjA5ODdhNzgwMTAwMDB8MTYxNjk2NDUwOTgzMg%3d%3d",
  "values": [
    {
      "@odata.type": "#microsoft.graph.driveProtectionUnit",
      "id": "2b014d8c-71fe-4d00-a01a-31850bc5b32c",
      "policyId": "9fec8e78-bce4-4aaf-ab1b-5451cc387264",
      "userId": "384974e2-72cd-48de-a6e8-6985d7c5db90",
      "userDisplayName": "Emily Braun", // Newly Added
      "userEmail": "emilyb@contoso.com", // Newly Added
      "status": "protectRequested",
      "createdBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "createdDateTime": "2015-06-19T12-01-03.45Z",
      "lastModifiedBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "lastModifiedDateTime": "2015-06-19T12-01-03.45Z",
      "error": null
    },
    {
      "@odata.type": "#microsoft.graph.driveProtectionUnit",
      "id": "57014d8c-71fe-4d00-a01a-31850bc5b32c",
      "policyId": "9fec8e78-bce4-4aaf-ab1b-5451cc387264",
      "userId": "184d9337-d8f0-456e-92cd-00a3abdd2093",
      "userDisplayName": "Alex Wilber", // Newly Added
      "userEmail": "alexw@contoso.com", // Newly Added
      "status": "protectRequested",
      "createdBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "createdDateTime": "2015-06-19T12-01-03.45Z",
      "lastModifiedBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "lastModifiedDateTime": "2015-06-19T12-01-03.45Z",
      "error": null
    },
    {
      "@odata.type": "#microsoft.graph.driveProtectionUnit",
      "id": "17014d8c-71fe-4d00-a01a-31850bc5b32c",
      "policyId": "9fec8e78-bce4-4aaf-ab1b-5451cc387264",
      "userId": "344d9337-d8f0-456e-92cd-00a3abdd2093",
      "userDisplayName": "Shaun Wong", // Newly Added
      "userEmail": "shaunw@contoso.com", // Newly Added
      "status": "protectRequested",
      "createdBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "createdDateTime": "2015-06-19T12-01-03.45Z",
      "lastModifiedBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "lastModifiedDateTime": "2015-06-19T12-01-03.45Z",
      "error": null
    },
    {
      "@odata.type": "#microsoft.graph.driveProtectionUnit",
      "id": "8f014d8c-71fe-4d00-a01a-31850bc5b32c",
      "policyId": "9fec8e78-bce4-4aaf-ab1b-5451cc387264",
      "userId": "781d9337-d8f0-456e-92cd-00a3abdd2093",
      "userDisplayName": "Janet Green", // Newly Added
      "userEmail": "janetg@contoso.com", // Newly Added
      "status": "protectRequested",
      "createdBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "createdDateTime": "2015-06-19T12-01-03.45Z",
      "lastModifiedBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "lastModifiedDateTime": "2015-06-19T12-01-03.45Z",
      "error": null
    },
    {
      "@odata.type": "#microsoft.graph.driveProtectionUnit",
      "id": "9b014d8c-71fe-4d00-a01a-31850bc5b32c",
      "policyId": "9fec8e78-bce4-4aaf-ab1b-5451cc387264",
      "userId": "2d1d9337-d8f0-456e-92cd-00a3abdd2093",
      "userDisplayName": "Eddie Brock ", // Newly Added
      "userEmail": "eddyb@contoso.com", // Newly Added
      "status": "protectRequested",
      "createdBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "createdDateTime": "2015-06-19T12-01-03.45Z",
      "lastModifiedBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "lastModifiedDateTime": "2015-06-19T12-01-03.45Z",
      "error": null
    }
  ]
}
```

### Example 2

List all driveProtectionUnits in a tenant.

#### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_all_driveprotectionunit"
}
-->
``` http
GET /solutions/backupRestore/driveProtectionUnits
```

#### Response

The following example shows the response.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.driveProtectionUnit"
}
-->
``` http
HTTP/1.1 200 OK

{
  "@odata.nextLink": "/solutions/backupRestore/driveProtectionUnits?$skiptoken=M2UyZDAwMDAwMDMxMzkzYTMyNjQ2MTM0NjMzMjM5NjYzNjY0MzczMDM0MzE2NTYzNjEzNzMwNjIzNjMzMzg2MjM0MzM2NDM0MzUzNDMzMzc0MDc0Njg3MjY1NjE2NDJlNzYzMjAxZThmYjY4M2Y3ODAxMDAwMDg4NjA5ODdhNzgwMTAwMDB8MTYxNjk2NDUwOTgzMg%3d%3d",
  "values": [
    {
      "@odata.type": "#microsoft.graph.driveProtectionUnit",
      "id": "2b014d8c-71fe-4d00-a01a-31850bc5b32c",
      "userId": "384974e2-72cd-48de-a6e8-6985d7c5db90
      "userDisplayName": "Emily Braun", // Newly Added
      "userEmail": "emilyb@contoso.com", // Newly Added
      "status": "unprotected",
      "createdBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "createdDateTime": "2015-06-19T12-01-03.45Z",
      "lastModifiedBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "lastModifiedDateTime": "2015-06-19T12-01-03.45Z",
      "error": null
    },
    {
      "@odata.type": "#microsoft.graph.driveProtectionUnit",
      "id": "8f014d8c-71fe-4d00-a01a-31850bc5b32c",
      "policyId": "9fec8e78-bce4-4aaf-ab1b-5451cc387264",
      "userId": "781d9337-d8f0-456e-92cd-00a3abdd2093",
      "userDisplayName": "Alex Wilber", // Newly Added
      "userEmail": "alexw@contoso.com", // Newly Added
      "status": "protectRequested",
      "createdBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "createdDateTime": "2015-06-19T12-01-03.45Z",
      "lastModifiedBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "lastModifiedDateTime": "2015-06-19T12-01-03.45Z",
      "error": null
    },
    {
      "@odata.type": "#microsoft.graph.driveProtectionUnit",
      "id": "9b014d8c-71fe-4d00-a01a-31850bc5b32c",
      "policyId": "9fec8e78-bce4-4aaf-ab1b-5451cc387264",
      "userId": "2d1d9337-d8f0-456e-92cd-00a3abdd2093",
      "userDisplayName": "Shaun Wong", // Newly Added
      "userEmail": "shaunw@contoso.com", // Newly Added
      "status": "unprotected",
      "createdBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "createdDateTime": "2015-06-19T12-01-03.45Z",
      "lastModifiedBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "lastModifiedDateTime": "2015-06-19T12-01-03.45Z",
      "error": null
    },
    {
      "@odata.type": "#microsoft.graph.driveProtectionUnit",
      "id": "9b014d8c-71fe-4d00-a01a-31850bc5b32c",
      "policyId": "9fec8e78-bce4-4aaf-ab1b-5451cc387264",
      "userId": "2e1d9337-d8f0-456e-92cd-00a3abdd2093",
      "userDisplayName": "Janet Green", // Newly Added
      "userEmail": "janetg@contoso.com", // Newly Added
      "status": "protected",
      "createdBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "createdDateTime": "2015-06-19T12-01-03.45Z",
      "lastModifiedBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "lastModifiedDateTime": "2015-06-19T12-01-03.45Z",
      "error": null
    },
    {
      "@odata.type": "#microsoft.graph.driveProtectionUnit",
      "id": "9b014d8c-71fe-4d00-a01a-31850bc5b32c",
      "userId": "2w1d9337-d8f0-456e-92cd-00a3abdd2093",
      "userDisplayName": "Eddie Brock ", // Newly Added
      "userEmail": "eddyb@contoso.com", // Newly Added
      "status": "unprotected",
      "createdBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "createdDateTime": "2015-06-19T12-01-03.45Z",
      "lastModifiedBy": {
        "application": {
          "id": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "displayName": "Microsoft Enhanced Restore"
        },
        "user": {
          "email": "abc@contoso.com",
          "id": "845457dc-4bb2-4815-bef3-8628ebd1952e",
          "displayName": "ABC"
        }
      },
      "lastModifiedDateTime": "2015-06-19T12-01-03.45Z",
      "error": null
    }
  ]
}
```
