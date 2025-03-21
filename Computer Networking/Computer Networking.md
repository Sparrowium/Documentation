
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
	
- A Layer 3 device has 2 portions a network number and a host number.
	
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
	- A router is a Layer 3 device and forwards data from a network to another