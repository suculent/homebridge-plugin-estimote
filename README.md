## Purpose

[![Greenkeeper badge](https://badges.greenkeeper.io/suculent/homebridge-plugin-estimote.svg)](https://greenkeeper.io/)

This is a plugin for Estimote Beacons with Homebridge integration, that sends received Bluetooth Telemetry Packets to MQTT and ELK.

## Requirements

* Running MQTT server.
* Running ELK stack.
* Node.js, Node Package Manager, Homebridge

## Installation

Install this as a homebridge plugin on the device where you run homebridge. You can redirect 'localhost' to a MQTT server you are using, if on other device. In my case, both are running on Raspberry PI.

    git clone https://github.com/suculent/homebridge-plugin-estimote.git
    cd homebridge-plugin-estimote/
    sudo npm install -g .        

Re/start your Homebridge now.
    
## Usage

Publishes to MQTT channels /ble
If you don't know how, install MQTT.fx and try again.

### Sample Minimal Homebridge Configuration

```
 "accessories" : [
    {
      "accessory" : "Estimote",
      "name" : "Estimote BLE",
      "description" : "Estimote Telemetry",
      "elasticsearch" : "http://mini.local:9200",
      "mqtt_broker" : "mqtt://192.168.1.21",
      "mqtt_channel" : "/ble"
    }
  ]
```
