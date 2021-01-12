# Creating-Dev-Environment

The ClusterDuck Protocol can be looked at as an Arduino Library developed for ESP32 development boards. In order to compile and upload the firmware to your Arduino board, you will first need to set up a proper development environment. If you follow this guide or some of our specific operating system pages you should get up and running in no time.

**We now have a working Linux install guide and script as well as for Mac Os please check those pages out if you are using either of those operating systems as the scripts and guides there make for easy install and setup.**

## Manual \(non-script install\) Arduino IDE

1. Download the \[Arduino IDE\].
2. Install the ESP32 core Library:
   * Once you have installed Arduino IDE open the program and go to Preferences ---&gt; Install Board Manager URLs: if you already have a URL in there go to the end, add a comma and then add your URL. If nothing is in the box and it is empty “Additional Boards Manager URLs” please add the following string: `https://dl.espressif.com/dl/package_esp32_index.json,https://adafruit.github.io/arduino-board-index/package_adafruit_index.json`
3. ESP32 Board install for Arduino IDE:
   * In the Arduino IDE, select Tools &gt; Board &gt; Boards Manager, and in the pop-up window type “esp32” into the search field. You should see the “esp32 by Espressif Systems” library. Install this library.

## ClusterDuck Library Install:

The next step will be installing the ClusterDuck Protocol and its required libraries. To do this you can clone the CDP onto your local machine or download the library as a .zip file and add it manually.

1. Open up a terminal or a git command prompt
2. Clone the ClusterDuck Protocol onto your local machine `git clone https://github.com/Code-and-Response/ClusterDuck-Protocol.git`
3. In order to populate the empty CDP library folders, you will need to run this command once cd into the ClusterDuck-Protocol directory `git submodule update --init --recursive`
4. Copy the `ClusterDuck-Protocol`folder into your local Arduino Libraries folder \|**MacOs** _/Users/USER/Documents/Arduino/libraries_.\| \|**windows** _C:/Users/USER/Documents/Arduino/libraries._ \|
5. Navigate into the `ClusterDuck-Protocol` folder and open the `Libraries` folder, then copy all the library folders 
6. Paste it into your local Arduino IDE Libraries folder: \|**MacOs** _/Users/USER/Documents/Arduino/libraries_.\| \|**windows**_C:/Users/USER/Documents/Arduino/libraries._\|
7. Open Arduino IDE
8. You should now be able to see the examples by going to File -&gt; Examples -&gt; ClusterDuck

You should be able to pull new commits directly to this folder in your Arduino library.

## DuckLink Hardware Assembly

1. Connect ESP32 board to your computer via USB data cable.

   ![Connected ESP32 board](https://www.project-owl.com/assets/wiki/esp32.jpg)

2. In Arduino IDE, select Tools &gt; “board” to Heltec\_WiFi\_LoRa\_32 or TTgo T-beam

   ![Select the correct board](https://www.project-owl.com/assets/wiki/arduino_heltec.png)

3. In Arduino IDE, select Tools &gt; “port” to 
4. In Arduino IDE, select File &gt; “Examples” to  and select whichever example code you want to flash
5. In Arduino IDE click the Arrow pointing to the right to verify and flash your duck.

Welcome to CDP you have now flashed your first duck enjoy

