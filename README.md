*This project has been created as part of the 42 curriculum by bpires-r.*

# Description

As explained in the **Project's subject**:

This activity is a general practical exercise designed to introduce the basics of computer networking. We are supposed to learn how to configure IP addresses, connect devices through a router, and understand the role of a gateway within a network.

The project consists of solving a set of 10 levels based on simulated networks and submit them to our git repository.
These exercises will contain a network diagram consisted of hosts, switches and routers with incomplete or incorrect configuration arguments. The task as said is to analyze and fix the configuration so that the communication between all devices is possible

In summary the project emphasizes:
- TCP/IP Addresses, specifically IPv4 Addresses
- Subnet Masking
- Default Gateways
- Router Interfaces

# Instructions

To launch the training interface, the provided project files must be extracted into a local directory. The interface is started by executing the provided script:
```./run.sh```
This script launches a local web server and opens the NetPractice interface in the default web browser.

If you prefer you can use the file explorer and open the index.html file inside extracted local directory. This will launch NetPractice interface.
# Submission

The repository must contain:
 - A README.md file at the root of the repository
 - 10 exported configuration files, one for each completed level also at the root of the repository

# Glossary

**Heterogeneous Devices** - In [computer networking](https://en.wikipedia.org/wiki/Computer_network "Computer network"), a **heterogeneous network** is a network connecting [computers](https://en.wikipedia.org/wiki/Computer "Computer") and other devices where the [operating systems](https://en.wikipedia.org/wiki/Operating_system "Operating system") and [protocols](https://en.wikipedia.org/wiki/Protocol_\(computing\) "Protocol (computing)") have significant differences. For example, [local area networks](https://en.wikipedia.org/wiki/Local_area_network "Local area network") (LANs) that connect [Windows](https://en.wikipedia.org/wiki/Windows "Windows"), [Linux](https://en.wikipedia.org/wiki/Linux "Linux") and [Macintosh](https://en.wikipedia.org/wiki/Macintosh "Macintosh") computers are [heterogeneous](https://en.wikipedia.org/wiki/Heterogeneous "Heterogeneous"). - #Source : [Wikipedia](https://en.wikipedia.org/wiki/Heterogeneous_network)**


# Resources

When working on this project I first started by picking the topics to first search and look deep into and then if preferred on specific topics inside it I would go deeper on other topics as well, this goes for the criteria of each one of us.

Here are the topics I went through some research in the beginning of this project.

- Types of Network Protocols
- OSI Model
- TCP/IP Addresses, specifically IPv4 Addresses
- Private IP Addresses
- Subnet Masking
- Default Gateways
- Router Interfaces

## Types of Network Protocols

A Network protocol is a collection of rules that governs how data is transmitted, received, and interpreted between devices on a network, regardless of their internal structure or design.

- Defines, what, how and when data is communicated.
- Enables communication between heterogeneous devices.
- Ensures reliable and standardized data exchange.
- Prevents data loss, duplication

**Communication process showing how data is encoded, transmitted, and decoded using network protocols:**


### The Working of Network Protocols

Network protocols work by dividing communication tasks into layers, where each layer performs a specific function to ensure successful data transmission

- Communication is based on the **OSI Model** which consists of 7 layers.
- Each OSI layer uses specific protocols to perform their task.
- Data moves layer by layer from sender to reciever.
- Example: Internet Protocol (IP) operates at the network layer and handles routing using source and destination addresses.
- Layered communication improves reliability, scalability, and troubleshooting.
### OSI Model

The OSI Model is a conceptual framework created by the International Organization for Standardization (ISO) to describe how data is transmitted across networks using a structures seven-layer architecture. 
- Divides network communication into seven functional layers.
- Assigns specific responsibilities to each layer.
- Promotes compatibility between different networking systems.
- Simplifies network design, implementation, and troubleshooting.

#### Layer 1: Physical Layer
This is the lowest layer of the OSI reference model and responsible for the actual physical connection between devices.
- [Physical Layer](https://www.geeksforgeeks.org/computer-networks/physical-layer-in-osi-model/) is responsible for transmitting individual bits from one node to the next.
- When receiving data, this layer will get the signal received and convert it into 0s and 1s and send them to the Data Link layer.
- Common physical layer devices are [Hub](https://www.geeksforgeeks.org/computer-networks/what-is-network-hub-and-how-it-works/), [Repeater](https://www.geeksforgeeks.org/computer-networks/repeaters-in-computer-network/), [Modem](https://www.geeksforgeeks.org/computer-networks/difference-between-modem-and-router/), and [Cables](https://www.geeksforgeeks.org/computer-networks/types-of-ethernet-cable/).

#### Layer 2: Data Link Layer (DLL)
The data link layer is responsible fir the node-to-node delivery of the message and make sure data transfer is error-free from one node to another, over the physical layer.
- When a packet arrives in a network, it is the responsibility of the DLL to transmit it to the host using its [MAC address](https://www.geeksforgeeks.org/computer-networks/mac-address-in-computer-network/).
- Packet in the DLL is referred to as Frame and [Switches and Bridges](https://www.geeksforgeeks.org/computer-networks/difference-between-switch-and-bridge/) are common DLL devices.
- The packet received from the Network layer is further divided into frames depending on the frame size of the NIC ([Network Interface Card)](https://www.geeksforgeeks.org/computer-networks/nic-full-form/).
- DLL also encapsulates Sender and Receiver’s MAC address in the header.

#### Layer 3: Network Layer
The Network Layer works for the transmission of data from one host to the other located in different networks and also takes care of packet routing
- The sender and receiver's IP [address](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/) are placed in the header by the network layer.
- Segment in the Network layer are referred to as Packets****.****
- Network layer is implemented by networking devices such as [routers and switches](https://www.geeksforgeeks.org/computer-networks/difference-between-router-and-switch/).

#### Layer 4: Transport Layer
This layer is responsible for end-to-end delivery of the message and Transport layer provides services to the application layer and takes services from the network layer. 
- The data in the transport layer is referred to as Segments and it is responsible for successful data transmission.
- Protocols used in Transport Layer are [TCP](https://www.geeksforgeeks.org/computer-networks/what-is-transmission-control-protocol-tcp/), [UDP](https://www.geeksforgeeks.org/computer-networks/user-datagram-protocol-udp/) [NetBIOS](https://www.geeksforgeeks.org/ethical-hacking/what-is-netbios-enumeration/), [PPTP](https://www.geeksforgeeks.org/computer-networks/pptp-full-form/).
- It adds source and destination [port number](https://www.geeksforgeeks.org/computer-networks/what-is-ports-in-networking/) in its header and forwards the segmented data to the Network Layer.
- ****Example:**** When a web application requests a web server, it typically uses port number 80, because this is the default port assigned to web applications.

#### Layer 5: Session Layer
Session Layer is responsible for the establishment of connections, management of connections, terminations of sessions between two devices and provides authentication and security.

#### Layer 6: Presentation Layer
The Presentation Layer is also called the Translation Layer and data from the application layer is extracted here and manipulated as per the required format to transmit over the network.
- Protocols used in the Presentation Layer are [TLS/SSL](https://www.geeksforgeeks.org/computer-networks/difference-between-secure-socket-layer-ssl-and-transport-layer-security-tls/) (Transport Layer Security / Secure Sockets Layer).
- [JPEG, MPEG, GIF](https://www.geeksforgeeks.org/computer-graphics/difference-between-jpeg-and-mpeg/), are standards or formats used for encoding data, which is part of the presentation layer’s role.

#### Layer 7: Application Layer
At the very top of the OSI Reference Model stack of layers, we find the [Application Layer](https://www.geeksforgeeks.org/computer-networks/application-layer-in-osi-model/) which is implemented by the network applications. These applications produce the data to be transferred over the network.

- This layer also serves as a window for the application services to access the network and for displaying information.
- Protocols used in the Application layer are [SMTP](https://www.geeksforgeeks.org/computer-networks/simple-mail-transfer-protocol-smtp/), [FTP](https://www.geeksforgeeks.org/computer-networks/file-transfer-protocol-ftp-in-application-layer/), [DNS](https://www.geeksforgeeks.org/computer-networks/domain-name-system-dns-in-application-layer/), etc.

### Types of Network Protocol
In most cases, communication across a network like the Internet uses the OSI Model . The OSI model has a total of seven layers. Secured connections, network management, and network communication are the three main tasks that the network protocol performs. The purpose of protocols is to link different devices.

The protocols can be broadly classified into three major categories:

#### 1. Network Communication
Communication protocols are really important for the functioning of a network. They are so crucial that it is not possible to have computer networks without them. These protocols formally set out the rules and formats through which data is transferred. These protocols handle syntax, semantics, error detection, synchronization, and authentication.

Below mentioned are some network communication protocol:
##### Hypertext Transfer Protocol(HTTP) 
Used for transferring hypertext data between systems on the World Wide Web, Hypertext Transfer Protocol ([HTTP](https://www.geeksforgeeks.org/blogs/http-full-form/)) operates at the application layer.
- Works on a [client-server model.](https://www.geeksforgeeks.org/system-design/client-server-model/)
- Used for loading web pages in browsers.
- Stateless protocol (does not store session information).
- Most data exchange on the web uses HTTP.
- Less secure unless used with HTTPS.

```
This will be used for the next Project Webserver.

Some of the extra information here was an advance on the research for these next projects - If you want to only take a look at the Netpractice basic information needed you can jump onto: TCP, IP - these are the ones you need.
```
##### Transmission Control Protocol(TCP)
Provides reliable and ordered data delivery through a [connection-oriented](https://www.geeksforgeeks.org/computer-networks/difference-between-connection-oriented-and-connection-less-services/) approach, a feature of the Transmission Control Protocol ([TCP](https://www.geeksforgeeks.org/computer-networks/what-is-transmission-control-protocol-tcp/)).
- Establishes a connection before data transmission.
- Uses sequenced acknowledgments to ensure reliability.
- Provides error detection and flow control.
- Guarantees data delivery in the correct order.
- Used in email, [FTP,](https://www.geeksforgeeks.org/computer-networks/file-transfer-protocol-ftp-in-application-layer/) web browsing, and streaming services.
##### Internet Protocol(IP)
Handles addressing and routing of data packets across interconnected networks using the Internet Protocol (IP).
- Sends data from source host to destination host.
- Uses IP addresses for device identification.
- Supports packet routing across different networks.
- Connectionless and best-effort delivery protocol.
- Forms the foundation of the Internet.

```
This will be more focused later in this document.
```

There's also a bunch more different types but we won't focus on those right now since it is not needed for netpractice.

# TCP/IP

- TCP (Transmission Control Protocol) is a communication protocol or list of rules to ensure data is sent and received accurately between devices.
- A list of rules/standards that are divided into layers folowing the OSI model.

This model is made of **Layers**
**APPLICATION**
End-user software: #email, #browsers

**TRANSPORT**
end-end communication for example ports: #TCP , #HTTP , #HTTPS

**INTERNET**
IP addressing and routing.

**PHYSICAL**
Link layer that handles the physical transition of data example: #Ethernet_Cables 

## What is a LAN?

A #LAN is a local area network. It has a network of devices communicating with each other within a limited range.
For example our home network has multiple devices connecting to each other and talking to each other.

## IP (_INTERNET PROTOCOL ADDRESS_)


An IP address is a numeric address which it's an identifier for a computer or device on a network.
Every device has to have an IP address for communication purposes.
The IP address consists of 2 parts: A network address and a host address.
There are also 2 types of IP addresses the first one is `IPv4` which is the most common one and the second type is `IPv6`.

1. Network Address (First IP of a network)
	- 192.168.1.0
2. Broadcast Address (last IP of a network)
	- 192.168.1.255
    
**Usable IP range: 1-254**
### IPv4
- IPv4 is the current version (_not for long_) of IP addresses.
- 32-bit numeric address written as four numbers separated by periods. 
```IPv4_Address
			66 . 94 . 234 . 13
```
- Each group of numbers that are separated by periods is called an `octet`.
- The number range in this octet goes from 0-255.
- This address version can produce over 4 billion, most exactly 4, 294,967,296 possible unique addresses.

#### Computers and Networks with IPv4
- Computers and Networks don't read IP addresses in this standard numeric format.
```IPv4_Address
			66 . 94 . 234 . 13
```
- They only understand numbers in binary format.
- Binary numbers only use 1's and 0's.
```IPv4_Address_Binary
			66 . 94 . 234 . 13
												01000010.01011110.00011101.00001101
```
- This binary numbers is what computer and networks actually read.

So how do I get this `binary number` from this `IP address`?

#### IPv4 _BINARY CONVERSION_

8 Bit Octet Chart

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- |

IPv4 is made of 4 sets of 8 binary bits and this sets are called octets. The bits in each octets are represented by a number.

if we need a number like `66` we first need to take a look at our 8 bit Octet Chart and you would put 1's under the numbers that would add up to the number 66. Because each bit can be 1's or 0's. If the bit is a 1 then the number that it represents counts, if it's a 0 then the number that it represents does not count. So by manipulating the ones and the zeros in the octet you can come up with a number from 0-255.


| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 1   | 0   | 0   | 0   | 0   | 1   | 0   |
This number represents the binary bit version of `66`.

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 1   | 0   | 1   | 1   | 1   | 1   | 0   |
This number represents the binary bit version of `94`.

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 0   | 0   | 1   | 1   | 1   | 0   | 1   |
This number represents the binary bit version of `29`.

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 0   | 0   | 0   | 1   | 1   | 0   | 1   |
This number represents the binary bit version of `13`.
So we put this number down here:

66              . 94           . 29           .13

| 01000010 | 01011110 | 00011101 | 00001101 |
| -------- | -------- | -------- | -------- |
### IPv6

IPv6 is the newer version of IP addressing designed to replace IPv4 due to limited number of available addresses.
- Uses 128-bit addresses instead of 32-bit (IPv4)
- Written in hexadecimal format, separated by colons.
`2001:0db8:85a3:0000:0000:8a2e:0370:7334`
- Provides a massive number of unique addresses (almost unlimited)
- Supports better security and efficiency
#### Summary
- IPv6 exists mainly to solve the **IPv4 exhaustion problem**.
- Not required for this project (NetPractice focuses on IPv4).
- Same concept as IPv4, just a **different format and larger space**.

# What is a Subnet
The subnet is basically the network address it tells us the range of usable IP addresses

A subnet is typically represented with a #CIDR notation.
The CIDR notation specifies the subnet mask in a shorter format. Indicating how many bits are used for the network portion.

SUBNET MASK: **/24**

| 11111111. | 11111111. | 11111111. | 00000000 |
| --------- | --------- | --------- | -------- |

| 255. | 255. | 255. | 0   |
| ---- | ---- | ---- | --- |
Network Portion           Host Portion

---
## Summary

- A sub/smaller network of a larger network
- It defines a range of IP addresses of a network
	- Identifies whether a host belongs to a network
- The network address with CIDR notation representing a subnet mask
	- example: 192.163.1.0 / 24
- A subnet mask indicates which part of an IP is fixed (network) and variable (host). Basically how many hosts a network can have.
	- example: /24 or 255.255.255.0 
- For a device to belong to the same network they need to have the same subnet mask

## How to know the range or CIDR notation

1. Convert the subnet mask from decimal to binary
2. Find The CIDR network by counting the bits inside the 32 bits that are being used (1's).

Example:
**Mask**: 255.255.255.128
**Binary**: 1111111.1111111.1111111.10000000
- Count the amount of 1's = **25**
The CIDR is /25.

## What is Subnetting?

Subnetting is the process of dividing a large IP network into smaller logical networks called subnets. Each subnet allows devices to communicate efficiently, improving network performance, security, and manageability.
### How to manipulate the subnet mask?
The only way to get more bits is by hacking/stealing them from the host bits.

192.168.1.0 /24 - subnet
255.255.255.0 -   subnet mask

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   |
11111111 . 11111111 . 11111111 . 00000000

1's = network bits 
0's = host bits

How many bits from the host we need to create 4 networks?
This where the second chart comes in.
If you notice while the 1st chart helps us with the binary conversion. The 2nd chart helps us with this problem.

| 128     | 64      | 32     | 16     | 8      | 4     | 2     | 1     |
| ------- | ------- | ------ | ------ | ------ | ----- | ----- | ----- |
| **256** | **128** | **64** | **32** | **16** | **8** | **4** | **2** |
| 0       | 0       | 0      | 0      | 0      | 0     | 1     | 1     |

We just need to find the number of bits we need in the second chart and fill them with ones. So in this case it took us 2 bits to be able to reach 4 networks.
In a case where we need for example 17, which is not a number in the chart, we would need to get to fill it till next bit.

| 128     | 64      | 32     | 16     | 8      | 4     | 2     | 1     |
| ------- | ------- | ------ | ------ | ------ | ----- | ----- | ----- |
| **256** | **128** | **64** | **32** | **16** | **8** | **4** | **2** |
| 0       | 0       | 0      | 1      | 1      | 1     | 1     | 1     |
So in this case we would need 5 bits.

But let's go back to the 4 networks example:
We will be starting at the beginning of our host bits on the subnet mask and we'll hack to bits.
From this:
11111111 . 11111111 . 11111111 . 00000000
To this:
11111111 . 11111111 . 11111111 . 11000000

So now we will convert our mask back into decimal:
255.255.255.192

Now in CIDR notation, which is just counting the amount of bits in our mask, we would get a /26.

But now we want to know, how many hosts are in this network?
**Finding the increment**:
It is the last network bit we have:
11111111 . 11111111 . 11111111 . 1[1]000000

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | 1   | 0   | 0   | 0   | 0   | 0   | 0   |
64 is out increment.

So we could have a network range for example from 

192.168.1.0 - 192.168.1.63

**63 not 64 because we include the 0!**
it also could be:

192.168.1.64 - 192.168.1.127
192.168.1.128 - 192.168.1.191
102.168.1.192 - 192.168.1.255

Now with all of these we have a total of 4 networks from a subnet mask of 255.255.255.192 or /26.
### Summary Steps
1. Calculate how many bits we need to hack
2. Hack the host bits
3. Find the increment
4. Create your networks
## What is a Gateway

A **Gateway** and a router is often the same device  the only difference is their function.
- **Router**: sends packets between different networks based on IP addresses and determines the best path for data to travel based on IP addresses
- **Gateway**: Acts as a "Gate" between two networks allowing them to communicate. It can connect networks that use different protocols as well.
A Gateway has a **Single IP address** which is of the **router** which serves as the **entry** and **exit** point for a network..

## Default Gateway

A **Default Gateway** is the device that allows a network to communicate with **other networks**. 
- It is usually the **router’s IP address** inside your local network.
- When a device wants to send data **outside its network**, it sends it to the default gateway.
- The gateway then **forwards the packet** to the correct destination.
### Example
- PC IP: `192.168.1.10`
- Subnet: `255.255.255.0`
- Default Gateway: `192.168.1.1`
If the PC wants to reach:
- `192.168.1.20` → Direct (same network)
- `8.8.8.8` → Goes through **default gateway**
### Summary
- Acts as an **exit point** from a local network.
- Required to access the **Internet or other networks**.
- Without it, communication is limited to the **local network only**.

## What is a Switch

A switch is a physical device that sits inside a local area network, LAN, and it connects multiple devices to help them communicate. It also manages when the data is sent and received
For example: 
A laptop sends a request to the switch to print a file. The switch then identifies that the request need to go to the printer's IP address and so it's sent it to the printer .

Switches use MAC addresses to handle the communication between devices.

A switch can also be connected to a #router

## What is a Router

A #router is a physical networking device that sits between the local area network and the external network, for example the internet. 
	Routers operate at the internet layer of the transmission control protocol  . If you're referring to the OSI model that would be the network layer. 
Routers connect us to the internet and other networks. This is called the wider area network.
They can also have multiple IP's for different networks and it uses routing tables to determine the best path for data travel and forward packets between the multiple networks.

### How Does a Router Work

Routers determine the path for a packet by examining its destination IP address and consulting the ***routing table***, which contains information on network paths. They use a set of rules to identify the most efficient route for each packet.

- ****Static routing:**** Configured manually, suitable for small or stable networks.
- ****Dynamic routing:**** Automatically updated based on network activity, ideal for large or changing networks.

## NETPRACTICE Tips

1. Take out all the noise and start clean
2. Solve one goal at a time
3. Refer to a subnet chart

## Direct Links

- [Types of Networks](https://www.geeksforgeeks.org/computer-networks/types-of-network-protocols-and-their-uses/)
- [Layers of OSI Model](https://www.geeksforgeeks.org/computer-networks/open-systems-interconnection-model-osi/)
- [Subnetting](https://www.youtube.com/watch?v=mJ_5qeqGOaI&list=PLIhvC56v63IKrRHh3gvZZBAGvsvOhwrRF&index=6)
- [More Subnetting](https://www.geeksforgeeks.org/computer-networks/introduction-to-subnetting/)
- [Switches](https://www.geeksforgeeks.org/computer-networks/what-is-a-network-switch-and-how-does-it-work/)
- [Router](https://www.geeksforgeeks.org/computer-networks/introduction-of-a-router/)
- [Routing Table](https://www.geeksforgeeks.org/computer-networks/routing-tables-in-computer-network/)

