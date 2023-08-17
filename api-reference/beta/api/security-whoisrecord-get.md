---
title: "Get whoisRecord"
description: "Read the properties and relationships of a whoisRecord object."
author: "joerattazzi-microsoft"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: apiPageType
---

# Get whoisRecord

Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

[!INCLUDE [threatintelligence-api-disclaimer](../../includes/threatintelligence-api-disclaimer.md)]

Read the properties and relationships of a [microsoft.graph.security.whoisRecord](../resources/security-whoisrecord.md) object.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
| :------------------------------------- | :------------------------------------------ |
| Delegated (work or school account)     | ThreatIntelligence.Read.All                 |
| Delegated (personal Microsoft account) | Not supported.                              |
| Application                            | ThreatIntelligence.Read.All                 |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

```http
GET /security/threatIntelligence/whoisRecords/{whoisRecordId}
```

## Optional query parameters

This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

| Name          | Description               |
| :------------ | :------------------------ |
| Authorization | Bearer {token}. Required. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [microsoft.graph.security.whoisRecord](../resources/security-whoisrecord.md) object in the response body.

## Examples

### Request

The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "get_whoisrecord",
  "sampleKeys": ["Y29udG9zby5jb20kJDY5NjQ3ODEyMDc3NDY1NzI0MzM="]
}
-->

```http
GET https://graph.microsoft.com/beta/security/threatIntelligence/whoisRecords/Y29udG9zby5jb20kJDY5NjQ3ODEyMDc3NDY1NzI0MzM=
```

### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.security.whoisRecord"
}
-->

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.security.whoisRecord",
  "id": "Y29udG9zby5jb20kJDY5NjQ3ODEyMDc3NDY1NzI0MzM=",
  "expirationDateTime": "2023-08-31T00:00:00Z",
  "registrationDateTime": "2022-07-30T09:43:19Z",
  "firstSeenDateTime": null,
  "lastSeenDateTime": null,
  "lastUpdateDateTime": "2023-06-24T08:34:15.984Z",
  "billing": null,
  "noc": null,
  "zone": null,
  "whoisServer": "rdap.markmonitor.com",
  "domainStatus": "client update prohibited,client transfer prohibited,client delete prohibited",
  "rawWhoisText": "Registrar: \n  Handle: 1891582_DOMAIN_COM-VRSN\n  LDH Name: contoso.com\n  Nameserver: \n    LDH Name: ns1.contoso.com\n    Event: \n      Action: last changed\n...",
  "abuse": {
    "email": "noreply@contoso.com",
    "name": null,
    "organization": null,
    "telephone": "+1.5555555555",
    "fax": null,
    "address": {
      "city": null,
      "countryOrRegion": null,
      "postalCode": null,
      "state": null,
      "street": null,
      "type": "unknown"
    }
  },
  "admin": {
    "email": "noreply@contoso.com",
    "name": "Domain Administrator",
    "organization": "Contoso Org",
    "telephone": "+1.5555555555",
    "fax": "+1.5555555555",
    "address": {
      "city": "Redmond",
      "countryOrRegion": "US",
      "postalCode": "98052",
      "state": "WA",
      "street": "123 Fake St.",
      "type": "unknown"
    }
  },
  "registrar": {
    "email": null,
    "name": null,
    "organization": "MarkMonitor Inc.",
    "telephone": null,
    "fax": null,
    "address": null
  },
  "registrant": {
    "email": "noreply@contoso.com",
    "name": "Domain Administrator",
    "organization": "Contoso Corporation",
    "telephone": "+1.5555555555",
    "fax": "+1.5555555555",
    "address": {
      "city": "Redmond",
      "countryOrRegion": "US",
      "postalCode": "98052",
      "state": "WA",
      "street": "123 Fake St.",
      "type": "unknown"
    }
  },
  "technical": {
    "email": "noreply@contoso.com",
    "name": "Hostmaster",
    "organization": "Contoso Corporation",
    "telephone": "+1.5555555555",
    "fax": "+1.5555555555",
    "address": {
      "city": "Redmond",
      "countryOrRegion": "US",
      "postalCode": "98052",
      "state": "WA",
      "street": "123 Fake St.",
      "type": "unknown"
    }
  },
  "nameservers": [
    {
      "firstSeenDateTime": null,
      "lastSeenDateTime": null,
      "host": {
        "id": "ns1.contoso-dns.com"
      }
    },
    {
      "firstSeenDateTime": null,
      "lastSeenDateTime": null,
      "host": {
        "id": "ns2.contoso-dns.com"
      }
    },
    {
      "firstSeenDateTime": null,
      "lastSeenDateTime": null,
      "host": {
        "id": "ns3.contoso-dns.com"
      }
    },
    {
      "firstSeenDateTime": null,
      "lastSeenDateTime": null,
      "host": {
        "id": "ns4.contoso-dns.com"
      }
    }
  ],
  "host": {
    "id": "contoso.com"
  }
}
```
