title: ETDG, Introduction to Networking
date: 2015-06-23
author:
    name: Ben Wallberg, Peter Eichman
    email: wallberg@umd.edu, peichman@umd.edu
output: index.html

--

### Introduction to Networking

UMD Libraries, Emerging Technologies Discussion Group

June 23, 2015

--

### Internet protocol suite

Many network models exist.  Today we will discuss the network
model used for The Internet, known as the Internet protocol suite.

https://en.wikipedia.org/wiki/Internet_protocol_suite

--

### Layer Model

A common way to build and understand complex computer systems is to create layers,
with each layer only needing to know its own implementation and how to
interact with an adjacent layer.

--

### Layer Model: Diagram

<table>
  <tr>
    <td>![Layer Model](450px-IP_stack_connections.png)</td>
    <td>
      [IP stack connections](http://commons.wikimedia.org/wiki/File:IP_stack_connections.svg)
      <br/>
      [CC BY-SA 3.0](http://creativecommons.org/licenses/by-sa/3.0/)
    </td>
  </tr>
</table>

--

### Layer Model: Levels

- Application layer
- Transport layer
- Internet layer
- Link layer

In the Internet model each layer only needs to understand itself and how to
interface with the next lower layer.

--

### Link Layer: Diagram

![Link Layer](LinkLayer.png)

--

### Link Layer: Definition

The **link layer** is used to move packets between the Internet layer
interfaces of two different hosts on the same link.  This layer may be
implemented on top of virtually any hardware networking technology.

https://en.wikipedia.org/wiki/Internet_protocol_suite#Link_layer


--

### Link Layer: Examples

Physical media: Ethernet, WiFi, 4G, Phone Line

Link: Network Interface Controller (NIC), Modem, Phone/Cell Antenna?

Media Access Control (MAC) Address (e.g., `80:e6:50:25:0d:74`)

--

### Link Layer: Ethernet Packet

aka Ethernet Frame

![](800px-Ethernet_Type_II_Frame_format.svg.png)

[Ethernet Type II Frame format](https://commons.wikimedia.org/wiki/File:Ethernet_Type_II_Frame_format.svg)
<br/>
[Public Domain](https://en.wikipedia.org/wiki/en:public_domain)

--

### Link Layer: Exercise

In this exercise, you will locate the MAC addresses for the WiFi NIC on your computer.

1. Open a Terminal
2. Type `ifconfig en0` at the prompt and press [Return]

--

### Internet Layer: Diagram


![Internet Layer](InternetLayer.png)

--

### Internet Layer: Definition

The **internet layer** is responsibile for sending packets across potentially
multiple networks. Internetworking requires sending data from the source network
to the destination network. This process is called routing.

https://en.wikipedia.org/wiki/Internet_protocol_suite#Internet_layer

--

### Internet Layer: Routing

Routers:

* Connect networks
* Packet for a computer on the local area network (LAN)? Deliver directly
* Packet for a remote computer? Send it to another router

--

### Internet Layer: Examples

* Classless Inter-Domain Routing (CIDR)
* Routing
* Internet Protocol (IP)
* Network Address Translation (NAT)
* Local Area Network (LAN)
* Wide Area Network (WAN)

--

### Internet Layer: Exercise

possible tools: tracert

--

### Transport Layer: Diagram

![Transport Layer](TransportLayer.png)

--

### Transport Layer: Definition

The **transport layer** establishes a basic data channel between hosts. It
provides end-to-end services that are independent of the underlying network
(link and internet layers).  These services are also independent of the
structure of user data and the logistics of exchanging information for any
particular specific purpose (application layer).

https://en.wikipedia.org/wiki/Internet_protocol_suite#Transport_layer

--

### Transport Layer: Examples

* User Datagram Protocol (UDP)
* Transmission Control Protocol (TCP)

Both operate on top of the IP protocol.  Due to the prevalence of TCP traffic the Internet protocol suite is also known as TCP/IP.

--

### Transport Layer: Examples

TCP and UDP both introduce the concept of port numbers (0-65535) to identify sending and receiving application end-points on a host.

Many applications have well known ports on the receiving end, eg. port 80 for web servers (HTTP). 

--

### Transport Layer: Examples

User Datagram Protocol (UDP) - used for simple, connectionless messaging transmissions

* Unreliable
* Unordered
* Lightweight, low latency
* Datagram (single packets)

https://en.wikipedia.org/wiki/User_Datagram_Protocol

--

### Transport Layer: Exercise

Observe UDP communications, using special interface Loopback (lo0) with IP address 127.0.0.1

1. Open Wireshark, capture packets on lo0, filter `udp.port == 64000`
2. `netcat --udp --listen --local-port=64000` to listen for UDP datagrams on port 64000
4. `echo 'Hello, World' | netcat --udp 127.0.0.1 64000` to send "Hello, World" datagram


--

### Transport Layer: Examples

Transmission Control Protocol (TCP) - connection oriented, bi-directional messaging

* Reliable
* Ordered
* Heavyweight

https://en.wikipedia.org/wiki/Transmission_Control_Protocol

--

### Transport Layer: Exercise

Observe TCP communications, using Loopback interface

1. Open Wireshark, capture packets on lo0, filter `tcp.port == 64000`
2. `netcat --tcp --listen --local-port=64000` to listen for TCP connections on port 64000
4. `echo 'Hello, World' | netcat --tcp --close 127.0.0.1 64000` to send "Hello, World" message

--

### Application Layer: Diagram

![Application Layer](ApplicationLayer.png)

--

### Application Layer: Definition

The **application layer** includes the protocols for providing user services or
exchanging data over the network connections established by the lower level
protocols. Data coded according to application layer protocols is encapsulated
into transport layer protocol units (such as TCP or UDP messages), which in turn
use lower layer protocols to effect actual data transfer.

https://en.wikipedia.org/wiki/Internet_protocol_suite#Application_layer

--

### Application Layer: Examples

Domain Name System (DNS)

The Domain Name System is an essential component of the functionality of most Internet services because it is the Internet's primary directory service, translating domain names, which can be easily memorized by humans, to IP addresses.

https://en.wikipedia.org/wiki/Domain_Name_System

--

### Application Layer: Examples

![DNS Configuration](DNS_Configuration.png)

--

### Application Layer: Exercise

Observe DNS communications.

1. Open Wireshark, capture packets on en0, filter `dns`
2. `nslookup lib.umd.edu`
3. `nslookup www.lib.umd.edu`
4. `nslookup oer.umd.edu`
5. `nslookup google.com`

--

### Application Layer: Examples

* File Transmission Protocol (FTP)
* Hypertext Transfer Protocol (HTTP)
* HTTP Secure (HTTPS)
* Transport Layer Security (TLS)
* Secure Shell (SSH) protocol
* Simple Mail Transfer Protocol (SMTP)

--

### Application Layer: Exercise
