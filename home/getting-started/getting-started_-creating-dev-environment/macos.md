# macOS CDP Dev Environment Setup:

By following the steps below you can get a macOS Dev environment up and running in no time"

1. Download and install the Arduino IDE by Followings instructions from [MacOS Arduino Gudie](https://www.arduino.cc/en/guide/macOSX)
2. Install the Silicon Labs USB to UART Bridge VCP Driver From [Downloads Page](http://www.silabs.com/Support%20Documents/Software/Mac_OSX_VCP_Driver_10_6.zip) **Make sure Silicon Labs has the necessary security preferences. \(go to System Preferences -&gt; Security and Privacy -&gt; General and allow Silicon Labs\).**
3. Install the ESP32 core Library by opening the Arduino IDE and go to \[Preferences\]. In \[Additional Boards Manager URLs\] add the following string: [https://dl.espressif.com/dl/package\_esp32\_index.json,https://adafruit.github.io/arduino-board-index/package\_adafruit\_index.json](https://dl.espressif.com/dl/package_esp32_index.json,https://adafruit.github.io/arduino-board-index/package_adafruit_index.json) **If there is already a URL inside this box go to the end add a comma and then this URL**
4. Next, you will need to load the Heltec ESP32 Board to your Arduino IDE

   From Arduino IDE menu, select \[Tools\] &gt; \[Board\] &gt; \[Boards Manager\] Search for "esp32". You should see the "esp32 by Espressif Systems" library. Install this library.

5. To run the script open a terminal cd into where you stored the script and run type the following: `./cdp-install-osx.sh <github_username>`

## FAQS

