# Quick Start

Open new sketch in Arduino IDE and include the ClusterDuck library

```c
#include "ClusterDuck.h"
```

Create ClusterDuck object

```c
ClusterDuck duck;
```

Initializes the ClusterDuck class object

**In setup\(\)**

```c
duck.begin(baudRate);
```

Initializes the baud rate for serial printing and messaging. You can adjust to your desired baud rate.

* int baudRate -- Default is 115000

Set device ID and captive portal form length.

```c
duck.setDeviceId(String deviceId, const int formLength);
```

* String deviceId -- input the device ID used to identify your registered device on the web -- do not leave null or empty string
* const int formLength -- \(optional\) define the number of captive portal form fields -- Default is 10 to match our default captive portal template

Setup DuckLink

```c
duck.setupDuckLink();
```

or

```c
duck.setupMamaDuck();
```

can also be used here to setup a MamaDuck, however you cannot use both in the same sketch.

**In loop\(\)**

Add corresponding Duck run code. Must be of the same device type as used in `setup()`. \(e.g. if `duck.setupMamaDuck()` is used in `setup()` use `duck.runMamaDuck()`\)

```c
duck.runDuckLink();
```

Your sketch should look something like this:

```c
#include "ClusterDuck.h"
ClusterDuck duck;

void setup() {
// put your setup code here, to run once:
    duck.begin();
    duck.setDeviceId("Z", 10);
    duck.setupDuckLink();
}

void loop() {
// put your main code here, to run repeatedly:
    duck.runDuckLink();
}
```

Now compile and upload to your device. If using a Heltec LoRa ESP32 board you should see a Duck Online message on the LED screen. You can now open your phone or laptop's wifi preferences and connect to the `SOS DuckLink Network`!

## API

`setDeviceId(String deviceId)`

* Set device ID that will be used to prevent DDoS \(Duck Denial of Service or Duck DoS\). Do not leave deviceId null or as an empty string. Use in setup\(\).

`void begin(int baudRate)`

* Initialize baud rate for serial. Use in setup\(\).

`void setupDisplay(String deviceType)`

* Initializes LED screen on Heltec LoRa ESP32 and configures it to show status, device ID, and the device type. Use in setup\(\).

`void setupLoRa(long BAND, int SS, int RST, int DI0, int DI1, int TxPower)`

* Initializes LoRa radio. Default setting is Heltec LoRa ESP32 pins \(SS = 18, RST = 14, DI0 = 26, DI1 = 25\). TxPower corresponds to the the transmit power of the radio \(max value: 20\). Use in setup\(\).

`void setFlag(void)`

* On LoRa packet received set receivedFlag to true if enableInterrupt is false.

`void setupWebServer(bool createCaptivePortal = false)`

* Initializes the websever and routes. Setting createCaptivePortal to true will make the captive portal automatically pop up on connection. If set to false, the captive portal can still be accessed by opening a browser and going to 192.168.1.1.

  / : HTTP\_GET : Captive Portal.

  /formSubmit : HTTP\_POST : Collects data from all inputs that have a name tag in html, turns it into a single String with each element separated by a \*. Then runs sendPayloadStandard\(String msg\).

  /id : returns \_deviceId.

  /restart : HTTP\_GET : Restarts Duck.

  /mac : HTTP\_GET : Returns device's mac address

  /wifi : HTTP\_GET : Portal to change wifi credentials

  /changeSSID : HTTP\_POST : Takes input values with name tags equal to ssid and pass. Uses these values to run setupInternet\(String SSID, String PASSWORD\)

`void setupWifiAp(const char * AP)`

* Initializes WiFi access point with SSID = AP.

`void setupDns()`

* Initializes DNS server.

`void setupInternet(String SSID, String PASSWORD)`

* Connects device to WiFi using supplied credentails.

`bool ssidAvailable(String val)`

* Does a Wifi scan for available networks. Returns true if val is one of the scanned SSIDs.

`void setupOTA()`

* Sets up Over The Air server for updating firmware on device.

`void setupDuckLink()`

* Template for setting up a DuckLink device. Use in setup\(\)

`void runDuckLink()`

* Template for running core functionality of a DuckLink. Use in loop\(\).

`void setupDetect()`

* Template for settuing up a DetectorDuck device. Use in setup\(\).

`void runDetect()`

* Template for running core functionality of a DetectorDuck. Use in loop\(\).

`void processPortalRequest()`

* Handles incoming and active connections to the captive portal. Required for runing captive portal. Use in loop\(\).

`void setupMamaDuck()`

* Template for setting up a MamaDuck device. Use in setup\(\).

`void runMamaDuck()`

* Template for running core functionality of a MamaDuck. Use in loop\(\).

`String tohex(byte *data, int size)`

* Takes bytes and converts it into hex

`int handlePacket()`

* Takes received LoRa packet and puts data into transmission.

`void sendPayloadStandard(String msg, String topic = "", String senderId = "", String messageId = "", String path = "")`

* Packages msg into a LoRa packet and sends over LoRa. topic is the topic that the message will be published to over MQTT. If topic is not specified it will default to "status". senderId is the ID of the originator of the message. Set device id will be used if senderId is not specified. messageId is the UUID of the message. If messageId is not specified uuidCreator\(\) will be used to create one. path is the recorded pathway of the message and is used as a check to prevent the device from sending multiple of the same message.

`void couple(byte byteCode, String outgoing)`

* Writes data to LoRa packet. outgoing is the payload data to be sent. byteCode is paired with the outgoing so it can be used to identify data on an individual level. Reference setDeviceId\(\) for byte codes. In addition it writes the outgoing length to the LoRa packet.

`bool idInPath(String path)`

* Checks if the path contains deviceId. Returns bool.

`String * getPacketData(int pSize)`

* Called to iterate through received LoRa packet and return data as an array of Strings.

  Note: if using standard byte codes it will store senderId, messageId, payload, and path in a Packet object. This can be accessed using getLastPacket\(\)

`void restartDuck()`

* If using the ESP32 architecture, calling this function will reboot the device.

`void reboot(void *)`

* Used to call restartDuck\(\) when using a timer

`void imAlive(void *)`

* Used to send a "Health Quack" over LoRa on a timer to signify the device is still on and functional.

`String duckMac(boolean format)`

* Returns the MAC address of the device. Using true as an argument will return the MAC address formatted using ':'

`String uuidCreator()`

* Returns as String of 8 random characters and numbers

`String getDeviceId()`

* Returns the device ID

`Packet getLastPacket()`

* Returns a Packet object containing senderId, messageId, payload, and path of last packet received. Note: values are updated after running getPacketData\(\) `volatile bool getFlag()`
* Returns value of receivedFlag.

`volatile bool getInterrupt()`

* Returns value of enableInterrupt. `int getRSSI()`
* Returns RSSI for last packet received.

`Sting getSSID()`

* Returns set SSID for wifi credentials.

`Sting getPassword()`

* Returns set password for wifi credentials.

`void setSSID(String val)`

* Sets value for ssid global variable for Wifi.

`void setPassworkd(String val)`

* Sets value for password global variable for Wifi.

`void flipFlag()`

* Flips value of bool receivedFlag.

`void flipInterrupt()`

* Flips value of bool enableInterrupt.

`void startReceive()`

* Starts LoRa receive mode.

`void startTransmit()`

* Transmits package stored in transmission. Resets both packetIndex and transmission

TODO: if there is an error sending packet, the packet is deleted. Add functionalilty to retry, but not create infinite loop. Maybe use interrupt.

`void ping()`

* Ping template using byte code ping\_B and sends "0" as payload. Devices using CDP will respond to ping with "1".

`void setupLED()`

* Setup channel for RGB LED. `void setColor(int red, int green, int blue)`
* Set color of RGB LED, 0-256.

