# ESP-Mesh-Network
## What is a mesh network?
A mesh network is a network in which devices -- or nodes -- are linked together, branching off other devices or nodes. These networks are set up to efficiently route data between devices and clients. They help organizations provide a consistent connection throughout a physical space.
Nodes in a network are programmed with software that tells the node how to handle information and interact with the network.
Mesh networks use routing or flooding techniques to send messages. In routing, a message hops from node to node to get to its destination. The mesh network must have continuous connections and reconfigure itself if a path is broken, using self-healing algorithms. There will often be more than one path between a source and a destination.
Mesh networks enable many devices to share internet connectivity, and for devices to communicate directly without first going through the internet. The utility of a mesh network over other network types, such as a hub and spoke network, is that if a node is too far away from the hub, it can still communicate via a closer node until it reaches a router.
## What is ESP8266 NodeMCU ?
NodeMCU is an open-source Lua based firmware and development board specially targeted for IoT based Applications. It includes firmware that runs on the ESP8266 Wi-Fi SoC from Espressif Systems, and hardware which is based on the ESP-12 module.
* NodeMCU ESP8266 Specifications & Features: 
* Microcontroller: Tensilica 32-bit RISC CPU Xtensa LX106
* Operating Voltage: 3.3V
* Input Voltage: 7-12V
* Digital I/O Pins (DIO): 16
* Analog Input Pins (ADC): 1
* UARTs: 1
* SPIs: 1
* I2Cs: 1
* Flash Memory: 4 MB
* SRAM: 64 KB
* Clock Speed: 80 MHz
* USB-TTL based on CP2102 is included onboard, Enabling Plug n Play
* PCB Antenna
* Small Sized module to fit smartly inside your IoT projects
## Demostration:
* Step_1 :
#### Intro to painlessMesh:
painlessMesh is a library that takes care of the particulars of creating a simple mesh network using esp8266 and esp32 hardware.  The goal is to allow the programmer to work with a mesh network without having to worry about how the network is structured or managed.

#### True ad-hoc networking
painlessMesh is a true ad-hoc network, meaning that no-planning, central controller, or router is required.  Any system of 1 or more nodes will self-organize into fully functional mesh.  The maximum size of the mesh is limited (we think) by the amount of memory in the heap that can be allocated to the sub-connections buffer and so should be really quite high.

#### JSON based
painlessMesh uses JSON objects for all its messaging.  There are a couple of reasons for this.  First, it makes the code and the messages human readable and painless to understand and second, it makes it painless to integrate painlessMesh with javascript front-ends, web applications, and other apps.  Some performance is lost, but I haven’t been running into performance issues yet.  Converting to binary messaging would be fairly straight forward if someone wants to contribute.

#### Wifi & Networking
painlessMesh is designed to be used with Arduino, but it does not use the Arduino WiFi libraries, as we were running into performance issues (primarily latency) with them.  Rather the networking is all done using the native esp32 and esp8266 SDK libraries, which are available through the Arduino IDE.  Hopefully though, which networking libraries are used won’t matter to most users much as you can just include painlessMesh.h, run the init() and then work the library through the API.

#### painlessMesh is not IP networking
painlessMesh does not create a TCP/IP network of nodes. Rather each of the nodes is uniquely identified by its 32bit chipId which is retrieved from the esp8266/esp32 using the system_get_chip_id() call in the SDK.  Every node will have a unique number.  Messages can either be broadcast to all of the nodes on the mesh, or sent specifically to an individual node which is identified by its `nodeId.

#### Installation 
