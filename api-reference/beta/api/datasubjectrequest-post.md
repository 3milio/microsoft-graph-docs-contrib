---
title: "Create dataSubjectRequest"
description: "Create a new dataSubjectRequest object."
author: "skadam-msft"
localization_priority: Normal
ms.prod: "compliance"
doc_type: apiPageType
---

# Create dataSubjectRequest
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a new [dataSubjectRequest](../resources/datasubjectrequest.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|DataSubject.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /compliance/dataSubjectRequests
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [dataSubjectRequest](../resources/datasubjectrequest.md) object.

The following table shows the properties that are required when you create the [dataSubjectRequest](../resources/datasubjectrequest.md).

|Property|Type|Description|
|:---|:---|:---|
|dataSubject|[microsoft.graph.dataSubject](../resources/datasubject.md)|Contains the properties for data subject for the request.|
|dataSubjectType|dataSubjectType|Data subject type. Possible values are: `customer`, `currentEmployee`, `formerEmployee`, `prospectiveEmployee`, `student`, `teacher`, `faculty`, `other`, `unknownFutureValue`.|
|description|String|Description for the request.|
|displayName|String|Name of the request.|
|internalDueDateTime|DateTimeOffset|Internal due date that is used for tracking the request completion.|
|regulations|String collection|One or more regulations for the request.|
|type|dataSubjectRequestType|Type of the request. Possible values are: `export`, `delete`, `access`, `tagForAction`, `unknownFutureValue`.|


## Response

If successful, this method returns a `201 Created` response code and a [dataSubjectRequest](../resources/datasubjectrequest.md) object in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "create_datasubjectrequest_from_"
}
-->
``` http
POST https://graph.microsoft.com/beta/compliance/dataSubjectRequests
Content-Type: application/json
Content-length: 849

{
    "type": "microsoft.graph.dataSubjectRequestType",
    "dataSubjectType": "microsoft.graph.dataSubjectType",
    "regulations": ["String"],
    "displayName": "String",
    "description": "String",
    "internalDueDateTime": "String (timestamp)",
    "dataSubject": {
        "firstName": "String",
        "lastName": "String",
        "email": "String",
        "residency": "String",
        "phoneNumber": "String",
        "SSN": "String"
    }
}
```


### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.dataSubjectRequest"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
    "type": "microsoft.graph.dataSubjectRequestType",
    "dataSubjectType": "microsoft.graph.dataSubjectType",
    "regulations": [
        "String"
    ],
    "displayName": "String",
    "description": "String",
    "status": "active",
    "internalDueDateTime": "String",
    "lastModifiedDateTime": "String",
    "id": "String",
    "createdDateTime": "String",
    "stages": [
        {
            "stage": "contentRetrieval",
            "status": "notStarted",
            "error": 
            {
                "@odata.type": "microsoft.graph.publicError"
            }
        },
        {
            "stage": "contentReview",
            "status": "notStarted",
            "error": 
            {
                "@odata.type": "microsoft.graph.publicError"
            }
        },
        {
            "stage": "generateReport",
            "status": "notStarted",
            "error": 
            {
                "@odata.type": "microsoft.graph.publicError"
            }
        },
        {
            "stage": "caseResolved",
            "status": "notStarted",
            "error": 
            {
                "@odata.type": "microsoft.graph.publicError"
            }
        }
    ],
    "createdBy": {
        "@odata.type": "microsoft.graph.identitySet"
    },
    "lastModifiedBy": {
        "@odata.type": "microsoft.graph.identitySet"
    },
    "dataSubject": {
        "firstName": "String",
        "lastName": "String",
        "email": "String",
        "residency": "String",
        "phoneNumber": "String",
        "SSN": "String"
    },
    "team": {
        "id": "String (identifier)",
        "webUrl": "String"
    }
}
```

