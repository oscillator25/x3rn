# Firmware

To create a basic clusterduck \(network of ducks\) all you need is a PapaDuck and a MamaDuck. We will go over how to do set up this basic clusterduck.

1. Select Duck:

   At this point you will need to choose what kind of Duck you want to make. There are Examples for different Ducks included in the ClusterDuck Protocol. Go to File -&gt; Examples -&gt; ClusterDuck.

   ![Using Cluster Duck examples](https://www.project-owl.com/assets/wiki/arduino_examples.png)

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

   Once you uploaded the firmware via cable, you can do this also **O**ver**T**he**A**ir. Connect to ducks wifi an then there are two ways to continue:

   **Upload via IDE**

   In Platform IO uncomment the "upload\_port = duck.local" line in .ini file and use the normal Upload button \(the white arrow at the bottom\).

   In Arduino IDE you can upload your sketch under Tools-&gt;Port-&gt;\(under the Serial Port Section is the network section\).

   **Upload the Binary to Captive Portal**

   To upload to the Captive Portal first you need to build a binary file. Then open "duck.local/firmware" and upload the binary.

   To create the binary with Platform IO compile your code \(the white hook at the bottom\). Then you find the binary in the build folder \(/.pio/build//firmware.bin\).

   To create the binary with Arduino IDE select Sketch-&gt;Export Compiled Binary. You will find this next to your sketch.

