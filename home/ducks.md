# Duck Family

Historically there have been three types of ducks, however over time it really has become primarily two types of ducks in use with a specialized third type for extreme low power use. The historic types are: papa, mama and ducklink, They form a partially-connected mesh network that in some ways can resemble a tree topology. The current recommendation is to use only two types of ducks: papa and mama. The reason is that the ducklinks only send messages, they don’t relay messages and they don’t receive messages. If you need an extreme low power duck that conserves power, sleeps, wakes ureads some sensors and then sends the data use the Ducklink style duck. For most use the mama duck is the primary platform. In order to understand the types of ducks it’s important to have some understanding of the Cluster Duck Protocol on the mesh.

## How does the mesh work currently.

### Papa Duck function on the mesh

The papa duck is the uplink, it receives messages from the mesh from any source, and uplinks them out of the mesh either into the Internet, to a local lan or to a blind serial port. That is their primary function. They could have some sensors or a GPS etc. But they do not relay data in the mesh, only uplink data out of the mesh. Warning DO NOT OVERLOAD the mesh, if the mesh gets overloaded, messages can be lost. Mama Duck functions on the mesh The mama duck is an interesting device, it serves many functions, it’s first primary function is a mesh reflector, that is it receives messages from the mesh and if it has not already seen the message it will forward it on the mesh. If it has already seen the message it drops the message and does not forward it a second or more times.

A second function of the mama duck is a captive web portal, where it can display a web page via WiFi and when the page is filled out and submitted back to the duck, it can compress the data \(or not\), create an message and send it out into the mesh to eventually find the papa duck and be uplinked out of the mesh. Other possible functions of the mama duck are sensors of almost any type from location \(GPS\) temperature, humidity, moisture, air quality, etc. The duck can read the sensors and create a message from the data, and again send it out to the mesh to eventually find the papa duck and be uplinked out of the mesh. The mesh is currently LoRa only but this may change. There are many variants of the primary types of duck \(papa, mama\). Any duck type can have GPS, Real Time Clock or sensors installed, though in most cases the mama gets sensors captive portal, etc. Any duck type can use mains power, battery power, solar, wind or a mix of power sources. Some ducks are optimized for battery or solar operations as they are expected to be in the field when mains power is out and they may be downgraded to a duckling to reduce power comsumption. Any duck can be placed in a waterproof container and made to float, or may be tethered in trees when infrastructure is missing from emergency events. The types are described below.

## Papa Duck

A papa duck is the end of the cluster duck mesh network and uploads the data into either an MQTT server or a local PC via serial port blind data dump. The MQTT server can be in the cloud, on a local PC, it doesn't really matter. You must have at least 1 papa duck for the Cluster Duck Protocol to function and have data uploaded out of the Cluster Duck mesh. Papa ducks receive data from Mama ducks or ducklings, it is immediately uploaded out of the mesh network. The connection to the real world can be hardwired Ethernet, WiFi, or serial port depending on type of hardware. Papa ducks are the up-link from the mesh network to the rest of the world. If you have more than one papa duck in the mesh it is quite possible that you will get duplicate messages because of how the mesh works so be prepared to have to de-duplicate your database or serial data stores. Known Papa Duck Types: MQTT Server uplinks, or mesh to TCP/IP networks Papa Duck – mesh to TCP/IP Network/Internet. There is a Papi variant that does mesh to local lan, the code bases should be merged, there is very little difference in the code bases.

**Iridium Duck** – mesh to satellite data to the Internet. Also known as the “Dish Duck”.

**Cell Duck** – mesh to TCP/IP network via GSM or LTE or LTE/IoT data.

### Serial uplinks

**Papi Duck** – mesh to blind serial out to local PC.

## Mama Duck

A mama duck is the mesh hub of the cluster duck protocol and moves data eventually towards a papa duck, data may hop between several mama ducks before finally getting to a papa duck. Mama ducks are cluster points for ducklings if used \(ducklings are never relays\) and Mama ducks can have a WiFi radio and serve web pages via it’s captive web portal and can have a wide range of sensors installed. They send the submitted data into the mesh, also they relay data further into the mesh to eventually to the papa duck to uplink out of the mesh. Known Mama Duck Types: Mama Duck – mesh to mesh network relay, may have a WiFi radio for captive portal but can be turned off to conserve power.

**DiscoDuck** – optimized to be used where cellular and WiFi is saturated. Provides two way communication using an Android chat app.

**Porta Duck** – heavily optimized for handheld battery operations.

**ClusterFlock** – Ducklings attached to a drone for aerial deployment.

**DuckDuck** – Ducklings optimized to be in the air \(drone\) and/or dropped in water.

**GPS** – Duckling optimized for location servers with GPS.

**Space Duck** – Optimized with sensors, may not have a WiFi captive portal.

**HopsLink** – DuckLinks with sensors optimized for beer delivery.

**BluDuck** – optimized to use Bluetooth instead of WiFi for captive portal.

## Ducklink

Link ducks or Ducklinks are a source of data at the edge of the Cluster Duck protocol. They are not normally used anymore, they may have captive portals, sensors of many kinds, including sensors to detect distance to the nearest mama duck or papa duck. Ducklinks connect to mama ducks and pass data to them, or if within range of a papa duck pass data directly to the papa duck. They do not cross connect to any other Ducklinks. They are normally used when it is important to conserve power.

**Ducklink** – Has onboard WiFi captive portal, relays data from captive portal to nearest mama duck. Can have any kind of sensor installed but is normally used when extreme low power consumption is needed, the duck may be put to sleep when not reading sensors to conserve power. Detector Duck – Designed to detect LoRa signal to assist deploying more mama ducks to expand the mesh. Will only detect mama and papa ducks, not other ducklings. This duck does not normally send data into the mesh, it is used by humans to determine where to deploy more mama ducks to increase the mesh.

