---
name: mqtt
title: MQTT API
permalink: "/en/development"
lang: en
category: Development
sub-category: API
---

If you configured a MQTT Broker with your Gladys installation, you have access to Gladys MQTT API.

Here are all the MQTT topics available, with examples of message to send:

#### Send Pod Heartbeat

This topic is used to tell Gladys that a pod is alive.

Topic:
```
/gladys/master/heartbeat
```

Body:
```json
{
  "pod_selector": "raspberry-pi-zero-pod"
}
```

#### Declare a new Pod

This topic is useful to declare a new pod in Gladys.

Topic
```
/gladys/master/pod/create
```

Body:
```json
{
  "name": "Raspberry Pi Zero Pod",
  "selector": "raspberry-pi-zero-pod"
}
```

#### Create a device

Topic
```
/gladys/master/device/create
```

Body:
```json
{
  "name": "New Lamp",
  "external_id": "philips-hue:1",
  "should_poll": false,
  "features": [{
    "name": "On/Off",
    "category": "light",
    "type": "binary",
    "read_only": false,
    "has_feedback": false,
    "min": 0,
    "max": 1
  }]
}
```

#### Push a new device state

Topic:
```
/gladys/device/state/new
```

Example 1:
```json
{
  "device_feature_external_id": "philips-hue:1:binary",
  "state": 1
}
```

Example 2:
```json
{
  "device_external_id": "philips-hue:1",
  "category": "light",
  "type": "binary",
  "state": 1
}
```
