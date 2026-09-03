# Network Essentials Module 1-7 — Summary & Key Learnings
## Date Completed: 31 August 2026
#Network Essentials Module 8-11 - Summary & Key Learnings
## Date Completed:03 September 2026

-

## 🔗 Navigation
- [ Home](../index.md)
- [ Introduction to Cybersecurity](introduction-to-cybersecurity.md)
- [ Network Essentials](network-essentials.md)

---

## What I Learned
- Network communication protocols and how devices communicate  
- The purpose of network communication standards  
- How to compare the OSI model with the TCP/IP model  
- That protocols connect devices to the network  
- DHCP/ICMPv6 provide IP addresses and default gateway information  
- IP delivers packets from the source to the destination  
- TCP guarantees reliability by ensuring all information sent is received  
- Ethernet handles communication within the same local network  
- IP works closely with the internet to deliver messages across networks  
- TCP acts like a “postman protocol,” ensuring reliable transport  
- HTTP governs the exchange and transfer of information at the application layer  
- Successful communication requires multiple protocols working together  
- The difference between protocol models and reference models  
- TCP/IP describes the functions of each protocol in the suite  
- OSI describes the functions required at each layer without specifying how they are implemented  

---

## OSI vs TCP/IP Diagram




+---------------------------+        +---------------------------+
|        OSI Model          |        |       TCP/IP Model        |
+---------------------------+        +---------------------------+
| 7. Application            |        | 4. Application            |
| 6. Presentation           |        |                           |
| 5. Session                |        |                           |
+---------------------------+        +---------------------------+
| 4. Transport              |        | 3. Transport              |
+---------------------------+        +---------------------------+
| 3. Network                |        | 2. Internet               |
+---------------------------+        +---------------------------+
| 2. Data Link              |        | 1. Network Access         |
| 1. Physical               |        |                           |
+---------------------------+

Key Notes:
- OSI = 7 layers (conceptual model)
- TCP/IP = 4 layers (practical model)
- OSI explains *what* happens; TCP/IP explains *how* protocols work

---

## My Reflections
This module helped me understand how devices communicate across networks and how different protocols work together to deliver information reliably. I now see how essential protocols like IP, TCP, DHCP, and HTTP are in real‑world communication. Learning the OSI and TCP/IP models also gave me a clearer understanding of how network processes are structured.

---

## Skills Gained
- Understanding of core network communication protocols  
- Ability to explain how TCP/IP and OSI models compare  
- Awareness of how protocols interact within a protocol stack  
- Clear understanding of IP addressing and reliable transport  
- Ability to describe how messages move from source to destination  

---

## Next Steps
Module 8 — IPv4 Issues & IPv6 Introduction
### IPv4 Issues
IPv4 uses 32-bit addresses, giving about 4.3 billion possible addresses. As the internet grew, this space became too small.

IPv4 Exhaustion Timeline
+----------------------+----------------------+
| Regional Registry    | Exhaustion Date      |
+----------------------+----------------------+
| LACNIC (Latin Am.)   | 2011                 |
| RIPE NCC (Europe)    | 2012                 |
| APNIC (Asia Pacific) | 2014                 |
| ARIN (North America) | 2015                 |
| AfriNIC (Africa)     | 2020                 |
+----------------------+----------------------+
### IPv6 Addressing
IPv6 addresses are:

128 bits

Written in hexadecimal

Contain 8 hextets

Not case-sensitive
Example
fe80:0000:0000:0000:0000:0123:4567:89ab
### IPv6 Shortening Rules
Rule 1 — Omit Leading Zeros 
01ab → 1ab
09f0 → 9f0
0a00 → a00
00ab → ab
Rule 2 — Double Colon (::)
                 +---------------------------+
                 |     Dual Stack Router     |
                 |   IPv4 + IPv6 Enabled     |
                 +--------------+------------+
                                |
        -------------------------------------------------
        |                       |                       |
+---------------+     +---------------+       +---------------+
| PC1           |     | PC2           |       | PC3           |
| Dual Stack    |     | Dual Stack    |       | Dual Stack    |
| IPv4 & IPv6   |     | IPv4 & IPv6   |       | IPv4 & IPv6   |
+---------------+     +---------------+       +---------------+

All devices can communicate using either IPv4 or IPv6.



Module 9 — Transmission Types
### Unicast
One sender → one receiver.

### Broadcast
Source: 172.16.4.1/24
Destination: 255.255.255.255
Broadcasts do not cross routers.

### Multicast
Multicast Transmission Diagram
Source: 172.16.4.1/24  
Destination Group: 224.10.10.5
                 +------------------+
                 |      Router      |
                 +--------+---------+
                          |
                          |
                 +--------+---------+
                 |      Switch      |
                 +--------+---------+
                          |
        -----------------------------------------
        |           |            |            |
        |           |            |            |
+---------------+ +---------------+ +---------------+ +---------------+ +---------------+
| PC1           | | PC2           | | PC3           | | Laptop        | | Printer       |
| 172.16.4.1/24 | | 172.16.4.2/24 | | 172.16.4.3/24 | | 172.16.4.4/24 | | 172.16.4.253/24|
|               | |               | | +------------+ | | +------------+ |               |
|               | |               | | |224.10.10.5| | | |224.10.10.5| |               |
+---------------+ +---------------+ +---------------+ +---------------+ +---------------+

Only PC3 and Laptop receive the multicast traffic because they joined group 224.10.10.5.



Module 10 — IPv4 Addressing & Subnetting
### Types of IPv4 Addresses
Public

Private

Network

Broadcast

Multicast

Special-use

### Network Number vs Host Number Diagram
Left Network: 192.168.18.0/24
Router: 192.168.18.99

+---------------------------+
|   Network 192.168.18.0    |
+-------------+-------------+
              |
      +-------+-------+
      |   Router      |
      |192.168.18.99  |
      +-------+-------+
              |
   ---------------------------
   |           |            |
+--------+ +--------+ +--------+
| PC1    | | PC2    | | PC3    |
|18.11   | |18.22   | |18.33   |
+--------+ +--------+ +--------+

Right Network: 192.168.5.0/24
Router: 192.168.5.99

+---------------------------+
|    Network 192.168.5.0    |
+-------------+-------------+
              |
      +-------+-------+
      |   Router      |
      |192.168.5.99   |
      +-------+-------+
              |
   ---------------------------
   |           |            |
+--------+ +--------+ +--------+
| PC1    | | PC2    | | PC3    |
|5.11    | |5.22    | |5.33    |
+--------+ +--------+ +--------+

Routers connect the two networks.
Network number identifies the network; host number identifies the device.### Why Subnetting Is Needed
Reduces broadcast domains

Improves performance

Enhances security

Conserves IPv4 addresses

### Internet of Things (IoT)
IoT relies heavily on IPv6, DHCP, and multicast.



 Module 11 — DHCP, Static & Dynamic Addressing
### Static IPv4 Addressing
Manually configured.
Used for servers, routers, printers.

### Dynamic IPv4 Addressing (DHCP)
DHCP Flow
Discover → Offer → Request → Acknowledge
Home routers act as both DHCP clients and servers.



Module 8-11 What I Learned

### What I Learned

I learned that DHCP and ICMPv6 help provide IP addresses and default gateway information to devices automatically.

I understood that the IP protocol delivers packets from the source to the destination, even across multiple networks.

I learned that TCP guarantees reliability by ensuring all information sent is received correctly — acting like a “postman protocol.”

I learned that Ethernet handles communication within the same local network (LAN).

I discovered how IP works closely with the internet to deliver messages across networks, regardless of distance.

I learned that TCP ensures reliable transport, checking for errors and resending lost data.

I understood that HTTP governs the exchange and transfer of information at the application layer.
I learned that successful communication requires multiple protocols working together in a protocol stack.

I understood the difference between protocol models and reference models.

I learned that TCP/IP describes the functions of each protocol in the suite.

I learned that the OSI model explains the functions required at each layer without specifying how they are implemented.




