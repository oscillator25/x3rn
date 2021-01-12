# Frequently-Asked-Questions

## General

### How many ducks do I need to set-up a network?

You only need at least two ducks, a papa duck and mama duck, to set-up a network. With two ducks, you can have a point to point network with the protocol with just 2 ducks. Adding more ducks will extend the network.

## Errors when compiling

### _fatal error: PubSubClient.h: No such file or directory_

The cause of this error because the library, _PubSubClient.h_, is missing. To install the library, go to Sketch -&gt; Include Library -&gt; Manage Libraries. In the search box, type PubSub. Find and install PubSubClient by Nick O'Leary.

### Multiple libraries were found for "WiFi.h"

This issue occurred because when the program tried to compile, it came across two “Wifi.h” files and was not sure which one to choose. But this is a warning. It should not be an error. Read the whole error to see if there are other issues.

### Linux issue with permission denied to port

* ser\_open\(\): can't open device "/dev/ttyACM0": Permission denied
* To fix this run the following commands via terminal 

  $ sudo usermod -a -G dialout 

  $ sudo chmod a+rw /dev/ttyACM0

* Replace username with your devices name & Replace /dev/ttyACM0 with your USB Port
* That can be found inside Arduino IDE via TOOLS &gt; Port 

## Setup Issues

### Board not displaying in Port

Make sure that the LoRa board is connected to the computer using a DATA TRANSFER CABLE. Not all cables are created equal. One of the cables transfer data from computer to computer. The other cable just charges devices but cannot transfer/receive data. Make sure you are using a data transfer cable.

## Errors When Running the ClusterDuck Network

### _Publish to 'client' failed._

This can be a data packet size issue. Check to see if the PubSubClient library is up-to-date. If it is then go into the PubSubClient.h file and change the parameter value of MQTT\_MAX\_PACKET\_SIZE, from 128 to 256. This increases the data capacity for MQTT. For more details, [check this closed issue](https://github.com/Code-and-Response/ClusterDuck-Protocol/issues/116)

[Github](https://github.com/Code-and-Response/ClusterDuck-Protocol)

