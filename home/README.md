# What is ClusterDuck Protocol?

![](../.gitbook/assets/cdp_logo_small.png)

## What is it?

In 2017 Hurricane Maria, a category-5 hurricane, hit Puerto Rico and wreaked havoc on the island. Not only did it destroy people’s homes but also people’s ways of communicating. Cell towers and generators were destroyed leaving people not able to communicate with anybody. Communication is very crucial during a crisis. Without communications civilians cannot reach out for help nor can responders reach out to civilians for critical, life-saving information.

The [ClusterDuck Protocol](https://clusterduckprotocol.org/) \(CDP\) was created by [Project OWL](https://www.project-owl.com/) to solve this problem. When all infrastructure is down, it restores that 1% of communication that people need to save lives. Civilians can send short messages providing their locations, emergencies, and other information to people who can help them. And local governments and responders can reach out to the public to provide critical information.

Since its creation, the vision for the CDP has grown beyond just servicing people in need after a hurricane to other natural disasters such as earthquakes, wildfires, cellular congestion \(large events\), sensor networks, and more. Project OWL open-sourced this project in March 2020 so that the CDP can reach the communities that need it as fast as possible and continue to explore new implementations.

## How does it work?

To provide communication, the CDP generates an ad-hoc mesh network by deploying IoT devices. We call these devices Ducks and a network of them is called ClusterDuck Network \(CDN\). There are 3 basic types of Ducks at the heart of CDN: [DuckLink](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/ducks#ducklink), [MamaDuck](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/ducks#mamaduck), and [PapaDuck](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/ducks#papaduck).

Civilians connect with DuckLinks \(without the need to have specific hardware or pre-downloaded software\) to submit their emergency message. The DuckLinks communicates that message with the MamaDucks. And the MamaDucks communicate that message with the PapaDuck. The PapaDuck can push the message up to the cloud or store it locally. In the CDN, there are two methods of communication being utilized, WiFi and LoRa. Civilians use WiFi to communicate with the DuckLinks and the Ducks communicate with each other using LoRa technology.

The DuckLinks serve as edge nodes that only transmit data. These function as remote sensors or as additional access points to a [Captive Portal](https://github.com/Code-and-Response/ClusterDuck-Protocol/wiki/Captive-Portal). MamaDucks inherit the same functionality of the DuckLinks, but also receive messages. MamaDucks repeat messages from DuckLinks and other MamaDucks until the message reaches a PapaDuck. PapaDucks are the endpoint of the network where all of the data is collected and can be stored or pushed up to the cloud.

![overview](https://www.project-owl.com/assets/wiki/cdp-explain-gif.gif)

