---
title: "Partner Billing invoicing and reconciliation API overview"
description: "Export APIs allow Microsoft partners to export of billed/unbilled reconciliation data to download the data in efficient and async fashion."
author: "abhishek-singh-ms"
ms.localizationpriority: medium
ms.prod: "reports"
doc_type: resourcePageType
ms.custom: zt-include
---

# Partner Billing invoicing and reconciliation data API overview

Namespace: microsoft.graph

As part of the Microsoft Partner Center ecosystem, Microsoft direct partners in the Cloud Solution Provider programs can request to export their billed and unbilled data to azure blob storage in async fashion. The asynchronous API is a novel method for quickly accessing billing and reconciliation data in manageable chunks. It eliminates the need to maintain an open connection for hours and loop through millions of transactions iteratively.

> [!NOTE]
>Daily-rated usage normally takes 24 hours to appear in Partner Center or to be accessed through the API.


## API overview

You can download the usage data asynchronously using three new steps (API endpoints). To learn more, read the following sections:

### Usage line-item endpoint
Use this API to access billed or unbilled consumption line items. It returns a 202 HTTP status and a location header with the URL, which you must poll at regular intervals until you receive a success status with a manifest URL

### Operation status endpoint
Until you receive the success status, keep polling this API at a regular interval. If the requested data is unavailable, the API response includes a Retry-After header indicating how long you should wait before sending another request. When operation has completed successfully, response also provides [manifest](../resources/partners-billing-manifest.md) with details of the generated files. Manifest provides a storage folder from which actual billing data can be downloaded. The response splits or partitions the files to optimize throughput and I/O parallelism

## Use cases for reconciliation APIs

This section describes the ways that Microsoft partners can use the billing APIs to programmatically get their billing and reconciliation data.

### Billed reconciliation data

| Use cases | APIs |
|--|--|
| Create a new export operation to export billed reconciliation data | [Create billed export operation](../api/partners-billing-billedusage-export.md) |
| Get if export operation is complete or not | [Get operation status](../api/partners-billing-operation-get.md) |


### Unbilled reconciliation data

| Use cases | APIs |
|--|--|
| Create a new export operation to export unbilled reconciliation data | [Create unbilled export operation](../api/partners-billing-unbilledusage-export.md) |
| Get if export operation is complete or not | [Get operation status](../api/partners-billing-operation-get.md) |



## Permissions

To export reconciliation data, the calling principal must be in the partner tenant and be granted the appropriate partner billing privilege permissions. This API supports the following partner permissions.

[!INCLUDE [permissions-table](../includes/permissions/partners-permissions.md)]

<!-- Start of: Link to ZT guidance: H2 section -->

[!INCLUDE [zero-trust](~/../azure_docs/includes/active-directory-zero-trust.md)]

<!-- End of: Link to ZT guidance -->

<!-- {
  "type": "#page.annotation",
  "description": "Partner Billing invoicing and reconciliation API overview",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
    "Error: /resources/partners-billing-usageexport-api-overview.md:
      Exception processing links.
      Link Definition was null. Link text: !INCLUDE zero-trust (Parameter 'Definition')"
  ]
}-->
