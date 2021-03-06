# Overview
This is a set of examples that showcase how the Cover libraries can be used together to construct several variations of controlling garage doors.

## Dependencies
These set of examples depend on the follwing libraries being installed:
* Robots Big Data Libraries http://robotsbigdata.com/index.html
* [Pub/Sub Client](http://pubsubclient.knolleary.net)
* [Cover Core](https://github.com/mlinnen/Cover_Core)
* [Cover Dual Switch Sensor](https://github.com/mlinnen/Cover_DualSwitchSensor)
* [Cover Garage Door Relay](https://github.com/mlinnen/Cover_GarageDoorRelay)
* [Cover Single LED Status](https://github.com/mlinnen/Cover_SingleLEDStatus)

You must install the dependent libraries before you compile the examples.

## Examples
### MQTT Single Garage
This example uses the cover libraries to control a single garage door all on one ESP8266.  See [ReadMe](examples/MQTTSingleGarage/readme.md) for more details.

### MQTT Double Garage
This example uses the cover libraries to control 2 garage doors all on one ESP8266.  See [ReadMe](examples/MQTTDoubleGarage/readme.md) for more details.

### MQTT Double Garage with multiple Controllers
This example uses the cover libraries to control 2 garage doors using multiple ESP8266s.  This is a more practical example because it limits the amount of wiring you need since you use the MQTT broker as a means to command both doors and sense the state of each door.  One ESP8266 is used to fire the relays to control the doors as well as display the state of each door.  Then you use two other ESP8266s closer to the up/down sensors to track the state of each door.  See [ReadMe](examples/MQTTDoubleGarageMultipleControllers/readme.md) for more details.


