# Getting-Started

## Building a Simple ClusterDuck Network

Here we will go over step-by-step on how to build a simple ClusterDuck Network \(CDN\). A simple CDN consists of only a MamaDuck and a PapaDuck. With these two Ducks, we can generate a small mesh network, send data and collect it. &lt;!--

1. [Acquire ESP32 LoRa Development Boards](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/hardware)
2. [Install Arduino IDE or PlatformIO](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/software)
3. [Install the ClusterDuck Protocol and Its required Libraries](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/firmware)
4. [Upload the Firmware to the Development Boards](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/firmware)
5. Deploy the ClusterDuck Network  

   --&gt;

   **Read the ClusterDuck Protocol**

   [Read the ClusterDuck Protocol \(CDP\)](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki) to get an understanding on what it does and how it achieves it.

## Get the Hardware.

* [List of the hardware we recommend](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/hardware). These are the minimum hardware we used for a simple CDN and it works.
* For a simple CDN, we need two Ducks \(LoRa boards\). \(If you want to create a bigger network, you need to have more boards.\)

## Get the Software

We need a compiler to compile and upload code to each of the Ducks. We recommend Arduino IDE and PlatformIO.

* [Arduino IDE](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/software#arduino-ide)
* [PlatformIO](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/software#platformio)

## Get the Code from ClusterDuck Protocol

1. [Get CDP from Github](https://github.com/Code-and-Response/ClusterDuck-Protocol) by downloading or cloning
   * Download: Click on the green icon labeled "Code" -&gt; click "Download Zip" -&gt; Open zip when it finishes downloading
   * Clone: In terminal run `git clone https://github.com/Code-and-Response/ClusterDuck-Protocol.git`
2. Get the Basic Libraries for the CDP
   * Copy all libraries from the ClusterDuck-Protocol/Libraries folder and paste it into Documents/Arduino/libraries folder

## Setting up the PapaDuck

1. [Read about the PapaDuck](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/ducks#papaduck)
2. Setting up the PapaDuck requires an additional step compared to the other Ducks. Since PapaDuck communicates with the internet, it needs a cloud platform to connect to. We recommend IBM Watson IoT Platform. 
   * [Create IBM Watson IoT Platform](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/IoT#setting-up-the-ibm-watson-iot-platform)
3. Open PapaDuck example code
4. Add your IBM Watson IoT credentials to the PapaDuck code.
   * Navigate to ClusterDuck-Protocol-examples -&gt; PapaDuckExample -&gt; PapaDuckExample.ino
   * Enter IBM Watson IoT Platform credentials inside the quotes. \[Provide IMAGE\]
5. Using a data cable connect a LoRa board to the computer and upload the code into the board
6. Compile the code into the board.

   That is it. Now you have a PapaDuck connected to the internet. Next is building a MamaDuck to complete the simple CDN.

   **Setting up the MamaDuck**

7. \[Read about the MamaDuck\]
8. Open MamaDuck example code

   -Navigate to ClusterDuck-Protocol-examples -&gt; MamaDuckExample -&gt; MamaDuckExample.ino

9. Using a data cable connect a LoRa board to the computer and upload the code into the board
10. Compile the code into the board.

    **And that is it! You should have a working ClusterDuck Network. Once again we went through how to build a simple CDN. If you would like to expand that, then you can add more MamaDucks \(or DuckLinks\) by getting more boards and repeating "Setting up the MamaDuck".**

\[Read about the MamaDuck\]: [https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/ducks\#mamaduck](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/ducks#mamaduck)

