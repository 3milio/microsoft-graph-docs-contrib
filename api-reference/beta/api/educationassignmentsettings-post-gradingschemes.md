---
title: "Create educationGradingScheme"
description: "Create a new educationGradingScheme object."
author: "v-rmanda"
ms.localizationpriority: medium
ms.prod: "education"
doc_type: apiPageType
---

# Create educationGradingScheme

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a new educationGradingScheme object.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "educationassignmentsettings-post-gradingschemes-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/educationassignmentsettings-post-gradingschemes-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PUT /education/classes/{educationClassId}/assignments/{assignmentid}/gradingScheme/$ref
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body

In the request body, supply a JSON representation of the [educationGradingScheme](../resources/educationgradingscheme.md) object.

You can specify the following properties when creating an **educationGradingScheme**.

**TODO: Remove properties that don't apply**
|Property|Type|Description|
|:---|:---|:---|
|displayName|String|The name of the grading scheme.|
|grades|[educationGradingSchemeGrade](../resources/educationgradingschemegrade.md) collection|The grades that make up the scheme.|
|hidePointsDuringGrading|Boolean|Display setting for our UI. Whether teachers can grade with points in addition to letter grades.|



## Response

If successful, this method returns a `201 Created` response code and an [educationGradingScheme](../resources/educationgradingscheme.md) object in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "create_educationgradingscheme_from_"
}
-->
``` http
PUT https://graph.microsoft.com/beta/education/classes/37d99af7-cfc5-4e3b-8566-f7d40e4a2070/assignments/e98aaae1-7c98-4e65-bb62-1994fe410552/gradingScheme/$ref
Content-Type: application/json

{
    "@odata.id": "https://graph.microsoft.com/beta/education/classes/37d99af7-cfc5-4e3b-8566-f7d40e4a2070/assignmentSettings/gradingSchemes/69911dea-bc5c-406a-8743-81d06225a3a1"
}
```


### Response
The following example shows the response.

<!-- {
  "blockType": "response",
  "truncated": true  
}
-->
``` http
HTTP/1.1 204 No Content
```

