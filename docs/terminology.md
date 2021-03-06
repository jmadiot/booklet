# Terminology

Some of the terms we use can be a little confusing at times, so here's a list of terms you should be familiar with.

#### MQTT

MQTT is a lightweight publish-subscribe message-bus over which messages can be exchanged between several clients. 

#### broker

A MQTT _broker_ is a server that enables the communication between clients. The broker is responsible for distributing messages to interested clients based on the topic of a message. 

#### publish

The act of sending a message to a broker. 

#### topic
Each message that is published by a client is send to a specific topic on the broker. Clients can opt to receive only certain or all messages depending on which topic they subscribe to. 

#### subscribe

Clients can specify to receive messages that are published to specific topics by subscribing to them. A client that is subscribed to the topic `owntracks/jane/iphone` will, for example, not receive a message that is published to `owntracks/john/nexus`.

#### QoS

_QoS_ or _Quality of Service_, specifies how the app should attempt to publish messages to an MQTT broker.

* QoS=0. The message is delivered at most once, or it is not delivered at all. Its delivery across the network is not acknowledged.
* QoS=1. The message is always delivered at least once. If the sender does not receive an acknowledgment, the message is sent again with the DUP flag set until an acknowledgment is received. As a result receiver can be sent the same message multiple times, and might process it multiple times.
* QoS=2. The message is always delivered exactly once. This is the safest but slowest method of transfer.

#### Retain

When a message is published to a _broker_ with the _durable_ or _retain_ flat
set, it means that the MQTT broker will attempt to store the last published
message on a particular topic.

A client which subscribes to that topic will receive that last retained message once it
connects to the broker.

#### Geocoding

_Reverse geocoding_ is the act of looking up the address for a pair of coordinates.

#### Geofence

A _geofence_ is an area around a particular coordinate. Geofences will trigger certain actions once the device enters or leaves the setup area. 
