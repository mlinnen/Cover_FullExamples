#### Configuration
The example requires you to fill out the Wifi and MQTT details before it will compile.

1. Copy mywifi.sample.h to mywifi.h
2. Edit the mywifi.h file to set the Wifi connection details.
3. Copy mymqttbroker.sample.h to mymqttbroker.h
4. Edit the mymqttbroker.h file to set the MQTT broker details.

After you make the changes to the mywifi.h and mymqttbroker.h you should be able to compile the example. 

#### Wiring
TODO

#### Running the example
The mosquitto MQTT broker and client tools are included in this repository in the test/MQTT/mosquitto folder.  You can use the test/MQTT/brokerlocal.bat to start up a local MQTT broker or just use one that is on on your network. 

You can use the test/MQTT/auditlocal.bat to launch the mosquitto_sub.exe to monitor all messages published to the local broker.  Use this if you are running the local broker without any username or password.

If you have a broker on your network that is password protected then use the test/MQTT/audit.bat to launch the mosquitto_sub.exe to monitor all messages published to the broker.  Before you run the audit.bat you should set the following environment variables:
* MQTT_IP - set to the IP of the MQTT Broker
* MQTT_USR - set to the user used to connect to the broker
* MQTT_PWD - set to the password of the user that will connect to the broker.

Once the broker and the audit are running you can go ahead and download the example code to the arduino and let it run.

Closing the up or down switches will change the state of the garage door and it will be published onto MQTT.  Use can use the bacth files located in test/MQTT folder to simulate various MQTT messages (like commands to close the garage door).
