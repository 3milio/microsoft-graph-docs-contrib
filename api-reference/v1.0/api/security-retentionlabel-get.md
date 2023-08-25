---
title: "Get retentionLabel"
description: "Read the properties and relationships of a retentionLabel object."
author: "sseth"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: apiPageType
---

# Get retentionLabel
Namespace: microsoft.graph.security

Read the properties and relationships of a [retentionLabel](../resources/security-retentionlabel.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|RecordsManagement.Read.All, RecordsManagement.ReadWrite.All|
|Delegated (personal Microsoft account)|Not Supported.|
|Application|Not supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /security/labels/retentionLabels/{retentionLabelId}
GET /security/triggers/retentionEvents/{retentionEventId}/labels/{retentionLabelId}
```

## Optional query parameters
This method supports the expand OData query parameters to help customize the response.  For example, to retrieve the **retentionEventType** property, you can use the `expand` parameter:`$expand=retentionEventType` or `$expand=descriptors`. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [microsoft.graph.security.retentionLabel](../resources/security-retentionlabel.md) object in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "get_retentionlabel"
}
-->
``` http
GET  https://graph.microsoft.com/v1.0/security/labels/retentionLabels/{retentionLabelId}
```

### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.security.retentionLabel"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.security.retentionLabel",
    "id": "64a99fb4-07be-0481-8746-44c15c0eef1f",
      "displayName": "Retention Schedule 10004",
      "behaviorDuringRetentionPeriod": "retain",
      "actionAfterRetentionPeriod": "relabel",
      "retentionTrigger": "dateCreated",
      "retentionDuration": {
        "@odata.type": "microsoft.graph.security.retentionDurationInDays",
        "days": "730"
      },
      "isInUse": "true",
      "descriptionForAdmins": "creation based retention label for schedule 10004",
      "descriptionForUsers": "retains for 2 years then relabeled",
      "createdBy": {
        "user": {
          "id": "efee1b77-fb3b-4f65-99d6-274c11914d12",
          "displayName": "Admin"
        }
      },
      "createdDateTime": "2017-11-27T02:10:12Z",
      "lastModifiedBy": {
        "user": {
          "id": "9563a605-e827-4324-a5a9-09efddff1e90",
          "displayName": "Records Manager"
        }
      },
      "lastModifiedDateTime": "2020-08-28T22:13:09Z",
      "labelToBeApplied": "Retention schedule 10005",
      "defaultRecordBehavior": "startLocked"
  }
}
```

