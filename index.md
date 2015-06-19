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

### Link Layer

Link Layer

The link layer is used to move packets between the Internet layer
interfaces of two different hosts on the same link.  This layer may be
implemented on top of virtually any hardware networking technology.

https://en.wikipedia.org/wiki/Internet_protocol_suite#Link_layer

--

### Link Layer: Diagram

![Link Layer](LinkLayer.png)

--

### Link Layer: Examples

Physical media: Ethernet, WiFi, 4G, Phone Line

Link: Network Interface Controller (NIC), Modem, Phone/Cell Antenna?

Media Access Control (MAC) Address (e.g., `80:e6:50:25:0d:74`)

--

### Link Layer: Exercise

In this exercise, you will locate the MAC addresses for the WiFi NIC on your computer.

1. Open a Terminal
2. Type `ifconfig en0` at the prompt and press [Return]

--

### Internet Layer: Diagram


![Internet Layer](InternetLayer.png)

--

### Internet Layer

The internet layer has the responsibility of sending packets across potentially multiple networks. Internetworking requires sending data from the source network to the destination network. This process is called routing.

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
* Domain Name System (DNS)

--

### Internet Layer: Exercise

--

### Transport Layer: Diagram

![Transport Layer](TransportLayer.png)

--

### Transport Layer

The transport layer establishes a basic data channel that an application uses in its task-specific data exchange. The layer establishes process-to-process connectivity, meaning it provides end-to-end services that are independent of the structure of user data and the logistics of exchanging information for any particular specific purpose. Its responsibility includes end-to-end message transfer independent of the underlying network, along with error control, segmentation, flow control, congestion control, and application addressing (port numbers). End-to-end message transmission or connecting applications at the transport layer can be categorized as either connection-oriented, implemented in TCP, or connectionless, implemented in UDP.

https://en.wikipedia.org/wiki/Internet_protocol_suite#Transport_layer

--

### Transport Layer: Examples

* Transmission Control Protocol (TCP)
* User Datagram Protocol (UDP)

--

### Transport Layer: Exercise

--

### Application Layer: Diagram

![Application Layer](ApplicationLayer.png)

--

### Application Layer

The application layer includes the protocols used by most applications for providing user services or exchanging application data over the network connections established by the lower level protocols, but this may include some basic network support services, such as many routing protocols, and host configuration protocols. Examples of application layer protocols include the Hypertext Transfer Protocol (HTTP), the File Transfer Protocol (FTP), the Simple Mail Transfer Protocol (SMTP), and the Dynamic Host Configuration Protocol (DHCP). Data coded according to application layer protocols are encapsulated into transport layer protocol units (such as TCP or UDP messages), which in turn use lower layer protocols to effect actual data transfer.

https://en.wikipedia.org/wiki/Internet_protocol_suite#Application_layer

--

### Application Layer: Examples

* File Transmission Protocol (FTP)
* Hypertext Transfer Protocol (HTTP)
* HTTP Secure (HTTPS)
* Transport Layer Security (TLS)
* Secure Shell (SSH) protocol

--

### Application Layer : Exercise

--








