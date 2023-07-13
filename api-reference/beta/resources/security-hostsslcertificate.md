---
title: "hostSslCertificate resource type"
description: "Observed relationship between a host and an sslCertificate"
author: "nblankenau"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: resourcePageType
---

# hostSslCertificate resource type

Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents an observed relationship between a **host** and an **sslCertificate**.


Inherits from [microsoft.graph.security.artifact](../resources/security-artifact.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List hostSslCertificates](../api/security-hostsslcertificate-list-host.md)|[microsoft.graph.security.hostSslCertificate](../resources/security-hostsslcertificate.md) collection|Get a list of the [microsoft.graph.security.hostSslCertificate](../resources/security-hostsslcertificate-get.md) objects and their properties.
|[Get hostSslCertificate](../api/security-hostsslcertificate-get.md)|[microsoft.graph.security.hostSslCertificate](../resources/security-hostsslcertificate.md)|Read the properties and relationships of a [microsoft.graph.security.hostSslCertificate](../resources/security-hostsslcertificate.md) object.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|firstSeenDateTime|DateTimeOffset|The first date and time that this hostSslCertificate was observed.|
|id|String|The system-generated id for this hostSslCertificate. Inherited from [microsoft.graph.entity](../resources/entity.md).|
|lastSeenDateTime|DateTimeOffset|The most recent date and time that this hostSslCertificate was observed.|
|ports|[microsoft.graph.security.hostSslCertificatePort](../resources/security-hostsslcertificateport.md) collection|The ports related with this hostSslCertificate.|

## Relationships
|Relationship|Type|Description|
|:---|:---|:---|
|host|[host](../resources/security-host.md)|The **host** for this hostSslCertificate|
|sslCertificate|[sslCertificate](../resources/security-sslcertificate.md)|The **sslCertificate** for this hostSslCertificate|

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.security.hostSslCertificate",
  "baseType": "microsoft.graph.security.artifact",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.security.hostSslCertificate",
  "id": "String (identifier)",
  "firstSeenDateTime": "String (timestamp)",
  "lastSeenDateTime": "String (timestamp)",
  "ports": [
    {
      "@odata.type": "microsoft.graph.security.hostSslCertificatePort"
    }
  ]
}
```

