---
title: "Get workbookDocumentTask"
description: "Get the properties and relationships of workbookDocumentTask object."
author: "VictorZheng-qizheng"
ms.localizationpriority: medium
ms.prod: "excel"
doc_type: apiPageType
---

# Get workbookDocumentTask

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get the properties and relationships of [workbookDocumentTask](../resources/workbookdocumenttask.md) object.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Files.ReadWrite    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Not supported. |

## HTTP request

<!-- { "blockType": "ignored" } -->
```http
GET /me/drive/items/{id}/workbook/worksheets/{id}/tasks/{id}
GET /me/drive/items/{id}/workbook/comments/{id}/task
```
## Optional query parameters

This method supports the [OData query parameters](/graph/query-parameters) to help customize the response.

## Request headers

| Name      |Description|
|:----------|:----------|
| Authorization  | Bearer {token}. Required. |
| Workbook-Session-Id  | Workbook session ID that determines if changes are persisted or not. Optional.|

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and the requested [workbookDocumentTask](../resources/workbookdocumenttask.md) object in the response body.

## Example

### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "get_workbookDocumentTask"
}-->
```msgraph-interactive
GET https://graph.microsoft.com/beta/drive/root/workbook/worksheets/D5667D8C-B814-4748-B942-9C41BCC9BBB1/tasks/47B4663E-612F-4E06-B2E6-E8EBE819CBB6
```

### Response

The following is an example of the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.workbookDocumentTask",
  "isCollection": false
} -->
```http
HTTP/1.1 200 OK

{
  "@odata.type": "microsoft.graph.documentTask",
  "createdBy": {
    "@odata.type": "microsoft.graph.emailIdentity",
    "id": "6463a5ce-2119-4198-9f2a-628761df4a62",
    "displayName": "Mike Smith",
    "email": "mikesmith@contoso.com"
  },
  "createdDateTime": "2015-03-25T18:36:49.2407981Z",
  "title": "new title-value",
  "id": "97A21473-8339-4BF0-BCB6-F55E4909FFB8",
  "assignees": [
    {
      "@odata.type": "microsoft.graph.emailIdentity",
      "id": "1e9955d2-6acd-45bf-86d3-b546fdc795eb",
      "displayName": "Joe Doe",
      "email": "joedoe@contoso.com"
    }
  ]
}
```
