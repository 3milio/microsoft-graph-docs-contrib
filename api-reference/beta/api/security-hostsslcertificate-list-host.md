---
title: "List host"
description: "Get the host resources from the host navigation property."
author: "**TODO: Provide Github Name. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
ms.localizationpriority: medium
ms.prod: "**TODO: Add MS prod. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
doc_type: apiPageType
---

# List host
Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get the host resources from the host navigation property.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|ThreatIntelligence.Read.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|ThreatIntelligence.Read.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /security/threatIntelligence/hosts/{hostId}/sslCertificates
```

## Optional query parameters
This method also supports the `$count`, `$select`, `$orderBy` `$top`, and `$skip` OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [microsoft.graph.security.hostSslCertificate](../resources/security-hostsslcertificate.md) objects in the response body.

## Examples

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "list_host"
}
-->
``` http
GET https://graph.microsoft.com/beta/security/threatIntelligence/hosts/contoso.com/sslCertificates?$count=true&$top=1&$skip=5
```


### Response
The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.security.host)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "id": "Y29udG9zby5jb20xNTUwMGZiOTY1NTE1MDVmMWVkYjI0ZGQzYjM2ZmNmZmRiNzY1ODMzYjgxMTg=",
      "firstSeenDateTime": "2023-03-10T01:20:47.000Z",
      "lastSeenDateTime": "2023-04-02T00:00:00.000Z",
      "ports": [
        {
          "port": 80,
          "firstSeenDateTime": "2023-03-10T01:20:47.000Z",
          "lastSeenDateTime": "2023-04-02T00:00:00.000Z",
        },
        {
          "port": 3000,
          "firstSeenDateTime": "2023-03-10T01:20:47.000Z",
          "lastSeenDateTime": "2023-04-02T00:00:00.000Z",
        },
      ],
      "host": {
        "@odata.type": "#microsoft.graph.security.hostName",
        "id": "contoso.com"
      },
      "sslCertificate": {
        "@odata.context": "$metadata#microsoft.graph.security.sslCertificate",
        "id": "ZmI5NjU1MTUwNWYxZWRiMjRkZDNiMzZmY2ZmZGI3NjU4MzNiODExOA==",
        "firstSeenDateTime": "2023-03-10T01:20:47.000Z",
        "lastSeenDateTime": "2023-04-02T00:00:00.000Z",
        "fingerprint": "fb:96:55:15:05:f1:ed:b2:4d:d3:b3:6f:cf:fd:b7:65:83:3b:81:18",
        "sslVersion": "3",
        "expirationDateTime": "2024-03-03T18:56:17.000Z",
        "issueDateTime": "2023-03-09T18:56:17.000Z",
        "sha1": "fb96551505f1edb24dd3b36fcffdb765833b8118",
        "serialNumber": "1137389559885717770175191329273386705719099773",
        "subject": {
          "commonName": "microsoft.com",
          "address": {
            "city": "Redmond",
            "countryOrRegion": "US",
            "postalCode": null,
            "postOfficeBox": null,
            "state": "WA",
            "street": null,
            "type": "unknown"
          },
          "email": null,
          "givenName": null,
          "organizationName": "Microsoft Corporation",
          "organizationUnitName": null,
          "serialNumber": null,
          "surname": null,
          "alternateName": [
            "pymes.microsoft.com",
            "mac2.microsoft.com",
            "sponsors.microsoft.com",
            "oemcommunity.microsoft.com",
            "gigjam.microsoft.com",
            "businesscentral.microsoft.com"
          ]
        },
        "issuer": {
          "commonName": "Microsoft Azure TLS Issuing CA 05",
          "address": {
            "city": null,
            "countryOrRegion": "US",
            "postalCode": null,
            "postOfficeBox": null,
            "state": null,
            "street": null,
            "type": "unknown"
          },
          "email": null,
          "givenName": null,
          "organizationName": "Microsoft Corporation",
          "organizationUnitName": null,
          "serialNumber": null,
          "surname": null,
          "alternateName": []
        }
      }
    }
  ]
}
```

