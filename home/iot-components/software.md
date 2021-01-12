# Software

The ClusterDuck Protocol is an Arduino Library developed for ESP32 development boards. To compile and upload the firmware to your arduino board you need a development environment. We recommend using the Arduino IDE or the PlatformIO extension for your preferred editor.

## Arduino IDE

Arduino IDE is a great place to start. Download the Arduino IDE here and get started.

1. Download the [Arduino IDE](https://www.arduino.cc/en/Main/Software).
   * **For MacOS**: You need to install the [USB to UART Bridge VCP Driver](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers) to connect to your development board.

     Once installed, make sure Silicon Labs has the necessary security preferences. \(go to System Preferences -&gt; Security and Privacy -&gt; General 

     and allow Silicon Labs\).
2. Install the ESP32 core Library
   * Once installed open the Arduino IDE and go to Preferences.

     \*Install Board Manager URLs: if you already have a URL in there go to the end, add a comma and then add your URL.

   * If nothing is in the box and it is empty “Additional Boards Manager URLs” please add the following string: `https://dl.espressif.com/dl/package_esp32_index.json,https://adafruit.github.io/arduino-board-index/package_adafruit_index.json`
3. Load the Heltec ESP32 Board to your Arduino IDE.
   * In the Arduino IDE, select Tools &gt; Board &gt; Boards Manager, and in the pop-up window type “esp32” into the search field. You should see the “esp32 by Espressif Systems” library. Install this library.

### Add the necessary libraries

The next step will be installing the ClusterDuck Protocol and its required libraries. To do this you can clone the CDP onto your local machine or download the library as a .zip file and add it manually.

#### Clone the ClusterDuck Protocol on your Local Machine.

1. Open up a terminal or a git command prompt
2. Clone the ClusterDuck Protocol onto your local machine `git clone https://github.com/Code-and-Response/ClusterDuck-Protocol.git`
3. Next CD into the ClusterDuck-Protocol directory or open it manually
4. Pull all the Library submodules needed for the Arduino IDE `git submodule update --init --recursive`
5. Copy the `ClusterDuck-Protocol`folder into your local Arduino Libraries folder **MacOs** _/Users/USER/Documents/Arduino/libraries_. **windows** _C:/Users/USER/Documents/Arduino/libraries._
6. Navigate into the `ClusterDuck-Protocol` folder and open the `Libraries` folder
7. Copy all the libraries form the ClusterDuck-Protocol `Libraries` folder
8. Paste it into your local Arduino IDE Libraries folder **MacOs** _/Users/USER/Documents/Arduino/libraries_.  **windows** _C:/Users/USER/Documents/Arduino/libraries._
9. Open Arduino IDE
10. You should now be able to see the examples by going to File -&gt; Examples -&gt; ClusterDuck

You should be able to pull new commits directly to this folder in your Arduino library.

#### Importing as a .zip

You can also add the CDP to the Arduino IDE manual by downloading the CDP as a zip here:

In the Arduino IDE, navigate to _Sketch &gt; Include Library &gt; Add.ZIP Library_. At the top of the drop-down list, select the option to "Add.ZIP Library".

![add library to arduino](https://www.project-owl.com/assets/wiki/add_Library.png)

Return to the _Sketch &gt; Include Library menu._ menu. You should now see the library at the bottom of the drop-down menu. It is ready to be used in your sketch. The zip file will have been expanded in the _libraries_ folder in your Arduino sketches directory.

Now you have the CDP installed you will need to install its required libraries by manually adding the zip files.

In the next step, you will need to download the zip files of the required libraries.

_note some example files need extra libraries that are linked in the example's directory_

* [https://arduinojson.org/v6/doc/installation/](https://arduinojson.org/v6/doc/installation/) Version 6
* [me-no-dev/AsyncTCP: Async TCP Library for ESP32](https://github.com/me-no-dev/AsyncTCP)
* [https://github.com/ThingPulse/esp8266-oled-ssd1306](https://github.com/ThingPulse/esp8266-oled-ssd1306)
* [https://github.com/me-no-dev/ESPAsyncWebServer](https://github.com/me-no-dev/ESPAsyncWebServer)
* [https://github.com/knolleary/pubsubclient](https://github.com/knolleary/pubsubclient)
* [https://github.com/olikraus/u8g2](https://github.com/olikraus/u8g2)
* [Arduino-timer](https://www.arduinolibraries.info/libraries/arduino-timer) Version 2.0.1
* [espressif/arduino-esp32: Arduino core for the ESP32](https://github.com/espressif/arduino-esp32)
* [IridiumSBD by Mikalhart: Rockblock library](https://github.com/mikalhart/IridiumSBD.git)

To add more Libraries go back to _Sketch &gt; include Library &gt; add .zip Library…_

### DuckLink Hardware Assembly

1. Connect ESP32 board to your computer via USB data cable.

   ![Connected ESP32 board](https://www.project-owl.com/assets/wiki/esp32.jpg)

2. In Arduino IDE, select Tools &gt; “board” to Heltec\_WiFi\_LoRa\_32

   ![Select the correct board](https://www.project-owl.com/assets/wiki/arduino_heltec.png)

3. In Arduino IDE, select Tools &gt; “port” to 

You are almost there. So far you downloaded Arduino IDE and the necessary files to get CDP working. What is left is uploading the firmware to the Ducks.

#### Prepare the firmware

## PlatformIO

PlatformIO has its own IDE but what we use is the extension. This allows us to use our own favorite code editor to write firmware which is great! We don't have to download an IDE for each new tech hobby we have.

### Installing ClusterDuck-Protocol global

1. From the [PIO Home](https://docs.platformio.org/en/latest/integration/ide/vscode.html#setting-up-the-project) tab select `Libraries`
2. Search for `ClusterDuck Protocol` and install it

### Installing ClusterDuck-Protocol for project only

1. Create a `New Project` from the [PIO Home](https://docs.platformio.org/en/latest/integration/ide/vscode.html#setting-up-the-project) tab
2. Choose a name, select the `Heltec Wifi LoRa 32 (V2) (Heltec Automation)` as board and `Arduino` as framework
3. Open the `platformio.ini` within your newly created project and add `lib_deps = ClusterDuck Protocol` at the end.

\[ClusterDuck Protocol Repository\]: [https://github.com/Code-and-Response/ClusterDuck-Protocol](https://github.com/Code-and-Response/ClusterDuck-Protocol)

