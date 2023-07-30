---
title: "Get branchConnectivityConfiguration"
description: "Retrieve the connectivity configuration for a specific branch."
author: "Moti-ba"
ms.localizationpriority: medium
ms.prod: identity-and-access
doc_type: apiPageType
---

# Get branchConnectivityConfiguration
Namespace: microsoft.graph.networkaccess

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve the connectivity configuration for a specific branch.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|NetworkAccessPolicy.Read.All, NetworkAccessPolicy.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

[!INCLUDE [rbac-global-secure-access-apis-read](../includes/rbac-for-apis/rbac-global-secure-access-apis-read.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /networkAccess/connectivity/branches/{branchSiteId}/connectivityConfiguration
```

## Optional query parameters
This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [microsoft.graph.networkaccess.branchConnectivityConfiguration](../resources/networkaccess-branchconnectivityconfiguration.md) object in the response body.

## Examples

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "get_branchconnectivityconfiguration"
}
-->
``` http
GET networkAccess/connectivity/branches/{branchSiteId}/connectivityConfiguration
```


### Response
The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.networkaccess.branchConnectivityConfiguration"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "http://graph.microsoft.com/beta/$metadata#branchConnectivityConfiguration",
    "branchId": "19a92090-c14e-4cea-a933-27d38f72c4d1",
    "branchName": "Seattle branch office",
    "links": [
        {
            "id": "26b92330-c246-2cef-a131-27d38f72c4s4",
            "displayName": "CPE1",
            "localConfigurations": [
                {
                    "endpoint": "20.127.132.184",
                    "asn": 65532,
                    "bgpAddress": "192.168.1.253",
                    "region": "eastUS"
                },
                {
                    "endpoint": "20.127.132.185",
                    "asn": 65532,
                    "bgpAddress": "192.168.1.254",
                    "region": "westUS"
                }
            ],
            "peerConfiguration": {
                "endpoint": "120.10.10.10",
                "asn": 65530,
                "bgpAddress": "10.20.20.20"
            }
        }
    ]
}
```

