# Install

#### Add ESP32 Board Library

1. Open Arduino
2. Go to Preferences, and in the “Additional Boards Manager URLs” please add the following string:

   [https://dl.espressif.com/dl/package\_esp32\_index.json,https://adafruit.github.io/arduino-board-index/package\_adafruit\_index.json](https://dl.espressif.com/dl/package_esp32_index.json,https://adafruit.github.io/arduino-board-index/package_adafruit_index.json)

```text
![Add additional boards to Arduino](https://www.project-owl.com/assets/wiki/arduino_boards.png "Arduino Boards")
```

#### Install ClusterDuck Protocol

**Using the Library Manager “COMING SOON”**

**Importing as a .zip Library**

In the Arduino IDE, navigate to _Sketch &gt; Include Library &gt; Add .ZIP Library_. At the top of the drop down list, select the option to "Add .ZIP Library".

![add library to arduino](https://www.project-owl.com/assets/wiki/add_Library.png)

Navigate to the downloaded ClusterDuck Protocol Folder and select.

Return to the _Sketch &gt; Include Library menu._ menu. You should now see the library at the bottom of the drop-down menu. It is ready to be used in your sketch. The zip file will have been expanded in the _libraries_ folder in your Arduino sketches directory.

**Manual Install**

You will need to clone the ClusterDuck Protocol onto your local machine and include the libraries folder into your local arduino libraries folder.

1. Clone the ClusterDuck Protocol onto your local machine `git clone https://github.com/Code-and-Response/ClusterDuck-Protocol.git`
2. Pull all the Library submodules needed for the Arduino IDE `git submodule update --init --recursive`
3. Copy the `ClusterDuck-Protocol`folder into your local Arduino Libraries folder **MacOs** _/Users/USER/Documents/Arduino/_. **windows** _C:/Users/USER/Documents/Arduino._
4. Navigate into the `ClusterDuck-Protocol` folder and open `Libraries` folder
5. Copy all the libraries form the `Libraries` folder
6. Paste into into your local Arduino Libraries folder **MacOs** _/Users/USER/Documents/Arduino/_.  **windows** _C:/Users/USER/Documents/Arduino._
7. Open Arduino IDE
8. You should now be able to see the examples by going to File -&gt; Examples -&gt; ClusterDuck

You should be able pull new commits directly to this folder in your Arduino library.

**Add required libraries**

The required libraries to work with the ClusterDuck protocol can be installed in multiple ways. There is a folder in the source code that is called “Libraries” and contains all the submodules to work with the ClusterDuck Protocol. Or you can download all the libraries manual and import into Arduino by .zip. Some libraries are available in the Arduino Libraries manager.

You should be able pull new commits directly to this folder in your Arduino library.

### Installing libraries through Library Manager

Some Libraries can be installed with the Arduino Library manager.

Go to _Sketch &gt; Include Library &gt; Manage Libraries_:

* Search for LoRa and install _LoRa by Sandeep Mistry_
* Search for u8g2 and install _u8g2 by Oliver_
* Search for ArduinoJson and install _ArduinoJson by Benoit Blanchon_

### Installing libraries by adding .Zip files

To add Libraries by zip files. Go to _Sketch &gt; include Library &gt; add .zip Library…_

Go to the following websites and download the Libraries:

* [adafruit/Adafruit-BMP085-Library: A powerful but easy to use BMP085/BMP180 Library](https://github.com/adafruit/Adafruit-BMP085-Library)
* [adafruit/Adafruit\_BMP280\_Library: Arduino Library for BMP280 sensors](https://github.com/adafruit/Adafruit_BMP280_Library)
* [https://arduinojson.org/v6/doc/installation/](https://arduinojson.org/v6/doc/installation/) Version 6
* [me-no-dev/AsyncTCP: Async TCP Library for ESP32](https://github.com/me-no-dev/AsyncTCP)
* [adafruit/DHT-sensor-library: Arduino library for DHT11, DHT22, etc Temperature & Humidity Sensors](https://github.com/adafruit/DHT-sensor-library)
* [https://github.com/ThingPulse/esp8266-oled-ssd1306](https://github.com/ThingPulse/esp8266-oled-ssd1306)
* [https://github.com/me-no-dev/ESPAsyncWebServer](https://github.com/me-no-dev/ESPAsyncWebServer)
* [https://github.com/FastLED/FastLED](https://github.com/FastLED/FastLED)
* [https://github.com/sandeepmistry/arduino-LoRa](https://github.com/sandeepmistry/arduino-LoRa)
* [https://github.com/swatish17/MQ7-Library](https://github.com/swatish17/MQ7-Library)
* [https://github.com/knolleary/pubsubclient](https://github.com/knolleary/pubsubclient)
* [https://github.com/olikraus/u8g2](https://github.com/olikraus/u8g2)
* [https://github.com/mkarawacki/wavesharesharpdustsensor](https://github.com/mkarawacki/wavesharesharpdustsensor)
* [adafruit/Adafruit\_Sensor: Common sensor library](https://github.com/adafruit/Adafruit_Sensor)
* [Arduino-timer](https://www.arduinolibraries.info/libraries/arduino-timer) Version 2.0.1
* [espressif/arduino-esp32: Arduino core for the ESP32](https://github.com/espressif/arduino-esp32)

## Load the Heltec ESP32 Board to your Arduino IDE:

In Arduino IDE, select _Tools &gt; Board &gt; Boards Manager_, and in the pop up window type “esp32” into the search field. You should see the “esp32 by Espressif Systems” library. Install this library.

Once the board library is installed, you are ready to use the Arduino IDE.

### Install The firmware

DuckLink Hardware and Firmware Assembly

1. Connect ESP32 board to your computer via USB cable.

   ![Connected ESP32 board](https://www.project-owl.com/assets/wiki/esp32.jpg)

2. In Arduino IDE, select Tools &gt; “board” to Heltec\_WiFi\_LoRa\_32

   ![Select the correct board](https://www.project-owl.com/assets/wiki/arduino_heltec.png)

3. In Arduino IDE, select Tools &gt; “port” to 

   ![Select the correct port](.https:/www.project-owl.com/assets/wiki/arduino_port.png)

4. Select Duck:

   At this point you will need to choose what kind of Duck you want to make. There are Examples for different Ducks included in the ClusterDuck Protocol. Go to File -&gt; Examples -&gt; ClusterDuck.

   ![Using Cluster Duck examples](https://www.project-owl.com/assets/wiki/images/arduino_examples.png)

```text
**Choose an Example File** 

_Note: every ClusterDuck network needs at least 1 MamaDuck and 1 PapaDuck_


**MamaDuckExample:** Choose a DuckID and modify the code for your needs for api references and more explanation see down below or go to [GitHub](https://github.com/Code-and-Response/ClusterDuck-Protocol)


**PapaDuckExample:** For the papa you need to setup a WiFi connection 

    #define SSID        ""
    #define PASSWORD    ""

Setup your SSID and Password between the “” in the code.

You can setup your own MQTT server or connect to the OWL DMS (Coming Soon!) here:

    #define ORG         ""          // "quickstart" or use your organisation
    #define DEVICE_ID   ""
    #define DEVICE_TYPE "PAPA"
    #define TOKEN       ""

    char server[]           = ORG ".messaging.internetofthings.ibmcloud.com";
    char topic[]            = "iot-2/evt/status/fmt/json";
    char authMethod[]       = "use-token-auth";
    char token[]            = TOKEN;
    char clientId[]         = "d:" ORG ":" DEVICE_TYPE ":" DEVICE_ID;
```

1. Upload the firmware

   Finally, upload this code to the Duck device by hitting the right-pointing arrow in the top left corner.

   ![Upload firmware](https://www.project-owl.com/assets/wiki/arduino_upload.png)

```text
This will show a lot of activity in the console, and if successful will say complete. If this process fails for any reason, contact us and we can help debug whatever is going wrong.

Disconnect the USB cable and connect the battery to the board.

If everything worked properly, the OLED screen on the board may light up and you should see the Wifi network available if you check wifi settings on your phone or computer.

Finished Duck:

![Running duck example](https://www.project-owl.com/assets/wiki/setup.png "Running duck example")
```

1. Upload the firmware OTA

   Once you uploaded the firmware via cabel, you can do this also **O**ver**T**he**A**ir. Connect to ducks wifi an then ther are two ways to continue:

   **Upload via IDE**

   In Platform IO uncommend the "upload\_port = duck.local" line in .ini File and use the normal Upload butten \(the white arrow at the bottom\).

   In Adruino IDE you can upload your sketch under Tools-&gt;Port-&gt;\(under the Serial Port Section is the networkn sektion\).

   **Upload the Binary to Capativ Portal**

   To upload to the Capativ Portal first you need to build a binary file. Then open "duck.local/firmware" and upload the binary.

   To create the binary with Platform IO comile your code \(the white hook at the bottom\). Then you find the binary in the build folder \(/.pio/build//firmware.bin\).

   To create the binary with Adruino IDE select Sketch-&gt;Export Compiled Binary. You will find this next to your sketch.

