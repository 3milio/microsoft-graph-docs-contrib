---
title: "List trustedCertificateAuthorities"
description: "List the trusted certificate authorities in a certificateBasedApplicationConfiguration object."
author: "madansr7"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# List trustedCertificateAuthorities
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

List the trusted certificate authorities in a [certificateBasedApplicationConfiguration](../resources/certificatebasedapplicationconfiguration.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|AppCertTrustConfiguration.Read.All, AppCertTrustConfiguration.ReadWrite.All|
|Delegated (personal Microsoft account)|AppCertTrustConfiguration.Read.All, AppCertTrustConfiguration.ReadWrite.All|
|Application|Not supported.|

[!INCLUDE [app-cert-config-apis](../includes/app-cert-config-apis.md)]
## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /directory/certificateAuthorities/certificateBasedApplicationConfigurations/{certificateBasedApplicationConfigurationId}/trustedCertificateAuthorities
```
## Optional query parameters

This method supports the `$select` OData query parameter to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [certificateAuthorityAsEntity](../resources/certificateauthorityasentity.md) objects in the response body.

## Examples
The following example shows how to get a list of trusted certificate authorities.

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "list_certificateauthorityasentity"
}
-->

``` http
GET directory/certificateAuthorities/certificateBasedApplicationConfigurations/0a6a9b97-b84c-406a-a703-14d699d1fbb1/trustedCertificateAuthorities
```


### Response
The following is an example of the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.certificateAuthorityAsEntity"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json
{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#directory/certificateAuthorities/certificateBasedApplicationConfigurations('e47a3693-e84f-48bf-8c54-767c56ad46c1')/trustedCertificateAuthorities",
    "value": [
        {
            "certificate": "MIIIcTCCBlmgA=",
            "id": "3add3691-8b1e-4ecf-83bd-4effceaae3f6",
            "isRootAuthority": false,
            "issuer": "CN=AME Infra CA 05, DC=AME, DC=GBL"
        },
        {
            "certificate": "MIIFVjCCAz6gA=",
            "id": "a572699a-8b9f-42df-a168-5e077078abfd",
            "isRootAuthority": true,
            "issuer": "CN=ameroot, DC=AME, DC=GBL"
        }
    ]
}
```
