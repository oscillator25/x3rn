# Duck-Projects

## DetectorDuck

When the CDN is up and running, how would you know if you are in range of the network? The solution is the DetectorDuck. A DetectorDuck can detect other Ducks close by. It uses an innate feature of a Duck that calculates a value called the Received Signal Strength Indicator \(RSSI\). The RSSI value tells how strong a signal is being received. If the RSSI is low, then the signal is weak and if it is high, then the signal is strong. Based on the RSSI value, a DetectorDuck can turn green \(great signal\), purple \(good signal\), red \(fair signal\), and blue \(no signal\).

![DETECTRO DUCK](https://www.project-owl.com/assets/detector_vector.gif)

There are a lot of benefits of the DetectorDuck. One of them is when setting up the CDN. it can be difficult to figure out where to deploy a Duck in the field. When deploying a Duck, we need to make sure it is connected fairly well with nearby Ducks. That is where the DetectorDuck comes in and makes sure that Ducks receive adequate signal from other nearby Ducks. It works by broadcasting a ping every 3 seconds and calculates the RSSI value of the pong of the nearest Duck device.

## SensorDuck

The SensorDuck is a special type of DuckLink that has a specific sensor attached to itself. The purpose of the SensorDucks are to deliver data regarding its environment using the sensors attached to itself. The idea is to use sensors to detect any anomalies that indicate a possible disaster so we can be better prepared. There are few SensorDucks already created:

[BMP180](https://github.com/Code-and-Response/ClusterDuck-Protocol/tree/master/examples/BMP180Example): collects weather data such as temperature and pressure.

[BMP280](https://github.com/Code-and-Response/ClusterDuck-Protocol/tree/master/examples/BMP280Example): collects weather data such as temperature and pressure. \(upgrade from the BMP180\)

[GP2Y](https://github.com/Code-and-Response/ClusterDuck-Protocol/tree/master/examples/DustSensorExample): senses the air quality; how much dust in the air

[DHT11](https://github.com/Code-and-Response/ClusterDuck-Protocol/tree/master/examples/DHT11Example): senses the temperature and humidity in the air

[MQ7](https://github.com/Code-and-Response/ClusterDuck-Protocol/tree/master/examples/MQ7Example): senses five different gases \(H2, LPG, CH4, CO, EtOH\)

\[ADXL335\]: measures the acceleration in the x, y, z direction

## DishDuck

Before the DishDuck, the ClusterDuck Network operated where the DuckLinks, MamaDucks, and PapaDucks communicate data with each other using LoRa. To get that data, the PapaDuck has to be connected to the internet so it can push up the data for access. What happens when the PapaDuck loses its connection to the internet? The DishDuck.

The DishDuck is a PapaDuck with an additional device attached to itself called the RockBlock 9603. The RockBlock acts like a modem for the Iridium Network which is a network of 66 satellites in the earth’s orbit. So when the DishDuck loses internet connection, it can use the RockBlock to transmit data to the satellite using Short-Burst Data. With the DishDuck, a combination of the PapaDuck and RockBlock, we can now retrieve our sensor data from anywhere in the world without relying on internet or GSM connectivity.

[Getting Started with DishDuck](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/DishDuck)

![](https://www.project-owl.com/assets/iridium_explain.jpg)

