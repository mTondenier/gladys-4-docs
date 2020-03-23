
---
layout: docs
name: rflink-configuration
title: Configurer les périphériques Rflink
category: Configuration
permalink: "/fr/configuration"
lang: en
---

## Introduction

[Rflink](http://www.rflink.nl/blog2/) is a home automation program that manages 433Mhz , 2.4Ghz , Mysensors and Milgiht devices.

## Connect your Rflink Gateway

Go to the Rflink integration Page and click on settings :
<br>
<img src="/assets/image/configuration/rflink/settings.PNG" alt="Settings" class="img-responsive" />


select the Usb port on which the gateway is connected and click connect : 

<img src="/assets/image/configuration/rflink/port.PNG" alt="Port selection" class="img-responsive" />


Reboot Gladys and you are ready!



## Add a device

There are two types of devices : Actuators and sensors .

# If your device is a sensor : 
	go in the devices tab and wait for your sensor to send data , gladys will automatically add the device.
	
# If your device is an actuator with a remote : 
	go in the devices tab and press the button of your remote ,  gladys will automatically add the device.
	
# If your device is actuator without remote : 
	You will have to known the id of the device and it's swicth number/channel.
	<br>
	go in the devices tab and click on new , add your device manually.

