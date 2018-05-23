# IOT
In this IOT demo, I have implemented the data flow from Sensors(MQTT)  to the Big Data Platform( HDF+HDP) using Nifi and Kafka.

The idea is to transmit the sensor data into Bigdata Platform and perform real time analytics on top of streaming data. Currently, I have finished up building the Big Data environment by installing Hortonworks Data Platform and Hortonworks Data flow on an Ubuntu Machine and executed the IOT demo from Sensor side to the Big Data Platform with including networking between these two platforms. Initially built HDP for Big Data Analytics but after IOT buzz, I have Integrated HDP 2.6.4 (Hortonworks Data Platform) with HDF 3.1(Hortonworks Data Flow). HDF has good ecosystem which has Nifi (Flow file), Storm (can analyze huge amount of Data), Druid (Real time Dashboards) and Kafka (Robust Message broker).

Here I will divide this entire Demo into two parts.
1.	Sensor side (We have Sensor with Raspberry Pi in Michigan)
2.	Big Data Platform (HDP + HDF) in Ohio.



After a good research I found that MQTT is light weight on the Sensor side as well as MQTT control packet headers are kept as small as possible. Each MQTT control packet consist of three parts, a fixed header, variable header and payload. Each MQTT control packet has a 2-byte Fixed header. Not all the control packet has the variable headers and payload. A variable header contains the packet identifier if used by the control packet. A payload up to 256 MB could be attached in the packets. Having a small header overhead makes this protocol appropriate for IoT by lowering the amount of data transmitted over constrained networks
