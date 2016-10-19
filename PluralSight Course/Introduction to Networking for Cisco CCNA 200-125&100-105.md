## Introduction to Network for Cisco CCNA 200-125/100-105
[Network Communication Models](#Network Communication Models)  
[Encapsulation](#Encapsulation)  
[Data Networking And Addressing](#Data Networks and Addressing)  

### Network Communication Models

| | |
|---|---|
|Media|Wires/Radio/Glass|
|Local|Ethernet|
|Global|Internet Protocol|
|Cues | TCP|
|Data | Website/Email|


##### TCP
- A 3-way handshake:
  1. From Sender - **SYN** - I want to make a connection to transfer data
  2. From Server - **SYN-ACK** - I'm available for transfer for data
  3. From Sender - **ACK** - OK, I'm about to send data  

#### Internet Protocol (IP)
- In order to send a message to another device, it must have an identifiable address
- Global addressing scheme

#### Ethernet
 - In order to send to another device locally, we must have a local addressing scheme; In this case the **MAC Address**
 - In order to send messages from one device IP to another, the intermediary devices will use MAC Addresses to at each step of the way to get there.

#### Wires/Radio/Glass
 - Devices need to be connected to each other by some means to communicate.

#### OSI Model vs TCP/IP Model
|TCP/IP Model |OSI Model |Example|
|---|---|---|
|Network Interface |Physical |Wires/Radio/Glass|
||Data Link |Ethernet|
|Internet |Network|Internet Protocol|
|Transport |Transport | TCP|
|Application |Session |SSL|
| |Presentation|Citrix ICA|
| |Application | Website/Email|
 - Will be mostly concerned with the top 4 layers (Physical, Data Link, Network, Transport)

### Encapsulation

#### OSI Model
 |||
 |---|---|
 |7 |Application|
 |||
 |||
 |4 |Transport|
 |3 |Network|
 |2 |Data Link|
 |1 |Physical|

 #### 7 - Application Layer
  - Data at this layer tends to be big. It will need to be broken up into chunks and placed into the payload of the transport layer

#### 4 - Transport Layer
 - **Segment:** A chunk of data with a trasnport layer header  

TCP Header Exmaple:  

|Source Port |Destination Port |Flags |Seq # |Ack # |Payload|
|---|---|---|---|---|---|

#### 3 - Network/Internet Layer
 - **Packet:** A chunk of data with a network layer Header

 IP Header Example:

 |Source IP Address | Destination IP Address |TTL | Other | Segment/Payload|
 |---|---|---|---|---|

#### 2 - Data Link/Network Interface Layer
 - **Frame:** A chunk of data, with a Data Link layer header.

  Ethernet Header Example:  

|Destination MAC Address| Source MAC Address |Layer 3 Protocol |Packet/Payload|
|---|---|---|---|

#### 1 - Physical Layer  
 - Converted to bits and then sent across physical medium (RF, copper, fiber, etc)  

### Data Networks and Addressing  
#### Addressing the Network
 - MAC Address: 48 bit unique identifier for every device that can be connected to a network. Written in hexadecimal format. Used for local communication.
 - Split into two halves - Manufacturer ID & Serial Number
 - Example MAC address: 000C:29FC:70A5

#### How Local Communication Works
 - Routers divide Networks
  - A frame can only be sent over a single network

#### How Global Addressing Works
 - In order to communicate to outside networks, IP addresses are assigned.
 - To communicate with an outside network, a packet with the required destination address will be encapsulated in a frame addressed to the router/default gateway. The router will then remove the packet from the frame and encapsulate it in a new frame to pass it along to the next router. This will repeat until it reaches the local network of the destination IP address.

#### IP Networks
 - Subnet mask separates IP addresses into network portion and host portion
 - Network portion represents a group of devices, host portion represents an individual devices
 - The function of router is to forward traffic from network to another
