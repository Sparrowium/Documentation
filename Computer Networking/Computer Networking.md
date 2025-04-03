
<h2 style="color:#6290C3"><center> Getting Started with Networking </center></h2>

## How Networks Work

- A network is a conduit that connects two or more computers or other devices.
	
- There are two basic kinds of networks:
	
	- [Local Area Network (LAN)]: Any group of computers on a single, geographically limited network. LANs allow user to exchange documents and share resources such as printers or file servers. A LAN can be wired or wireless, and both.
		
	- [Wide Area Network (WAN)]: A network that connects LANs over large geographic distances.
	
- [Open Systems Interconnection (OSI) Reference Model]: Often referred as network stack. This models identifies the steps and functions that must be completed at each layer when computers communicate over a network. It provides guidelines on how computers communicate over a network. It does not define a specific procedures or protocols.
	![[Pasted image 20250312212113.png]]
- [Network Protocols]:
	
	- [Protocol]: A formal set of rules or procedures computers must understand, accept, and use to be able to communicate over a network. Examples of protocols includes: TCP, UDP, SNMP, SMTP, IMAP, HTTP, and FTP. Different protocol are used at different layer.
		
	- Network protocols operate in the same manner like human conversation, ask and answer in turns, defining rules such as when computers are able to transmit data, which computer is destined for, and what to do if the data is not received.
		
	- The OSI Reference Model describe such behavior. On the sender, data flows down the model or stack. At each layer in the stack, protocols add headers and trailers or footers which contain information. When a lower layer receives information from upper layer, it consider the entire package as data and add its own header, and if needed, footer or trailer to the data. The process of adding headers and footers to data layer is called **encapsulation**. On the receiver, data flows up the stack. At each layer, the addressing or protocol information is examined and removed layer by layer until the computer gets to the actual data. The process of removing headers at each layers of the stack is called **de-encapsulation**.
	
- [TCP/IP Reference Model]: A simple, four layer model. Defines specific protocols at each layer. **TCP/IP** stands for Transmission Control Protocol/Internet Protocol. 
	![[Pasted image 20250312212127.png]]
	- In addition, the Application, Presentation, Session of the OSI Reference Model is fold into Application Layer on the TCP/IP Model. Then the Transport and Network map directly between the two models. Lastly, the Data Link and Physical is folded into Network Access Layer on the TCP/IP Model.
	
- [Five Layer Model]: A derive of the TCP/IP Model, often called Hybrid Networking Model, where the Data Link and Physical is mapped directly rather than folded into Network Access Layer. Layer 1-4 is the Lower Layer while Application Layer often called Layer 7.
	![[Pasted image 20250312212052.png]]
- [Traversing the Network Model]: 
	![[Pasted image 20250312215042.png]]
	- [Application Layer]: Data is first processed according to one of the many Application Layer Protocols, such as SMTP. Application Layer protocols specify details such as how data should be encoded, compressed, or encrypted, and how sessions should be managed. Some Application Layer Protocol:
		![[Pasted image 20250312212039.png]]
		- [HTTP]: Hypertext Transfer Protocol, a communication for the transfer of information on the Internet and the World Wide Web.
			
		- [FTP]: File Transfer Protocol, a network protocol used to transfer data from one computer to another through a network, such as over the internet.
			
		- [DNS]: Domain Name System associates various information with domains names, mos importantly, it serves as the phone book for the Internet by translating human-readable computer hostnames, such as `www.example.com`, into IP address, such as 208.77.188.166. Networking equipment needs to know these IP addresses to deliver information.
			
		- [SMTP]: Simple Mail Transfer Protocol, the most popular protocol for sending electronic mail on the Internet.
		
	- [Transport Layer]: Specifies which Application Layer protocol should be used to process data on the receiving computer. Each Application Layer protocol is assigned a unique numerical identifier, called a port, which is used to identify the protocol. Example:
		`HTTP: Port 80`
		`DNS: Port 53`
		`SMTP: Port 25`
		![[Pasted image 20250312212007.png]]
		- The Transport Layer also includes the destination port number in the header it adds to the data. When the data arrives at the destination computer, the Transport Layer there examines the Application Layer protocol the data should be sent to. It also includes a source port number in the header, typically a random number, uniquely identifies he connection on the sending side. This port allows the receiving computer to carry on multiple sessions with the sending computer without intermixing the data.
			
		- Two Transport Layer protocols for reliability:
			
			- [UDP]: User Datagram Protocol. Commonly used for short messages and time-sensitive data. Ex: DNS, Gaming, Voice over IP, Streaming Video.
				
			- [TCP]: Transmission Control Protocol, a robust protocol providing delivery notification, error checking, and recovery procedures. The receiving computers tells the sending computer when the data was received. Ex: HTTP, SMTP, FTP. TCP accepts data from the Application Layer protocol and cuts the data into smaller pieces called segments to ensure a steady flow of data between two computers regardless of the differences in connection bandwidth. Segmentation allows the receiver to send back information in an order, and allows the receiver to pack information in an order. The receiving side uses the sequence number to tell the sending side when segments have been received, if the sending does not receive it, a resend will be performed.
		
	- [Network Layer]: Receives data segments from the Transport Layer and adds a header to create a packet. Layer 3 header contains a destination and source IP Address.
		![[Pasted image 20250312212759.png]]
		- The Network Layer identifies the upper layer Transport Layer protocol that is being used. Each Transport Layer protocol is assigned a unique identifier or IP protocol number. Later on when the computer is unwrapping the data layer by layer, it identifies the IP specified in the header and determine which upper layer protocol should process the data next. Ex:
			`UDP: IP protocol number 17`
			`TCP: IP protocol number 6`
			
		- [IP]: Internet Protocol, used to send data from one computer to another on the Internet. Each computer or host has at least one IP address that uniquely identifies it from all other computers on the internet.
		
	- [Data Link Layer]: Receives packets and adds its own header to each packet to create a frame. The header usually includes other address, referred to as a Layer 2 address, or a MAC (Media Access Control) address.
		![[Pasted image 20250312213102.png]]
		- The Layer 2 header typically also includes an indication as to which Layer 3 protocol is in the data portion of the frame. In addition, it also performs a data integrity check using checksum at the sending and receiving of data, so that the data is discarded as soon as data frame isn't correct. Finally, Layer 2 converts the data into ones and zeros of digital communications.
			
		- [Ethernet]: A LAN network technology, its set of standards define rules about frame format, as well as how computers communicate with each other over a single wire shared by all devices on the network.
		
	- [Physical Layer]: Converts these bits into electrical signals and sends them across the physical medium. Physical Layer specification define characteristic such as cabling specifications, voltages levels, physical data rates, maximum transmission distances, and physical connectors.
		![[Pasted image 20250312214749.png]]
	![[Pasted image 20250312215012.png]]![[Pasted image 20250312215118.png]]
- [Seven Layer OSI Reference Model]: A layered, abstract description for communications and computer network protocol design.
	![[Pasted image 20250312215841.png]]
	- [Application Layer]: Specifies network related functions for a user application or program. Not a GUI.
		
	- [Presentation Layer]: Accepts data from the Application layer and converts or encodes it into a standard format that the Application Layer or other computer ca understand. It also involve standard data compression or data encryption schemes, ensuring that the receiving computer can properly uncompress or decipher the data.
		
	- [Session Layer]: Establishes, manages, and ends the connections for sessions between the applications on the communicating computers. The server runs one conference application, but tracks each sessions individually.
		
	- [Transport Layer]: Take data from the upper layer, converts it to a format that can be transmitted over the network, and manages the flow of data between the two hosts that are communicating.
		
		- [Connectionless Transport Service]: Provides no delivery notification system, error checking, or recovery procedures. 
			
		- [Connection Oriented Service]: Responsible for making sure that the data is delivered error-free and in proper sequence. Flow control may also occur in this type of service. It can dynamically adjust the flow of data from one computer to another so that the transmitting computer does not send more data than the receiving computer can handle. especially when there might be a difference in connection speeds.
		
	- [Network Layer]: Take the segment from Layer 4 and adds a header to it to create a "packet". It is responsible for delivering the packet to the destination computer. If there are more than one route to the destination computer, the Network Layer chooses the best path for the packet to take. It treat each packet independently, so it is possible that two packets from the same transmission might take different path to arrive at the destination computer.
		
	- [Data Link Layer]: Takes packet from the Network Layer and adds another header to from a "frame". It can also add a trailer to the frame, such as a Cyclic Redundancy Check (CRC). CRC is a simple mathematical calculation performed on each frame to ensure it hasn't been corrupted in transit. Finally, it translates the frame into binary digits, or bits, for the Physical Layer.
		
	- [Physical Layer]: Where binary digits move across a physical medium. It defines the electrical or optical signal that equals a one, and the signal that equals a zero. Physical Layer standards includes cabling specifications, electrical or optical signaling, and lower-level framing of ones and zeros.
	
- [Networking Addressing]: 
	![[Pasted image 20250312221836.png]]

## Building Ethernet LANs

- [PC's]: Are also known as end user's devices, hosts.
	
- Ethernet is a set of standards that define rules for things such as Frame Format, Communication.
	
- [Collision Domain]: A group of devices compete for access.
	
- [Ethernet Component]: 
	
	- [Network Segments]: A group of network devices that compete with each other for access to the wire. Including the Physical Layer Characteristic, Access to Network, Frame Format.
		
	- [Ethernet Shared Bus]: Multiple computers connected to the same physical wire or cable.
		
	- [Physical Cable Segment]: The cable or wire used to connect network devices.
		
	- To connect end user's devices a Network Interface Controller (NIC) and Ethernet Cabling-or a wireless NIC.
		
	- [Network Interface Controller (NIC)]: A computer hardware component installed in a computer or printer so that it can be connected to a network. The terms NIC, Network Adapter, Network Card and LAN are used interchangeably.
		
	- Access to the physical wire or segment is controlled by a Media Access Control (MAC) protocol. Ethernet uses Carrier Sense Multiple Access with Collisions Detection as it MAC Protocol.
		
	- [CSMA/CD]: Carrier Sense Multiple Access with Collisions Detection.
		
	- In Ethernet LANs, the CSMA/CD protocol regulates the "conversation".
		
	- [Half-Duplex Communication]: The CSMA/CD protocol allows a network device to either transmit data or receive data, but not both simultaneously.
		
	- [Half-Duplex]: Half Duplex Data transmission provides for communication in both directions, but only one direction at a time.
		
	- [Full-Duplex]: Full Duplex Communication sends and receives data at the same time. 
		
	- When one device on a network segment is transmitting data, other devices cannot transmit data.
		
	- Data is encapsulated by the NIC into an Ethernet Frame. Additionally, the Term 802.3 is also Ethernet Frame II but includes a Logical Link Control Portion which allows Layer 3 protocols other than IP access to the wire.
		![[Pasted image 20250318152722.png]]
	- The Ethernet Frame contains the Destination of the Device receiving the data as well as the source of the Layer 2 Address of the device sending the data. Each NIC has a unique Layer 2 address that is assigned by its manufacturer. The manufacturer burns this address into a PROM chip on the NIC, then the NIC uses this address as the source address in a frame. For the destination address, it uses the address that is burned into the NIC on the receiving device. 
		Ex: Hardware Address, Physical Address, MAC Address.
		
		- [Destination Layer 2 Address]: The MAC address of the receiving device.
			
		- [Source Layer 2 Address]: The MAC address of the sending device.
			
		- [Type]: Identify which Layer 3 protocol is being transported in the Ethernet frame. In an 802.3 frame, it indicates the length of the frame.
			
		- [Checksum]: Includes a CRC which is a method of checking errors in data that has been transmitted on a communication link.
		
	- [MAC]: A 48-bit (6 byte) address that uniquely identifies a device's NIC. Ex: 00:90:69:9f:ea:46. Bytes in MAC address can be displayed via `:`, `-`, and `.` . The first 3 byte identifies the manufacturer Organizational Unique Identifier (OUI), the 00:90:69 is Juniper Network OUI. The last 3 byte identifies the Unique NIC.
		
		- When a device is sends data to one other device it uses an individual or unicast address.
			
		- [Broadcast Destination MAC Address]: An address that allows a device to send the same data to every device on the network.
			
		- [Group Address / Multicast MAC Address]: An address that allows a device to send data to a group of devices on the same network. It always has the first bit of the first byte set to 1.
		
	- When the NIC is ready it adds the destination and source MAC address and send it into the segment. Every devices on the segments receive the frame and processes it. If it doesn't match the address, the frame is be discarded by the device NIC. The device that match, the NIC will run the CRC to check the data then examines the type frame to determine the upper Layer protocol. Then it strips off the Ethernet frame and forward the data to the appropriate upper layer protocol.
	
- [Repeater]: A physical layer device that connects 2 or more separate physical cable segments together. It is a simple hardware that regenerates electrical signals, sending all frames from one physical cable segment to another.
	Maximum Cable Length for Ethernet Media: ![[Pasted image 20250318155533.png]]
- [The 5-4-3 Rule]: Means that there can only be a total of 5 cable segments connected through 4 repeaters and only 3 of the 5 segments can contain end-user devices. The other 2 segments or link segments are used to connect the repeaters.
	![[Pasted image 20250318170550.png]]![[Pasted image 20250318170559.png]]![[Pasted image 20250318170612.png]]![[Pasted image 20250318170622.png]]![[Pasted image 20250318170630.png]]![[Pasted image 20250318170638.png]]
- [Cabling]: Coaxial Cabling, Twisted Pair Cabling based on 10BASE-T standard.
	10BASE-T: 10 mbps transmission speed, Basedband (only Ethernet signaling is carried on the wires), Twisted Pair of unshielded, but insulated.
	
- [Hub]: Shared Bus with Repeater to Star Configuration with Hub to prevent daisy chain cable segment failures. A hub takes a signal from a device and repeats it to all other device. It is simply a junction that join all the different devices together. Operates at Level 1.
	
- [Bridge]: Connects two or more physical cable segments to create one larger network, each side of the bridge becomes a separate collision domain or network segment. A bridge can be used to break up network into separate domain collision, this is called network segmentation.
	![[Pasted image 20250318201532.png]]
	- A Bridge operates at Level 2, Data Link Layer. Ethernet bridges have three basic functions: Forwarding Lanes, Learning MAC Addresses, Controlling Traffic. A bridge uses a MAC Address Table, like a database, to limit and control traffic on a network
		
	- When a bridge receives a frame with a destination MAC Address in its MAC address table, it can foward or drop it selectively, reducing overall network traffic.
		
	- Bridges never change the destination or sort MAC address. They just simply look at the destination MAC address to make their decisions.
		
	- Network Loop can form if Destination MAC Address is unknown. Same case applied for broadcast address and multicast address, the bridge must foward it to every port and might result in a broadcast storm which might block all other traffic and put the network into a hold/stand-still. To prevent this a Spanning Tree Protocol (STP) is used.
	
- [Network Speed]: The data transfer rate or bit rate. The amount of data that can be transferred from one point to another in a given time period, usually one second. It is expressed in bits of data per second, which is abbreviated bps or bits/s (not Bps). It is also the maximum capacity of a network connection.
	![[Pasted image 20250318195627.png]]![[Pasted image 20250318195940.png]]
- [Network Throughput]: The actual amount of data that can be sent over a network in a given period of time. This is due to network congestion.
	
- [Twisted Pair Cable]: Consist of Voice, Ethernet Receive, Auxiliary, Ethernet Transmit, which are connected to the pin of an RJ-45M (Male).
	![[Pasted image 20250318200526.png]]
- [Straight-through Ethernet Cable]: Connects an end-user device to a network device. When the end-user device sends data on its transmit pair of wires, the network device receives the data on its receive pins.
	![[Pasted image 20250318200818.png]]
- [Crossover Ethernet Cable]: Connects two end-user device. The crosses wires within the cable allow the transmit wires on the sending computer to connect to the receive circuitry on the receiving computer.
	![[Pasted image 20250318200826.png]]
- [Switches]: Layer 2 device that help manage and control traffic, each port creates a separate collision domain, forward traffic and builds a MAC address table, can have few or hundreds of ports. Each of the port are dedicated to a single end-user device.
	![[Pasted image 20250318201600.png]]
	- Each collision domain has only two devices: the switch and the end-user device. This means that the end-user are no longer competing for network access. Since both sides of the connection will receive data form only a network device, packets will not get corrupted by multiple stations transmitting simultaneously.
		
	- Full-duplex transmission, Bandwidth is not shared, Virtual LANs are possible.
		
	- [VLANs]: Are a way to subdivide a LAN. A VLAN is a group of PCs, servers, and other network devices that may be connected to the same switch as other devices but behave as if they are connected to the same, smaller LAN or a completely separate switch. Devices that are in one VLAN do not receive broadcasts from devices in another VLAN.
		![[Pasted image 20250318201814.png]]
	- Limitations: Susceptible to network loops, might not improve performance with multicast and broadcast traffic, might not be able to interconnect geographically dispersed networks.
	
- [Wireless LAN Architectures]: A device with built-in radio that usually comes with 3 architecture: Autonomus, Centralized, Distributed.
	
	- [Autonomus WLAN]: Known as “Fat Access Point” or “Fat AP” architecture where all functionality is coded into every access point — or wireless termination point.
		![[Pasted image 20250318202824.png]]
	- [Centralized WLAN Architecture]: Known as a switched WLAN system. In this type of system, the access points become “Thin” or “Lightweight” and there is a central switch or access point controller that actually manages them. With a centralized (or switched) WLAN system, the access point controllers are the managed devices. This reduces the management problem by at least a factor of 10. 
		![[Pasted image 20250318202946.png]]
		- Switched WLAN systems are physically more secure than other architectures. The access point controller may be installed in a locked data closet or data center and the thin access points are a less likely target for theft as, without the controller, they can’t be used. 
			
		- In addition to this, these access points typically don’t store any configuration data or admin user credentials. The access point controller can also include a powerful network processor that can provide value added functionality, such as security and access control, VLAN management and manipulation, user roaming between access points and quality of service.
		
	- [Distributed WLAN]: Known as a wireless mesh. A wireless mesh can be used to create a dynamic network in environments where cabling would be impossible.
		
	- [802.11 Group of Standard]: Defines the variety of connection type and standards for Layer 1 and Layer 2. 
		802.11 (Legacy): Frequency-hopping spread spectrum, or FHSS, and direct sequence spread spectrum, or DSSS, modulation were used by these standards to control interference.
		802.11a: The new OFDM modulation technique also further reduced issues with interference and increased the stability of wireless connections.
		802.11n: Introduced a multi-input, multi-output physical layer, which uses multiple wireless signals to greatly increase the amount of bandwidth that can be transmitted simultaneously. 
		![[Pasted image 20250318204153.png]]
		- The standards at Layer 2 primarily control who may use the wireless channel at any point in time. The primary access method is Carrier Sense Multiple Access/Collision avoidance, or CSMA/CA. A wireless client cannot detect collisions while it is transmitting. So it relies on receiving positive acknowledgements from the access point to confirm that data was received. 
			![[Pasted image 20250318204549.png]]
		- In addition to CSMA/CA, Virtual Collision Detection, and Asynchronous Data Transfers, other important specifications at this layer control security — so access control authentication and encryption— roaming between access points, power save specifications, and Quality of Service.
		![[Pasted image 20250318204925.png]]
		- [Frame Control]: Contains a set of flags to indicate: Type and Subtype of frame, coming from or going to the distribution system, whether there are more fragments of a frame, whether access point has more frames to send, a retry of frame or not. It also have power management, protected frames and other flags.\
			
			- Common Control types: 
				1. [Data frames]: Include regular data that is being transmitted and certain types of special messages intended for the access point.![[Pasted image 20250318210411.png]]
				2. [Control frames]: Are things like request to send, clear to send, and acknowledgement frames.![[Pasted image 20250318210426.png]]
				3. [Management frames]: Include things like beacons sent by access points to advertise the wireless network or probes sent by a client looking for a particular wireless network.![[Pasted image 20250318210438.png]]![[Pasted image 20250318210450.png]]
			
		- [Duration]: Specifies a time interval during which other clients that read this signal should not transmit data.
			
		- [Third Access]: Either the original source MAC address or the ultimate destination MAC address of this particular frame.
			
		- [Sequence Control]: Contains sequence and fragment numbers to help the receiving reassemble frames and fragmented frames in the intended order.
			
		- [Fourth Access]: Used only in what is called a "wireless distribution system" where data is actually being replaced between the access points.
		
	- [Passive Scanning]: A process to find access point by listening to access beacons.
		
	- [Active Scanning]: Probing for a particular network. The client then sends an association management frame to the access point. The access point responds with an association ID, accepting the association, then the client is on the network. 
		
	- [Roaming]: Sending re-association request and awaits for new association ID.
		
	- [Hidden Node Problem]: This problem can occur when there are two clients on either side of an access point which are within range of the access point, but which can’t actually hear each other’s transmissions.
		
		- The method is resolve this was CSMA/CA. Another method available in 802.11 is Virtual Collision Detection, which requires the use of the Request to Send (RTS) and Clear to Send (CTS) control frames. Wireless networks can be configured to use this method for frames that are larger than a certain threshold.
		
	-  [Frame Control Settings]:
		
		- [The RTS threshold]: Can be used to specify a size of frame above which the Request to Send/Clear to Send mechanism must be used.
			
		- [Retry counters]: Specify how many times a device should try resending a frame before discarding it. A different value can be set for frames smaller or larger than the RTS threshold.
			
		- [The fragmentation threshold]: Specifies what size of packet should be split into fragments, and the fragment lifetime specifies how long fragments should be kept while waiting for related fragments to arrive.

## Routing Basic

- Small Router.![[Pasted image 20250320200248.png]]
- Router in Network Diagram.![[Pasted image 20250320200313.png]]
- In addition to a Layer 2 address brunt into it by the manufacturer, each NIC or network interface also has a Layer 3 address assigned to it by the network administrator.
	
- A Layer 3 device has 2 portions: a network number and a host number.
	
- Network administrators assign Layer 3 addresses, specifically the network number, to all devices in a network to introduce order. Layer 3 addresses provide a way of grouping network devices, for ex Layer 3 addresses could be assigned to group network devices by building, by floor, or by functional group.
	
- [Broadcast Domain]: Is the group of devices that can be reached by sending a frame addressed to the broadcast MAC address.
	![[Pasted image 20250320201412.png]]
	- [Broadcast MAC Address]: The address that a device uses to send data to every device within a LAN either directly or by way of a bridge or a switch.
		
	- Each device in a broadcast domain has the same network portion of their Layer 3 address, and each has a unique host number.
	
- [Address Resolution]: The process of using Layer 3 address to determine Layer 2 address. 
	
	- First, it sends a broadcast frame to retrieve the target MAC address and then the target check whether it is the recipient. After that it reply by sending a frame back to the sender device along with it's information. Now since the two device knows each other addresses, it can now communicate via unicast for direct communication.
		`Sender Frame:`
		![[Pasted image 20250320202418.png]]
		`Recipient Frame:`![[Pasted image 20250320202450.png]]
	 
- [Address Resolution Protocol (ARP)]: For TCP/IP network, ARP maps an IP address, which is Layer 3 address, to a Layer 2 address.
	
- [Routers]: Used to breaking up broadcast domains. Where switches allow communication within a broadcast domain, routers allow communication between broadcast domains. Each broadcast domains becomes a separate network. Within a group of interconnected networks, each network or broadcast domain must have a unique network number.
	
	- Within each network, each device has a Layer 3 address, consisting of its network number and unique host number within that network, and each device has a Layer 2 or MAC address. In addition, each port or interface on the router also requires a Layer 3 address and an associated Layer 2 address.
		![[Pasted image 20250320203445.png]] 
	- A router is a Layer 3 device and forwards data from a network to another. To facilitate communication, the router must know how to reach other networks. Routers can learn this information dynamically through routing protocols such as Routing Information Protocol (RIP) or the Open Shortest Path First protocol or OSPF. In order to do so you must establish a **routing table** that includes the destination network number, the next hop along the way to the destination network, which port or interface on the router should reach the next hop. The "Next Hop" address either indicates that the destinated network is directly connected to the router or provides the address of another router on a directly connected network.
		
	- Many networks administrators usually set a default route which way to route the packet if it encounters one with a network number that is not listed in its own routing table.
		![[Pasted image 20250322230200.png]]![[Pasted image 20250322230214.png]]
	
- [Default Gateway]: A device, such as a router, which serves as a door or an access point to another network. End-user devices send packet to their configured default gateway when the destination network number is not the same as their network number.
	
- [Different Layer Technology]: Ethernet, FDDI, Frame Relay, ATM have unique Layer 2 format. Since the router strip of the original Layer 2 frame, performs route lookup, routers can also connect different types of Layer 2 Networks.
	
- [FDDI Format]: A format that was used after the router strip off the original frame format it through a default gateway.
	![[Pasted image 20250322232105.png]]

## IP Addressing

- [Internet Protocol]: The most common Layer 3 protocol. Layer 3 addresses known as IP Addresses. The Internet protocol uses these addresses to transmit data from a source network device to a destination network device. It also performs other services such as fragmentation and reassembly of data.
	
- [IPv4]: The most commonly used protocol. ![[Pasted image 20250325161144.png]]
	
- [IPv6]: Next-generation protocol. ![[Pasted image 20250325161241.png]]
	
- The major difference is the size of the 2 addresses.
	
- [IP Functionality]: When a computer needs to send data, the Internet Layer adds an IP header to the data to form an IP packet, also known as an IP datagram. In addition, it  includes many fields.
	![[Pasted image 20250325161533.png]]
	- [Source IP Address]: This field specifies the 32-bit IP Address of the originator of the IP packet.
		
	- [Destination IP Address]: This field specifies the 32-bit IP Address of the destination of the IP packet.
	
- [IP Address Portion]: Consists of 32-bit which includes A **Network Portion** and a **Host Portion**.
	
	- Routers uses addresses the different way, the dotted format was just a simpler format for human. Routers use addresses in binary format, which is their native format.
		![[Pasted image 20250325164659.png]]
	- Each number in the dotted decimal format represents an 8-bit binary number. Each one and zero is a single bit. So, an IP address is actually a 32-bit number that is separated into 4 groups of 8 bits each.
		
	- Some of them are used for Network Prefix and the rest are used for Host Prefix. They do not have fixed value.
		
	- [Network Mask, Netmasks, Address Mask, Subnet Masks]: Used to identify the network portion of an IP Address. Assigned my network administrator.
		
	- The IP address and network mask together identify which bits are used for the network prefix and which bits are used for the host portion. In a mask, if a bit is turned on—in other words, if it’s a ‘1’--the corresponding bit in the IP address is used for the network prefix. If a bit is turned off (or a ‘0’) in the network mask, the corresponding bit in the IP address is used for the host portion.
		![[Pasted image 20250325173122.png]]
	- IPv4 addresses use decimal numbers, MAC and IPv6 addresses use hexadecimal numbers.
	
- [Broadcast MAC Address]: Consists of 48 bits set to 1. In hexadecimal, ffff.ffff.ffff .
	
- [Network Number]: Determined by network mask, the bits that are turned on in the network mask designate the part of the address that is the network number. 
	![[Pasted image 20250325183143.png]]
	- When a device needs to determine its network number, it compares each bit in its IP address with each bit in its network mask. If both bits are a 1, the device sets the corresponding network bit to a 1. If either bit is a zero, the device sets the corresponding network bit to a zero. 
		![[Pasted image 20250325183418.png]]
	
- [CIDR Notation]: Classless Inter-Domain Routing, also known as the "slash notation", the address is still shown using dotted decimal, but it is followed by a "forward slash" and the number of bits used in the network prefix. The number after the slash is also known as he prefix length. It can also be used to indentify a range of addresses.
	![[Pasted image 20250401155957.png]]
	- [Classful and Classless Routing and CIDR Notation]: IP network numbers always fell on an octet boundary. This scheme divided the IP address space into different size chunks or classes of addresses based on how many octets are used for the network portion and how many are used for the host number.
		![[Pasted image 20250401202116.png]]
	- The address class is actually encoded into the first few bits of the IP address as shown in the table on screen. If the first bit was a zero, then it was a Class A network. If not, the router looked at the second bit. If this bit was a zero, then it was a Class B network. And finally, if the third bit was a zero, then it was a Class C network. This scheme came to be known as “classful” IP addressing where 192.168.1.0 is an example of a Class C network.
		![[Pasted image 20250401202248.png]]![[Pasted image 20250401202321.png]]
	- [CIDR Routing Table Entry]: Reduce the size of routing tables by summarizing many "classful" network numbers into a single table entry.
		![[Pasted image 20250401202529.png]]
	- [Network Mask with CIDR Notation]: Based on the network masked that was displayed using the CIDR notation, the machine determine the IP Address to whether the send data directly or to the default gateway.
	
- [Network Masks and Host Numbers]: Devices use network masks to determine their network prefix. But, a network mask also identifies the valid host numbers on a given network. In any network, the first address, where all host bits are set to 0, identifies the network number. The last address, where all host bits are set to 1, is always reserved as the broadcast address for the network. You might remember that a broadcast address is an IP address that allows information to be sent to all devices on a given network. All numbers except these two reserved numbers are valid host numbers.
	![[Pasted image 20250401203103.png]]
	- [Host Number Formula]: `2^(# of host bits) - 2`
		
	- If more host addresses are needed, a change in network  mask size is required.
	
- [IP Subnetting]: Means taking a single network number and splitting it into smaller networks-or subnets-which is short for sub-networks.
	
	- To create a subnet, you change the size of the network mask. More network bits means fewer host bits, more host bits mean fewer network bits.
		![[Pasted image 20250401204054.png]]****
	- The decimal equivalent for the last octet of network bits is equal the total of `2^n` that was flipped to 1, in this case was `128+64+32+16 = 240`. The full subnet mask, in this case `255.255.255.240` leaving the prefix length equal to 28.
	
- [Network Prefix on Octet Boundary]: If a network prefix does not falls on an Octet Boundary it is impossible to determine the actual subnet number without the mask.
	
- [ISP]: Internet Service Providers provides Companies or Organizations an IP Address. Some are reserved for specific uses. Companies are free to use IP addresses out of the private address space within their internal network, which is also known as an intranet. Companies must not use these networks outside their intranet, because these same private addresses are used by many other companies as well as home networks.
	
- [Loopback Interfaces]: A virtual software interface not associated with or connected to any hardware that a device uses to send a message back to itself. Mostly uses for testing and troubleshooting. It can be used to connect to a local server without actual network connection, useful for testing service without exposing them to the security risks of accessing them through the network.
	
- [Multicast IP Address]: To send the same data to a group of devices.
	
- Routers uses static routes and dynamic routing protocols such as OSPF (Open Shortest Path First) or IS-IS (Intermediate System to Intermediate System) to learn about remote networks and build their routing table.
	
- [Route Summarization]: Or Route Aggregation combines a group of network numbers into a single route. Route aggregation makes routing traffic across the network and the Internet much more efficient as there are fewer routes in the routing table and fewer routes to advertise. 
	
- [Longest Match Routing]: Is the matching based on the CIDR notation where the Routing Table Entry shows the longest and most specific match for the destination address.
	![[Pasted image 20250401212641.png]]
- [MTU]: Maximum Transmission Unit, the fixed upper limit on the size of a packet that can be sent in a single frame.
	![[Pasted image 20250401214025.png]]
- [IP Fragmentation]: If a packet is bigger than the MTU of the Layer 2 technology, a device might need to break the packet into several pieces or fragments. The fragments are then sent individually and reassembled into the original packet by the receiving device. Each fragment contains an IP header that duplicates most of the original header followed by as much data as can be carried to keep the total length smaller than the network’s MTU. The fragments are now sent as separate packets until they reach the destination host, where they are reassembled.
	
- [IPv4 vs IPv6]:
	
	- IPv6 has 4 times the size of IPv4, 128 bits to 32 bits. The larger address size meaning that the suppl for addresses wont exhaust for many years.
		
	- IPv6 eliminates the need for Network Address Translation thanks to its huge number of IP Address available. Reduces administrative overhead. Host can use stateless autoconfiguartion or DHCPv6 (Dynamic Host Configuration Protocol) to assign an IP address to themselves. Supports greater levels of security. Makes processing more efficient in several ways.
		
	- Fixed length header, solve the optional field consumption. Removed Header Checksum to simplify processing and push the error checking to Layer 4. Removed Identification, Flags, and Fragment Offset, since routers do not  fragment IPv6 packets, hosts are responsible to do all of this. Protocol is replaced with Next Header field.
		![[Pasted image 20250401220011.png]]![[Pasted image 20250401215557.png]]![[Pasted image 20250401215614.png]]
	- IPv6 introduce the addition of number of extension, however this does not decrease the processing speed, since these extensions are examined by endpoint devices not routers.
		![[Pasted image 20250401215941.png]]
	- New field: Flow Control, Used or QoS (Quality of Service) management.
		
	- [IPv6 Header]: ![[Pasted image 20250401220219.png]]
- [IPv6 Addressing]: IPv6 presents a 128-bit address in eight 16-bit hexadecimal sections separated by colons. However, IPv6 does allow for abbreviation.
	![[Pasted image 20250401220410.png]]
	- Four consecutive zeros in an address can be identified as a single zero.
		
	- You can also omit leading zeros from the notation.
		
	- A double colon can replace consecutive zeros, leading zeros, or trailing zeros; however, you can not use a double colon twice in an address notation. Doing so will result in the misinterpretation of the IP address.
		
	- Are not case sensitive.
		
	- [RFC 5952 Requirement]: The document specifies that this format should be followed by people and systems when representing IPv6 addresses as text, but systems should be able to accept and handle any legitimate IPv6 format.
		
		1. Leading zeros MUST be suppressed.
		2. The use of the double colon symbol must be used to its maximum capability.
		3. All letters should be represented in lowercase.
		4. When an alternative choice exists in the placement of a “::” (double-colon symbol), the longest run of consecutive 16-bit zero fields must be shortened.
		5. The double colon symbol must NOT be used to shorten just one 16-bit field. When the length of the consecutive 16-bit 0 fields are equal, the first sequence of zero bits must be shortened using the double colon.
		6. When the length of the consecutive 16-bit 0 fields are equal, the first sequence of zero bits must be shortened using the double colon.
		
	- Carry the same concept when it comes to Network Prefix and Host Portion. But Host portion is often called Interface ID. In the network prefix, it consist of 2, Global Routing Prefix, Subnet ID.
	
- [IPv6 Subnetting]: Can be achieve by changing the size of the Subnet ID.
	
	- Note that the first address ends with "001" not "000".
		
	- The first address in a subnet is the "anycast address". A packet sent to this address will be routed to the nearest interface in that subnet.
		
	- IPv6 does not use broadcast.
	
- [Reserved Prefix]: 
	![[Pasted image 20250401221925.png]]

## WAN Technologies

- LANs are built, owned, and operated by individual companies and organizations. WANs are own by third-party service providers.
	
- WANs service providers are sometimes called service providers, telcos, WAN carriers, or just "carriers".
	
- Like LANs, traditional WAN protocol operates at the Physical and Data Link Layer which is Layer 1,2. Each WAN technology, such as the Point-to-Point protocol or PPP or Frame Relay, uses a different Layer 2 format and provides different options for reliability and error recovery. 
	
- [Network Cloud]: Represent the WAN or the Internet through which a data travels to get from one LAN to another. A cloud is used to represent the WAN or Internet precisely because it's nebulous and hides the details of the service provider's network links and switching equipment. 
	
- [WAN Terminology and Basic Concepts]:
	
	- [Customer Premise Equipment (CPE)]: Is any communications equipment located on the customer's premises that is used to connect to the service provider's network. The customer can own the CPE or can lease it from the service provider. 
		
	- [Central Office]: The service provider's exchange or office. Often called the distribution center, sending data to other place along the path until it's final destination. A service provider may have several CO interconnected using high-speed fiber optic trunk lines. Some COs might connect to other service providers, such as international carriers. 
		
	- [Local Loop or Last Mile]: A copper or a fiber cable connect the CPE to the nearest CO.
		
	- [Data Terminal Equipment (DTE)]: The device generating the data.
		
	- [Data Communication Equipment (DCE)]: The device that actually puts the data on the local loop, such as a modem, ensures that the data is in the correct format for the local loop.
	
- [Components of a Local Loop]: A personal computer connects to a modem, which converts digital signal to analog signal. Routers are only for digital line but uses CSU (Channel Service Unit)/ DSU (Digital Service Unit).
	
	- [CSU/DSU]: Prepare the data traffic for digital files. These can either be separate or combined device. 
		
	- [CSU]: Provides termination for the digital signal and ensures connection integrity through error correction and line monitoring. 
		
	- [DSU]: Converts the digital frames used in the service provider's network into a frame format that the router can understand and vice versa.
	
- [Digital Line]: Can either be copper or fiber, but not the one that dictate the line. Rather it is the equipment being used o the line is analog or digital. 
	
- [WAN Layer Technology]:
	
	- [Layer 1]: Analog Telephone Lines, Digital Telephone Lines, Fiber-optic Connection.
		
		- [T1 Lines]: A high-speed digital telephone line, as a Point to Point connection. The "T" stands for T-carrier system, this system combines or "multiplexes" voice and data signals from different devices within a location into a single link using **Time Division Multiplexing** or TDM. With TDM, device take turns transmitting a fixed amount of data across the link using a specific timeslot or "channel". A T1 line divides a single line into 24 different channel where each "conversation", whether voice or data, is assigned to a specific timeslot. A channel consist of 8 bits, the total is 192 with an additional bit assigned for framing and synchronization which made up a "T1 Frame", timeslot are allocate by customers.
			
		- [DS0]: The basic digital signaling rate. DS stands for Digital Signal, and is a system classifying digital circuits according to the rate and format of the signal. 24 DS0 is DS1. A DS1 is a signal lives inside the T1 Line.
			
		- [T3 and DS3]: Same concept but larger rather than DS1 it contains DS3 which have 28 DS1s, which provides bit stuffing, alignment, error checking, and in-band management.
			
		- [E1 and E3]: Same concept, European configuration according to their standards. Not compatible with T1 and T3.
			
		- [Fiber Optic Lines]: have Synchronous Optical Network (SONET) for North America, Synchronous Digital Hierarchy (SDH) for the rest of the world. Both of these define a basic frame format and hierarchy of signaling speed, but it is not compatible to each other.
			![[Pasted image 20250402150624.png]]![[Pasted image 20250402150644.png]]![[Pasted image 20250402150654.png]]
			- [STS]: Synchronous Transport Signal, a SONET Frame Format being carried over electronically using coaxial cabling.
				
			- [OC]: Optical Carrier, a SONET signal being carried over a fiber optic network. OC Level express the speed of an OC-n line.
				
			- [STM]: Synchronous Transport Module, a SDH Frame Format.
			
		- [OTN]: Optical Transport Network, based on wavelength division multiplexing (WDM). It transmit incoming signals simultaneously over a fiber optic line by putting each signal into a different wavelength (color) of light, on the receiving end, a de-multiplexer recognizes each different wavelength of light and turn it back into signal it receives. OTN can handle more than SONET/SDH and can be integrated with existing systems, it also provides monitoring and fault handling.
		
	- [Layer 2]: Same concept as LAN technologies but using a different technologies such as PPP, Frame Relay, ATM, Carrier Ethernet.
		
		- [PPP]: Point to Point Protocol, can transport IP traffic as well as other Layer 3 protocols. Used over leased lines as well as dial-up, broadband, and cellular connections. A packet is only encapsulated into PPP when WAN is involve, when it reaches its destination it is re-encapsulated into Ethernet frame for routing over LAN, both routers on each end of the WAN must be configured to used PPP or else they wont understand. PPP is known for connection-oriented protocol, which mean that both device must ensure they are ready to communicate before sending data.
			![[Pasted image 20250402152145.png]]
		- Formal connection establishment process is required for to communicate via PPP. First, using the Link Control Protocol (LCP), it establish a connection and configure the link, it also test the point to point line and perform a "Negotiation". Two, Authentication process. Three, a Network Control Protocol (NCP) is used to configure the Layer 3 protocols in use on the link.
			
		- [Negotiation]: It begin by sending a Configure-Request message, if a Configure-Reject occur, a Configure-Request will be resent, if an option has an unacceptable value a Configure-Nak (Negative Acknowledgement) is sent and a Configure-Request is resent, finally, if all are accepted, an Configure-Ack is sent and the two device are now connected. But for the other device to deliver message, a negotiation must be initiated, despite the other device has already been accepted to deliver to the designated device, after that a "LCP Open" status is popped up and proceed to authentication phase.
			
		- [Authentication]: Verify the identity, if denied, the physical link is terminated, if success, proceeds to NCP. PPP Authentication protocol consists of PAP (Password Authentication Protocol), CHAP (Challenge Handshake Authentication Protocol), MS-CHAP (Microsoft Variant), EAP (Extensible Authentication Protocol). It const of three simple step, the Authenticator sends a "Challenge" message, the "Caller" receive, encrypt and sent "Response" message back, the "Authenticator" send a "Success/Failure" message. This is often called a "three-way handshake".
			
		- [Configure the Layer 3 Protocol in use on the link]: This process use a Network Control Protocol (NCP), to establish and configure the different Layer 3 protocol running over the connection. Device in IP-based Network uses IP Control Protocol. When establish connection, both sides of the WAN must agree on everything before the data can be transmitted on the link, including which IP address will be used.
			
		- [IPCP]: A process where a device sends Config-Request to another device and want that device to do all the work, then the other device respond with a Config-Nak with the alternate address, then the sender send an Config-Ack or Nak after accepting the other device address.
			
		- [Keepalives]: The connection is maintain by sending periodic messages.
			![[Pasted image 20250402204919.png]]![[Pasted image 20250402204937.png]]![[Pasted image 20250402204949.png]]![[Pasted image 20250402204956.png]]![[Pasted image 20250402205002.png]]![[Pasted image 20250402205010.png]]![[Pasted image 20250402205017.png]]![[Pasted image 20250402205022.png]]
		- [PPP Limitations]: Require a dedicated circuits between each location, which is expensive.
			
		- [Frame Relay]: Establish a virtual connection through a configured virtual circuits. Many virtual circuit can run over a physical connection, and each of them keep the customer traffic separated. However congestion may still happen.
			
		- [ATM]: Asynchronous Transfer Mode, A cell switching technology, means that Layer 3 packet are segmented into fixed length. This allow fast circuit to be built, because switches does not have to spend time determining the start and end of a variable length frame. The fixed cell size also ensure that delay-sensitive data is not adversely affected by long data frames. ATM enables transport of voice, video, and data on the same network with guaranteed performance or quality of service for each type of traffic. Allow many people to share a service provider's network resources and create private VPNs. 
			
		- [Carrier Ethernet]: Ethernet but Carrier grade, supa fast, does not require Frame Relay or ATM experts, specialized premise equipment. Offer multiple service using single interface to customer.
	
- [Metro Ethernet Forum]: Aims to help carrier Ethernet network.
	![[Pasted image 20250402210849.png]]
	- IEEE provides standards, ITU provides telecommunication standards and recommendations for carrier Ethernet.
	
- [MEF Three Layer Model]: Like Five-Layer model, but the functionality is more tightly integrated. 
	![[Pasted image 20250402211328.png]]
	- [Application Service Layer]: Support end-user applications.
		
	- [Ethernet Service Layer]: Carries the application.
		
	- [Transport Service Layer]: Uses various networking and media types to deliver the Ethernet service.
	![[Pasted image 20250402211516.png]]
	- [Data Plane]: Handles data according to the rules or logic in place.
		
	- [Control Plane]: Instruct the data plane on how to process data.
		
	- [Management Plane]: Provides administrative interface allowing for configuration.
	
- [MPLS]: Multiprotocol Label Switching, provides the privacy and security of a Frame Relay or ATM networks, yet allows foe the inherent any-to-any connectivity and flexibility typical of an IP-based network.
	
	- [MPLS Domain]: A domain.
		
	- MPLS sit between Layer 2 and Layer 3, often called Layer 2.5. An encapsulation and switching technique used to route data over a WAN. Can be used over any Layer 2 technology, PPP or Ethernet.
		
	- [LSP]: Label Switched Path, are used to connect location. These start and end on providers routers.
		
	- [LSR]: Label Switching Router, running the MPLS protocol. Makes a forwarding decision based on the MPLS Label switching table.
		
	- [LER]: Label Edge Router, a special type of LSR that is responsible for assigning appropriate MPLS label to a packet. It strip off the Layer 2 packet and adds a MPLS header. It can assign labels based on Destination IP Network, Destination IP Network and Application Type, Source and Destination IP Network, Specific QoS requirement.
		
	- [FEC]: Forwarding Equivalency Class, a group of packet that will be treated or forwarded the same way within the provider's MPLS domain.
		
	- [Transit Label Switching Router]: A transit LSR routes based on MPLS labels only.
		
	- MPLS label-based switching method allow routers to make forwarding decisions based on the contents of a simple label.
	
- [IP Routing vs MPLS Label Switching]: IP routing is a repetitive process. MPLS consist of 4 router:
	
	- [Ingress LSR]: Examine IP header, Assign to FEC, add MPLS header, encapsulate and forward.
		
	- [Transit LSR]: There are two which examine MPLS header, perform label look up and swap, encapsulate and forward.
		
	- [Egress LSR]: Remove MPLS header, examine IP header, perform longest match loop up, encapsulate and forward.
	
- [MPLS Header]: Sometimes called shim header.
	![[Pasted image 20250402214147.png]]
	- [MPLS Label]: Contains a 20 bit locally significant value specifying the packet belongs to a certain LSP.
		
	- [Experimental Bit]: Used for QoS. 
		
	- [Bottom of Stack Bit]: Indicate where an IP packet or another MPLS header follows the current MPLS header, if the bit is set to one, an IP header is next, if it is set to zero, another MPLS header follows.
		
	- [TTL]: Often called Time To Live, used to prevent looping MPLS packets in the network. Each LSR decrement this field by 1, when the value is zero, the LSR drop the packet. By default, the ingress LSR copies the IP header's TTL field when it adds the MPLS header. The egress LSR copies the MPLS TTL value back to the IP packet when the label is removed.
	
- [MPLS Services]: 
	![[Pasted image 20250402214645.png]]

## Transport Layer Protocol

- Data get route to the correct computer with the help of IP and other lower layer protocols, such as Ethernet. The Transport Layer protocols is getting the data from one application program to the correct application program on another, it enable true end-to-end or application-to-application communication.
	
- User Datagram Protocol (UDP), and the Transmission Control Protocol (TCP), bridge the gap between the lower layer, which are responsible for data delivery and the Application layer. These utilize software ports to help route data to the correct application, the destination port provides a way of getting the data to the correct Application Layer protocol and ultimately the correct application program. The source port uniquely identifies the connection on the sending side.
	
- Transport Layer also multiplexes data, which are provided by UDP and TCP. 
	
- Software ports are specific to the Transport Layer, and are used to route data to the appropriate Application Layer protocol and ultimately the correct application program. Hardware ports are also known as NICs (Network Interface Card), operates at Layer 1. IP Interfaces (Layer 3).
	
	- [Port Field]: A 16 bit field, allowing for port numbers ranging from 0-65535.
		![[Pasted image 20250402221425.png]]![[Pasted image 20250402221440.png]]![[Pasted image 20250402221449.png]]![[Pasted image 20250402221509.png]]
	
- [Data Multiplexing]: Combines all the different types of data into a single stream, down to IP Interface. At Transport Layer, UDP/TCP add a header to data that includes the sources and destination port number. At Network Layer, the IP interface adds the source and destination IP addresses. At Data Link Layer, framing information was added. At Physical Layer, frames is converted to an electrical signal and transmitted. On the receiving end the process is reserved. At the end the single data stream is de-multiplexed into multiple stream going to the appropriate Application Layer Protocol.
	
- [UDP Protocol]: The simplest and fastest transport protocol. Includes 4 field, 2 of which are port numbers.
	![[Pasted image 20250402222330.png]]![[Pasted image 20250402222409.png]]![[Pasted image 20250402222416.png]]
	- Limited error checking, no recovery, checksum is optional, Application using UDP interact almost directly with IP in Network Layer. Since it only has 4 fields, it is often referred as a "datagram" rather than a segment, after an IP header was added, a packet was created.
	![[Pasted image 20250402222721.png]]
	- UDP is Connectionless Service, Unreliable Protocol. It transmit as fast as it could. Example of application uses UDP: DNS Domain Name System, TFTP Trivial File Transfer Protocol, SNMP Simple Network Management Protocol, Streaming video and audio application.
		
	- [DNS Server]: Known as server, searches its database for the requested name and sends back a response that includes the requested domain name and IP address. The DNS application on the sending computer waits for a reply from the DNS server. If it does not receive a DNS reply, it could got dropped, it tries again or sent to a different DNS server.
	
- [TCP Protocol]: Connection-Oriented, computer exchanges messages in a "three-way handshake". Ordered data, duplicate detection, and flow control.
	![[Pasted image 20250403150403.png]]
	- [Source Port]: The 16-bit field indicates the port number of the sending Application Layer protocol. Any replies should be sent to this port number.
		
	- [Destination Port]: The 16-bit field indicates the port number of the receiving Application Layer protocol.
		
	- [Sequence Number]: A 32-bit number field used to track and reorder segment. Specifically, the sequence number of the first byte of data in this segment. If the SYN (Synchronize Packet) flag is set, the sequence number is the initial sequence number or ISN.
		
	- [Acknowledge Number]: A 32-bit field identifying the next sequence number the sender expects to receive. Therefore, the number will be one more than the most recently received data byte.
		
	- [Data Offset]: This 4 bit field is the number of 32-bit words in the TCP header. It indicates where the data begins.
		
	- [Reserved]: 4 Bit that are allocated for future use. Set to 0 be default.
		
	- [8 Flag/Control Bit]: 
		
		- [CWR and ECE]: The Congestion Window Reduced, or CWR flag, and the Explicit Congestion Notification Echo, or ECE flag, are used to negotiate congestion notification capabilities.
			
		- [URG]: The urgent flag indicates that the Urgent Pointer is in use.
			
		- [ACK]: The acknowledge flag indicates that the Acknowledge Number field is in use.
			
		- [PSH]: The push flag tells the receiver to deliver or push this segment to the receiving Application Layer Protocol as soon as possible.
			
		- [RST]: The reset flag tells the receiver that the sender is ending the connection. All queued data and allocated buffers should be released.
			
		- [SYN]: The sender uses the synchronization flag during connection setup to synchronize the sequence number.
			
		- [FIN]: The finish flag indicates that the sender has no more data to transmit.
		
	- [Window]: This 16-bit field specifies the number of bytes that the sender of this segment can receive.
		
	- [Checksum]: A 16-bit field that validates the entire segment, both header and data.
		
	- [Urgent Pointer]: A 16-bit fields indicates where the urgent data is within the data field. Is only valid if Urgent flag is set.
		
	- [Options]: Control window size, maximum segment size, or additional functions required by the upper layer application generating the data.
	
- [Application Layer Protocol using TCP]: 
	
	- [Hypertext Transfer Protocol (HTTP)]: A communications protocol for the transfer of information on the internet and the World Wide Web.
		
	- [Simple Mail Transfer Protocol (SMTP)]: For sending electronic mail on the Internet.
		
	- [File Transfer Protocol (FTP)]: Used for transfer data from one computer to another through a network, such as over the Internet.
	
- [TCP in Action]:
	![[Pasted image 20250403154514.png]]
- [URLs]: Stand for Uniform Resource Locator, the address of a Webpage on the Internet.
	![[Pasted image 20250403154907.png]]
	- The firs part of the URL is the Application Layer Protocol. The second part of the URL, `www.juniper.net` is the domain name of the web server. The last part of the URL is the path, often refer to a file location of the file on the webserver.
	
- [TCP Three-Way Handshake]: 
	![[Pasted image 20250403160430.png]]
	- Client starts a TCP connection with initial sequence. 
		
	- Server responds with its own initial sequence, and the client's next sequence. And turn ACK flag to 1.
		
	- Client acknowledges server's next sequence and send back the ACK flag.
	
- Once the TCP connection is established, the PC's Web Browser application communicates with the Webserver using HTTP as the Application Layer protocol to send data across the TCP connection. 
	![[Pasted image 20250403160419.png]]
	- [HTTP Client]: Also known as the Web Browser.
		
	- [HTTP Server]: Known as the webserver.
		
	- The HTTP client first sends out a HTTP GET messages that includes the requested resources (Webpage), and the name of the server.
		
	- The HTTP Server then responds with a status message and response code. This response might indicate success or failure, or might redirect the client to a different webserver. A success message might include the requested resources or Webpage using HTML, or the client might need to send additional HTTP GET messages to the webserver to which the server responds.
	
- [Key TCP Operation]: Application Layer protocols send data to TCP as a continuous stream of bites. TCP group bits into bytes, and bytes into manageable chunks or segments that can be one byte or many bytes in length. Each byte of data sent over a TCP connection has a sequence number. Each byte is acknowledged. Sequence number are used for acknowledge which data has been received, determine if the data has been lost or damaged, put the data into the correct order.


