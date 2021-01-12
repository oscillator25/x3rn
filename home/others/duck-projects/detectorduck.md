# DetectorDuck

When the CDN is up and running, how would you know if you are in range of the network? The solution is the DetectorDuck. A DetectorDuck can detect other Ducks close by. It uses an innate feature of a Duck that calculates a value called the Received Signal Strength Indicator \(RSSI\). The RSSI value tells how strong a signal is being received. If the RSSI is low, then the signal is weak and if it is high, then the signal is strong. Based on the RSSI value, a DetectorDuck can turn green \(great signal\), purple \(good signal\), red \(fair signal\), and blue \(no signal\).

![DETECTRO DUCK](https://www.project-owl.com/assets/detector_vector.gif)

There are a lot of benefits of the DetectorDuck. One of them is when setting up the CDN. it can be difficult to figure out where to deploy a Duck in the field. When deploying a Duck, we need to make sure it is connected fairly well with nearby Ducks. That is where the DetectorDuck comes in and makes sure that Ducks receive adequate signal from other nearby Ducks. It works by broadcasting a ping every 3 seconds and calculates the RSSI value of the pong of the nearest Duck device.

