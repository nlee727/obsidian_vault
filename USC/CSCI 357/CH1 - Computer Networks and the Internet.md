### Nuts and Bolts View
Home Network -> Regional ISP -> Global ISP
- Internet is a recursive network of networks
    - ISP gets their services from other ISPs, and eventually reaching a global ISP
    - A bunch of connected components

Modem - modulation and demodulation 
- Convert analog to digital data and backwards

Communication links
- fiber, copper, radio satellite
- Transmission maximum rate: bandwidth

Protocols - control sending and receiving of messages
- TCP, IP, HTTP, Skype, 801.11 (wifi)

Internet Standards
- RFC: Request for comments 
- IETF: Internet Engineering Task Force
    - Would take one of the RFC that many people are using and they standardize
Must use the same protocol

### A Service View
Infrastructure that provides services to applications
### Protocol
Specific message sent, specific actions taken when the message is received
- Define format, order of messages send and received among network entities, actions taken on message transmission, receipt

## 1.2 The Network Edge
- Two parts of the internet: the network core (ISPs like routers), and network edge (Hosts like clients and servers
- Hosts: clients and servers

- Have to keep in mind bandwidth, and shared or dedicated connection
### Access Network: Digital Subscriber Line (DSL)
Connecting through telephone network (DSL modem)
- ADSL same thing except download/upload speed are different
    - Usually upload is 10x slower

Combined with telephone data and send together, split at the server
- Low frequency data (telephone)
- High frequency (internet)

### Access Network: Cable Network
Multiple houses tapped into one cable network that was split and put underground
- At home, you have a receiver that can be tuned to different frequencies to get different channels
    - Frequency Division Multiplexing

### Access Network: Home Network
Cable or DSL modem connects to a router which connects to a wireless access point (usually combined into one)

### Access Network: Enterprise Network (Ethernet)
Routers use dijkstras algorithm, which needs a lot of router (more expensive)
- The use of ethernet switches

### Access Network: Wireless Network
Shared wireless access network connects end system to router via base station (access point)

Wireless LAN:
- Within building e.g. 100 ft
- Uses repeaters for wider coverage
- 450 mbps 
Wide-area wireless access
- Provided by telco (cellular)
- Operate with 10km 
- Slower than wireless LAN (1-10mbps)

### Host: Sends Packets of Data
- Host sending function takes application message
    - Stream of bytes that are broken down into packets (a few kilobytes), of length *L* bits
    - Receiver assembles the packets into full message

- Transmits packet into access network at transmission rate $R$.
    - Link transmission rate, link capacity, link bandwidth

How long to send a packet? 
- Transmission delay (for the packet to leave the device)
$$
\frac{\text{L (bits)}}{\text{R(bits/sec)}}
$$
- Different than propagation delay (affected by medium, distance)

### Physical Media
- Bit: what propagates between transmitter/receiver pairs
    - Information theory (0 or 1), Physical Bit (1)
- Physical link: what lies between transmitter and receiver
- Guided Media: copper, fiber, coax
- Unguided media:
    - Signals propagate freely e.g. radio
- Twisted pair (TP)
    - Two insulated copper wires
    - Instead of having a perfect shielding of every conductor, it twists to shield the data
    - Copper is subject to alpha particle corruption, not fiber

## Network Core
A mesh of interconnected routers