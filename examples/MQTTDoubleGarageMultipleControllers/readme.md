## Overview
This is a much more practical example the reduces the amount of wiring you will need to run but will increase the number of arduino controllers you will use.  This example uses 3 ESP8266's that all work together to manage controlling 2 garage doors.  One ESP8266 listens for commands to open or close either door and controls a relay to tell the door to change state.  This same ESP8266 also listens for state changes with either door and controls some LEDs telling the user what state the door is in. Two other ESP8266's monitor each door's state using 2 magnetic sensors on each door.

The following sketches will be used on each ESP8266:
* MQTTCommandAndStatus - fires a relay to command either door and also displays the state of each door.
* MQTTSensor1 - monitors two magnetic switches for door 1 and publishes MQTT messages when the state of the door changes.  
* MQTTSensor2 - monitors two magnetic switches for door 2 and publishes MQTT messages when the state of the door changes.  

#### Configuration
The example requires you to fill out the Wifi and MQTT details for each sketch before it will compile.

1. In each sketch folder (MQTTCommandAndStatus, MQTTSensor1 and MQTTSensor1)
2. Copy mywifi.sample.h to mywifi.h
3. Edit the mywifi.h file to set the Wifi connection details.
4. Copy mymqttbroker.sample.h to mymqttbroker.h
5. Edit the mymqttbroker.h file to set the MQTT broker details.

After you make the changes to the mywifi.h and mymqttbroker.h you should be able to compile each of the example sketches. 

#### Wiring
TODO

#### Running the example
The mosquitto MQTT broker and client tools are included in this repository in the test/MQTT/mosquitto folder.  You can use the test/MQTT/brokerlocal.bat to start up a local MQTT broker or just use one that is on on your network. 

You can use the test/MQTT/auditlocal.bat to launch the mosquitto_sub.exe to monitor all messages published to the local broker.  Use this if you are running the local broker without any username or password.

If you have a broker on your network that is password protected then use the test/MQTT/audit.bat to launch the mosquitto_sub.exe to monitor all messages published to the broker.  Before you run the audit.bat you should set the following environment variables:
* MQTT_IP - set to the IP of the MQTT Broker
* MQTT_USR - set to the user used to connect to the broker
* MQTT_PWD - set to the password of the user that will connect to the broker.

Once the broker and the audit are running you can go ahead and download the sketches to each of the ESP8266s and let it run.

Closing the up or down switches will change the state of either garage door and it will be published onto the MQTT broker.  You can use the batch files located in test/MQTT folder to simulate various MQTT messages (like commands to close either of the garage doors).
