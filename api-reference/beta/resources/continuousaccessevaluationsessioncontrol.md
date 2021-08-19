---
title: "continuousAccessEvaluationSessionControl resource type"
description: "Session control to control continuous access evaluation settings"
author: "lujiangfeng666"
localization_priority: Normal
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# continuousAccessEvaluationSessionControl resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Session control to control continuous access evaluation settings. Inherits from [Conditional Access Session Control](conditionalaccesssessioncontrol.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|mode|continuousAccessEvaluationMode|Specifies continuous access evaluation' setting. Possible values are: `strictEnforcement`, `disabled`, `unknownFutureValue`.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.continuousAccessEvaluationSessionControl"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.continuousAccessEvaluationSessionControl",
  "mode": "String"
}
```
