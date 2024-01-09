---
title: "Update workplaceSensorDevice"
description: "Update the properties of a workplace sensor device."
author: "ms-amakumar"
ms.localizationpriority: medium
ms.prod: "outlook"
doc_type: apiPageType
---

# Update workplaceSensorDevice
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a workplace sensor device.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|PlaceDevice.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|PlaceDevice.ReadWrite.All|

For an app with delegated permissions to write workplace devices, the signed-in user must be a member of one of the following Microsoft Entra administrator roles: Global Administrator or Exchange Online management roles: TenantPlacesManagement.

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /workplace/sensorDevices/{id}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
<!-- [!INCLUDE [table-intro](../../includes/update-property-table-intro.md)] -->

In the request body, provide the entire JSON for the [workplaceSensorDevice](../resources/workplacesensordevice.md) object with updated fields. Partial updates aren't supported. If any optional property is excluded, it's set to null. To add new sensors, append a new sensor object to the existing sensor collection. Conversely, if a sensor object is removed from the collection, it's deleted from the device.

The following table specifies the properties that can be updated.

|Property|Type|Description|
|:---|:---|:---|
|description|String|The description of the device. Optional.|
|deviceId|String|The user-defined unique identifier of the device provided at the time of creation. Required. Read-Only.|
|displayName|String|The display name of the device. Optional.|
|ipV4Address|String|The IPv4 Address of the device. Optional.|
|ipV6Address|String|The IPv6 Address of the device. Optional.|
|macAddress|String|The MAC address of the device. Optional.|
|manufacturer|String|The manufacturer of the device. Required.|
|placeId|String|The unique identifier of the place where the device is located. If the device is installed in a room featuring a mailbox, this property should match the ExternalDirectoryObjectId or Microsoft Entra object Id of the room mailbox. Optional.|
|sensors|[workplaceSensor](../resources/workplacesensor.md) collection|A list of sensors associated with the device that collect and report data about physical or environmental conditions, such as occupancy, people count, inferred occupancy, temperature etc. Required.|
|tags|String collection|A list of custom tags associated with the device. Supports $filter. Optional.|


## Response

If successful, this method returns a `200 OK` response code and an updated [workplaceSensorDevice](../resources/workplacesensordevice.md) object in the response body.

## Examples
### Example 1: Add a new tag
#### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "update_workplacesensordevice_tags"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/workplace/sensorDevices/ade7078f-4bf5-4239-bfde-95a7c4225df7
Content-Type: application/json

{
    "deviceId": "contoso_9D6816",
    "displayName": "Contoso 9D6816 Device",
    "description": "Contoso 9D6816 Device",
    "macAddress": "00:0A:95:9D:68:16",
    "manufacturer": "Contoso",
    "ipV4Address": "192.168.1.100",
    "ipV6Address": "2001:db8::ff00:42:8329",
    "placeId": "acfa3bc0-2b83-425b-8910-84a0250e9671",
    "tags": [
        "Building A",
        "Floor 3",
        "Room 301",
        "Conference Room",
        "v1.0.7"
    ],
    "sensors": [
        {
            "sensorType": "occupancy"
        },
        {
            "sensorType": "peopleCount"
        }
    ]
}
```


#### Response
The following is an example of the response
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.workplaceSensorDevice"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#workplace/sensorDevices/$entity",
    "id": "ade7078f-4bf5-4239-bfde-95a7c4225df7",
    "deviceId": "contoso_9D6816",
    "displayName": "Contoso 9D6816 Device",
    "description": "Contoso 9D6816 Device",
    "macAddress": "00:0A:95:9D:68:16",
    "manufacturer": "Contoso",
    "ipV4Address": "192.168.1.100",
    "ipV6Address": "2001:db8::ff00:42:8329",
    "placeId": "acfa3bc0-2b83-425b-8910-84a0250e9671",
    "tags": [
        "Building A",
        "Floor 3",
        "Room 301",
        "Conference Room",
        "v1.0.7"
    ],
    "sensors": [
        {
            "sensorId": "Occupancy",
            "displayName": null,
            "sensorType": "occupancy",
            "placeId": "acfa3bc0-2b83-425b-8910-84a0250e9671"
        },
        {
            "sensorId": "PeopleCount",
            "displayName": null,
            "sensorType": "peopleCount",
            "placeId": "acfa3bc0-2b83-425b-8910-84a0250e9671"
        }
    ]
}
```

### Example 2: Add a new sensor
#### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "update_workplacesensordevice_new_sensor"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/workplace/sensorDevices/ade7078f-4bf5-4239-bfde-95a7c4225df7
Content-Type: application/json

{
    "deviceId": "contoso_9D6816",
    "displayName": "Contoso 9D6816 Device",
    "description": "Contoso 9D6816 Device",
    "macAddress": "00:0A:95:9D:68:16",
    "manufacturer": "Contoso",
    "ipV4Address": "192.168.1.100",
    "ipV6Address": "2001:db8::ff00:42:8329",
    "placeId": "acfa3bc0-2b83-425b-8910-84a0250e9671",
    "tags": [
        "Building A",
        "Floor 3",
        "Room 301",
        "Conference Room"
    ],
    "sensors": [
        {
            "sensorType": "occupancy"
        },
        {
            "sensorType": "peopleCount"
        },
        {
            "sensorType": "inferredOccupancy"
        }
    ]
}
```


#### Response
The following is an example of the response
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.workplaceSensorDevice"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#workplace/sensorDevices/$entity",
    "id": "ade7078f-4bf5-4239-bfde-95a7c4225df7",
    "deviceId": "contoso_9D6816",
    "displayName": "Contoso 9D6816 Device",
    "description": "Contoso 9D6816 Device",
    "macAddress": "00:0A:95:9D:68:16",
    "manufacturer": "Contoso",
    "ipV4Address": "192.168.1.100",
    "ipV6Address": "2001:db8::ff00:42:8329",
    "placeId": "acfa3bc0-2b83-425b-8910-84a0250e9671",
    "tags": [
        "Building A",
        "Floor 3",
        "Room 301",
        "Conference Room"
    ],
    "sensors": [
        {
            "sensorId": "Occupancy",
            "displayName": null,
            "sensorType": "occupancy",
            "placeId": "acfa3bc0-2b83-425b-8910-84a0250e9671"
        },
        {
            "sensorId": "PeopleCount",
            "displayName": null,
            "sensorType": "peopleCount",
            "placeId": "acfa3bc0-2b83-425b-8910-84a0250e9671"
        },
        {
            "sensorId": "InferredOccupancy",
            "displayName": null,
            "sensorType": "inferredOccupancy",
            "placeId": "acfa3bc0-2b83-425b-8910-84a0250e9671"
        }
    ]
}
```

### Example 3: Remove a sensor
#### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "update_workplacesensordevice_remove_sensor"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/workplace/sensorDevices/ade7078f-4bf5-4239-bfde-95a7c4225df7
Content-Type: application/json

{
    "deviceId": "contoso_9D6816",
    "displayName": "Contoso 9D6816 Device",
    "description": "Contoso 9D6816 Device",
    "macAddress": "00:0A:95:9D:68:16",
    "manufacturer": "Contoso",
    "ipV4Address": "192.168.1.100",
    "ipV6Address": "2001:db8::ff00:42:8329",
    "placeId": "acfa3bc0-2b83-425b-8910-84a0250e9671",
    "tags": [
        "Building A",
        "Floor 3",
        "Room 301",
        "Conference Room"
    ],
    "sensors": [
        {
            "sensorType": "peopleCount"
        }
    ]
}
```


#### Response
The following is an example of the response
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.workplaceSensorDevice"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#workplace/sensorDevices/$entity",
    "id": "ade7078f-4bf5-4239-bfde-95a7c4225df7",
    "deviceId": "contoso_9D6816",
    "displayName": "Contoso 9D6816 Device",
    "description": "Contoso 9D6816 Device",
    "macAddress": "00:0A:95:9D:68:16",
    "manufacturer": "Contoso",
    "ipV4Address": "192.168.1.100",
    "ipV6Address": "2001:db8::ff00:42:8329",
    "placeId": "acfa3bc0-2b83-425b-8910-84a0250e9671",
    "tags": [
        "Building A",
        "Floor 3",
        "Room 301",
        "Conference Room"
    ],
    "sensors": [
        {
            "sensorId": "PeopleCount",
            "displayName": null,
            "sensorType": "peopleCount",
            "placeId": "acfa3bc0-2b83-425b-8910-84a0250e9671"
        }
    ]
}
```

