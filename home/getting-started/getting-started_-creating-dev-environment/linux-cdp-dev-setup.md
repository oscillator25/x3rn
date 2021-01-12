# Linux-CDP-Dev-Setup

### This guide will help you successfully get a Linux dev environment up and running:

#### Preferred method of setup \(Script Install\):

1. First please get [Arduino IDE](https://www.arduino.cc/en/main/software) Installed. Once you have it successfully installed please open and run it just one time and close it out, This populates some folders and required pieces.
2. Now you have the IDE installed, you will now need to install Python 3 and make it your default Python on your machine. You can do this by running the following in your terminal: `sudo apt-get install python3 python3-pip python3-setuptools` \| Now make Python 3 the default interpreter is possible by running:`sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 10>` **Note:You must logout of your account and back in for this to take effect**
3. Great now we have Python 3 and Arduino IDE installed we are getting closer to completing the environment setup. You will need to install PySerial a dependency for CDP. Install it by running this in a terminal: `pip3 install pyserial`

#### Install and run ClusterDuck\_Automator\_for\_Linux:

1. Next, install the ClusterDuck\_Automator\_for\_Linux script. The git clone will install the check\_ClusterDuck\_dependencies bash script. The first time it's run it will create the install\_ClusterDuck\_libraries bash script. Just some script magic to make it clear what to run to check things and to install things. Eventually, it might even have a update\_ClusterDuck\_libraries script but not today. Eventually, the script will exist somewhere within the Project Owl repositories but for now.

   `git clone git@github.com:dmandala/ClusterDuck_Automator_for_Linux.git`

2. Now you need to run the script. It should be executable, but if it happens it is not yet executable you can solve this by doing:

   `chmod u+x check_ClusterDuck_dependencies`

   Once you have done that run the script in a terminal by:

   `./check_ClusterDuck_dependencies`

   The output will tell you if you have a clean environment with all the necessary pieces in place. Resolve any missing software errors by installing them using your distro's tools. Once that is done you can now proceed to the install of the ClusterDuck-Protocol libraries.

#### Install ClusterDuck-Protocol libraries :

1. To install run the script install\_ClusterDuck\_libraries like this:

   `./install_ClusterDuck_libraries`

2. The script will clone the latest CDP down and set up all necessary libraries in the proper places. Once that has completed you are now ready to use the Clusterduck Protocol libraries and flash some ducks.

### Manual Install for Linux DEV setup:

**This section is to do a manual install in case the preferred method above failed**

#### Dependency Setup:

1. First please get [Arduino IDE](https://www.arduino.cc/en/main/software) Installed. Once you have it successfully installed please open and run it just one time and close it out, This populates some folders and required pieces.
2. Now you have the IDE installed, you will now need to install Python 3 and make it your default Python on your machine. You can do this by running the following in your terminal: `sudo apt-get install python3 python3-pip python3-setuptools` \| Now make Python 3 the default interpreter is possible by running:`sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 10>` **Note: You must logout of your account and back in for this to take effect**
3. Great now we have Python 3 and Arduino IDE installed we are getting closer to completing the environment setup. You will need to install PySerial a dependency for CDP. Install it by running this in a terminal: `pip3 install pyserial`
4. Now in order to get ESP32 Boards populated please goto your Arduino IDE and go to Preferences. \*Install Board Manager URLs: if you already have a URL in there go to the end, add a comma and then add your URL. If nothing is in the box and it is empty “Additional Boards Manager URLs” please add the following string: [https://dl.espressif.com/dl/package\_esp32\_index.json,https://adafruit.github.io/arduino-board-index/package\_adafruit\_index.json](https://dl.espressif.com/dl/package_esp32_index.json,https://adafruit.github.io/arduino-board-index/package_adafruit_index.json)
5. Once you have done that you need to select Tools &gt; Board &gt; Boards Manager, and in the pop-up window type “esp32” into the search field. You should see the “esp32 by Espressif Systems” library. Install this library.

#### Github Setup:

1. Open up a terminal or a git command prompt and make sure your are in the Arduino IDE libraries folder.
2. Clone the ClusterDuck Protocol onto your local machine `git clone https://github.com/Code-and-Response/ClusterDuck-Protocol.git`
3. Next CD into the ClusterDuck-Protocol directory or open it manually
4. All the library folders in CDP libraries are empty. In order to populate them you need to run the following command `git submodule update --init --recursive`
5. Once you have that done and the libraries are populated you need to take them all and copy them one directory back to the Arduino libraries folder.

Now Enjoy and Go Flash Ducks!

## FAQS:

1. ser\_open\(\): can't open device "/dev/ttyACM0": Permission denied error. In order to solve this issue, you must give permissions to use the serial ports. You can do that with the following commands: `sudo usermod -a -G dialout $USER` or `sudo chmod a+rw /dev/tty*` replace \* with your USB Port. Logout and re-login may be required to apply this change.

   On Arch Linux this is done slightly differently by adding the user to uucp group with the following command: `sudo usermod -a -G uucp $USER`

2. How do I know what version of Python is defaulting on my machine? Run `which python` if you get Python2\* whatever version that is no good you need python3 so follow the instructions above

