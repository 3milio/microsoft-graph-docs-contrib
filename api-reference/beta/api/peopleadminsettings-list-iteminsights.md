---
title: "List insightsSettings"
description: "Get the insightsSettings resources from the itemInsights navigation property."
author: "jolintve"
ms.localizationpriority: medium
ms.prod: "insights"
doc_type: apiPageType
---

# List insightsSettings

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get the [insightsSettings](../resources/insightssettings.md) resources from the itemInsights navigation property.

To learn how to customize the privacy of item insights in an organization, see [Customize item insights privacy](/graph/insights-customize-item-insights-privacy).

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "peopleadminsettings-list-iteminsights-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/peopleadminsettings-list-iteminsights-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /admin/people/itemInsights
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [insightsSettings](../resources/insightssettings.md) objects in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_insightssettings"
}
-->
``` http
GET https://graph.microsoft.com/beta/admin/people/itemInsights
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.insightsSettings)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "isEnabledInOrganization": true,
  "disabledForGroup": "edbfe4fb-ec70-4300-928f-dbb2ae86c981"
}
```

