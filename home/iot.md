# Setting up the IBM Watson IoT Platform

In order for the PapaDuck to communicate with the internet, you need to create a device in the IBM Watson IoT Platform. Creating a device allows you to connect your an IoT device \(in this case, the PapaDuck\) to IBM Watson. You are telling IBM Watson to let the device connect to the internet and receive its data.

Follow these steps to connect a device to IBM Watson IoT Platform 1. Create an IBM Cloud account through [this link](https://ibm.biz/BdqiVW). Fill out all the required information and confirm your email address. 1. Follow this link to provision an instance of the [IBM Watson IoT Platform](https://cloud.ibm.com/catalog/services/internet-of-things-platform). Note: you can also find this by [browsing through the catalog](https://cloud.ibm.com/catalog). 1. Make sure the Lite plan is selected and click `Create`. You can change the `Service Name` if you want to, but it's not required.

```text
![iot-platform-3](https://www.project-owl.com/assets/wiki/iot-platform-3.png)
```

1. After the service provisions, click `Launch`.

   ![iot-platform-4](https://www.project-owl.com/assets/wiki/images/iot-platform-4.png)

2. Click `Add Device`.

   ![iot-platform-5](https://www.project-owl.com/assets/wiki/iot-platform-5.png)

3. Enter your `Device Type` and `Device ID`, then click `Next`.

   ![iot-platform-6](https://www.project-owl.com/assets/wiki/iot-platform-6.png)

4. Filling out anything in the `Device Information` tab is optional, click `Next`.

   ![iot-platform-7](https://www.project-owl.com/assets/wiki/iot-platform-7.png)

5. Leave the field for `Authentication Token` blank, as one will be generated automatically. You can specify your own if you prefer. Click `Next`.

   ![iot-platform-8](https://www.project-owl.com/assets/wiki/iot-platform-8.png)

6. Ensure that the `Summary` page looks good, then click `Finish`.

   ![iot-platform-9](https://www.project-owl.com/assets/wiki/iot-platform-9.png)

7. You'll see the authentication token listed, ensure that you do not misplace it, otherwise, you will have to regenerate a new token.

   ![iot-platform-10](https://www.project-owl.com/assets/wiki/iot-platform-10.png)

8. Open `PapaDuckExample.ino` and replace `ORG`, `DEVICE_ID`, `DEVICE_TYPE`, and `TOKEN` with the information from the summary screen. Make sure you also have the correct WiFi SSID and password filled out in that file as well. After you flash the duck with this information, you'll see data flowing through the IBM Watson IoT Platform.

![iot-platform-11](https://www.project-owl.com/assets/wiki/iot-platform-11.png)

