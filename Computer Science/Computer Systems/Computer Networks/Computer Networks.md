A set of computers sharing resources located on or provided by network nodes.

<h2 style="color:#6290C3"><center> Basic </center></h2>
## What is Computer Networks?

- Computer Networks is a set of computers sharing resources located on or provided by network nodes
	
- Computer use common **communication protocols** over **digital interconnections** to communicate with each other. These interconnections are made up of **telecommunications network** technologies based on physically *wired, optical, and wireless radio frequency* methods that may be arranged in a variety of network topologies.
	
- [Nodes]: Include *personal computer*, *servers*, *networking hardware*, or other specialized or general-purposed **hosts**. They are identified by **network addresses** and may have **hostnames**.
	
- [Hostnames]: Serve as memorable labels for the nodes and are rarely changed after initial assignment. 
	
- [Network Addresses]: Serve for locating and identifying the nodes by communications protocols such ass the **internet protocol**.
	
- Computer networks may be classified by many criteria, including the *transmissions medium* used to carry signals, **bandwidth**, **communication protocols** to organize **network traffic**, the network size, the topology, **traffic control** mechanisms, and organizational intent.

## What is the Use of Computer Networks? 

- Computer networks enhance how users communicate with each other by using various electronic methods like email, instant messaging, online chat, voice and voice calls, and video conferencing. 
	
- Networks also enable the sharing of computing resources.
	
- Networks allow for the sharing of files and information, giving authorized users access to data stored on other computers or devices.

## Network Packet

- A formatted unit of data carried by a **packet-switched network**.
	
- Packets consist of two types of data: Control Information and User Data (payload). 
	
	- [Control Information]: Provides data the network needs to deliver the user data, for example, source and destination network addresses, error detection codes, and sequencing information. Typically, control information is found in packet headers and trailers, with payload data in between.
		
	- [Payload]: The part of the transmitted data that is the actual intended message.
	
- In packet switching, the bandwidth of the transmission medium is shared between multiple communication sessions, in contrast to circuit switching, in which circuits are preallocated for the duration of one session and data is typically transmitted as a continuous bit stream.
### Terminology

- In the seven-layer **OSI model** of computer networking, *packet* strictly refer to a *protocol data unit* at layer 3, the **network layer**.
### Architecture

- The basis of packet concept is the postal letter: the header is like the envelope, the payload is the entire content inside the envelope, and the footer would be your signature at the bottom.
### Contents

- A packet may contain any of the following components:
	
	- [Addresses]: The routing of network packets requires two network addresses, the source address of the sending host, and the destination of the receiving host.
		
	- [Error Detection and Correction]: Performed at various layers in the protocol stack. Network packets may contain a checksum, party bit or cyclic redundancy checks to detect errors that occur during transmission. At the transmitter, the calculation is performed before the packet is sent. When received at the destination, the checksum is recalculated, and compared with the one in the packet. If discrepancies are found, the packet may be corrected or discarded. Any packet loss due to these discards is dealt with by the network protocol.
		
	- [Hop Limit]: Under fault conditions, packets can end up traversing a closed circuit. If nothing was done, eventually the number of packets circulating would build up until the network was congested to the point of failure. **Time to live** is a field that is decreased by one each time a packet go through a network hop. If the field reaches zero, routing has failed, and the packet if discarded.
		
	- [Length]: There may be a field to identify the overall packet length. In some type of networks, the length is implied by the duration of the transmission.
		
	- [Protocol Identifier]: Specifies a packet's protocol and allows the protocol stack to process many types of packets.
		
	- [Priority]: The priority of a packet, usually helps with congestion.
		
	- [Payload]: The data that is carried on behalf of an application. It is usually of variable length, up to a maximum that is set by the network protocol and sometimes the equipment on the route. When necessary, some networks can break a larger packet into smaller packets.

## Network Topology

- The arrangement of the elements (links, nodes, ...) of a communication network. 
	
- The topological structure of a network and may be depicted physically or logically. It is an application of graph theory wherein communicating devices are modeled as nodes and the connections between the devices are modeled as links or lines between the nodes.
	
- [Physical Topology]: The placement of the various components of a network. Or, the transmission medium layout used to link devices is the physical topology of the network.
	
- [Logical Topology]: How data flows within a network or the way that the data passes through the network from one to another without regard to the physical interconnection of devices.
	
- Distances between nodes, physical interconnections, transmissions rates, or signal types may differ between two different networks, yet their logical topologies may be identical.
	
- A network's physical topology is a concern of the physical layers of the **OSI Model**.
	
- Common Topologies:
	![[Pasted image 20250313194214.png]]
	- [Bus Network]: All nodes are connected to a common medium along this medium. This was the layout used in the original Ethernet, called 10BASE5 and 10BASE2. This is still a common topology on the data link layer, although modern physical layer variants use point-to-point links instead, forming a star or a tree.
		
	- [Star Network]: All nodes are connected to a special central node. This is the typical layout found in a small switched Ethernet LAN, where each client connects to a central network switch, and logically in a wireless LAN, where each wireless client associates with the central wireless access point.
		
	- [Ring Network]: Each node is connected to its left and right neighbor node, such that all nodes are connected and that each node can reach each other node by traversing nodes left- or rightwards. Token ring networks, and the Fiber Distributed Data Interface (FDDI), made use of such a topology.
		
	- [Mesh Network]: Each node is connected to an arbitrary number of neighbors in such a way that there is at least one traversal from any node to any other.
		
	- [Fully Connected Network]: Each node is connected to every other node in the network.
		
	- [Tree Network]: Nodes are arranged hierarchically. This is the natural topology for a larger Ethernet network with multiple switches and without redundant meshing.
	
- [Overlay Network]: A virtual network that is built on top of another network. Nodes in the overlay network are connected by virtual or logical links. Each link corresponds to a path, perhaps through many physical links in the underlying network. 
	![[Pasted image 20250313194630.png]]
## Network Links

- [Transmission Media]: Are resources used to link devices to form a computer. These includes:
	
	- [Electrical Cables]: Ethernet, Power Line Communication, etc.
		
	- [Optical Fiber]: Fiber optic communication.
		
	- [Radio Waves]: Wireless networking. 
		
	- These are defined at layers 1 and 2 - the physical layer and the data link layer.
	
- A widely adopted family of transmission media used in local are network (LAN) technology is collectively known as Ethernet. The media and protocol that enable communication between networked devices over Ethernet are defined by [IEEE 802.3](https://en.wikipedia.org/wiki/IEEE_802.3). Ethernet transmit data over both copper and fiber cables. Wireless LAN standards ([IEEE 802.11](https://en.wikipedia.org/wiki/IEEE_802.11)) use radio waves, or others use infrared signals as a transmission medium. Power line communication uses a building's power cabling to transmit data. 
	
- [Wired Technology]: Connect directly through a physical medium.
	
	- [Coaxial Cable]: Used for television systems, office buildings, and other work site for local area networks. The cables consist of copper or aluminum wire surrounded by an insulating layer (typically a flexible material with a high dielectric constant), which itself is surrounded by a conductive layer. The insulation between the conductors helps maintain the characteristic impedance of the cable which can help improve its performance. Transmission speed ranges from 200 million bits per second to more than 500 million bits per second.
		
	- [Signal Traces On Printed Circuit Board]: Common for board-level serial communication, particularly between certain types integrated circuits, a common example is SPI (Serial Peripheral Interface).
		
	- [Ribbon Cable]: A cost effective media for serial protocols, especially within metallic enclosures or rolled within copper braid or foil, over short distances, or at lower data rates. Several serial network protocols can be deployed without shielded or twisted pair cabling, that is, with flat or ribbon cable, or a hybrid flat and twisted ribbon cable, should EMC, length, and bandwidth constraints permit. 
		
	- [Twisted Pair Wire]: The most widely used medium for all telecommunication. Twisted pair cabling consist of consist of copper wires that are twisted into pairs. Ordinary telephone wires consist of two insulated copper wires twisted into pairs. Computer network cabling (wired Ethernet as defined by IEEE 802.3) consists of 4 pairs of copper cabling that can be utilized for both voice and data transmission. The use of two wires twisted together helps to reduce crosstalk and electromagnetic induction. The transmission speed ranges from 2 million bits per second to 10 billion bits per second. Twisted pair cabling comes in two forms: unshielded twisted pair (UTP) and shielded twisted pair (STP).
		
	- [Optical Fiber]: A glass fiber. It carries pulses of light that represent data. Some advantages of optical fibers over metal wires are very low transmission loss and immunity from electrical interference. Optical fibers can simultaneously carry multiple wavelengths of light, which greatly increases the rate that data can be sent, and helps enable data rates of up to trillions of bits per second. Optic fibers can be used for long runs of cable carrying very high data rates, and are used for undersea communications cables to interconnect continents.
	
- [Wireless Technology]: 
	
	- [Communication Satellites]: Communicate via microwave radio waves, which are not deflected by the Earth's atmosphere. The satellites are stationed in space, typically in geostationary orbit 35,786 km (22,236 mi) above the equator. These Earth-orbiting systems are capable of receiving and relaying voice, data, and TV signals.
		
	- [Cellular and PCS Systems]: Use several radio communications technologies. The systems divide the region covered into multiple geographic areas. Each area has a low-power transmitter or radio relay antenna device to relay calls from one area to the next area.
		
	- [Radio and Spread Spectrum Technology]: Wireless local area networks use a high-frequency radio technology similar to digital cellular and a low-frequency radio technology. Wireless LANs use spread spectrum technology to enable communication between multiple devices in a limited area. Common flavor of open standard wireless radio-wave technology known as WiFi.
## Network Nodes

- [Network Interfaces]: A network interface controller (NIC) is computer hardware that computer to the network media and has the ability to process low-level network information.
	
	- In Ethernet networks, each NIC has a unique *Media Access Control (MAC) Address*-usually stored in the controller's permanent memory. To avoid address conflicts between network devices, MAC address are unique. The size of an Ethernet MAC address is six octets (6x8 bits). Three most significant octets are reserved to identify NIC manufacturers.
	
- [Repeaters and Hubs]: 
	
	- [Repeater]: An electronic device that receives a network signal, cleans it of unnecessary noise and regenerates it. The signal is re-transmitted at a higher power level, or to the other side of obstruction so that the signal can cover long distances without degradation. In most twisted-pair Ethernet configurations, repeaters are required for cable that runs longer than 100 meters. With fiber optics, repeaters can be tens or even hundreds of kilometers apart. 
		
	- Repeaters work on the physical layer of the OSI model but still require a small amount of time to regenerate the signal. This can cause a propagation delay that affects network performance and may affect proper function. As a result, many network architectures limit the number of repeaters used in a network
		
	- [Hub]: An Ethernet repeater with multiple ports. In addition to reconditioning and distributing network signals, a repeater hub assists with collision detection and fault isolation for the network.
	
- [Bridges and Switches]: Bridges only have two ports but a switch can be thought of as a multi-port bridge. Switches normally have numerous ports, facilitating a star topology for devices, and for cascading additional switches.
	
	- Bridges and switches operate at the data link layer (layer 2) of the OSI model and bridge traffic between two or more network segments to form a single local network. Both are devices that forward frames of data between ports based on the destination MAC address in each frame. They learn the association of physical ports to MAC addresses by examining the source addresses of received frames and only forward the frame when necessary. If an unknown destination MAC is targeted, the device broadcasts the request to all ports except the source, and discovers the location from the reply.
		
	- Bridges and switches divide the network's collision domain but maintain a single broadcast domain. Network segmentation through bridging and switching helps break down a large, congested network into an aggregation of smaller, more efficient networks.
	
- [Routers]: An inter-networking device that forwards packets between networks by processing the addressing or routing information included in the packet. The routing information is often processed in conjunction with the routing table. A router uses its routing table to determine where to forward packets and does not require broadcasting packets which is inefficient for very big networks.
	
- [Modems]: Are used to connect network nodes via wire not originally designed for digital network traffic, or for wireless. To do this one or more carrier signals are modulated by the digital signal to produce an analog signal that can be tailored to give the required properties for transmission.
	
- [Firewalls]: A network device or software for controlling network security and access rules. Firewalls are inserted in connections between secure internal networks and potentially insecure external networks such as the Internet. Firewalls are typically configured to reject access requests from unrecognized sources while allowing actions from recognized ones.
 ## Communication Protocols

- A set of rules for exchanging information over a network. Communication protocols have various characteristics. They may be connection-oriented or connectionless, they may use circuit mode or packet switching, and they may use hierarchical addressing or flat addressing.
	
- In a protocol stack, often constructed per the OSI model, communications functions are divided up into protocol layers, where each layer leverages the services of the layer below it until the lowest layer controls the hardware that sends information across the media. The use of protocol layering is ubiquitous across the field of computer networking.
	
- Common Protocols: TCP/IP, Ethernet,...
## Network Geographic Scale

- [Nanoscale Network]: Communication between sensors and actuators found in biological systems and other harsh environment.
	
- [Personal Area Network (PAN)]: A computer used for communication among computers and different information technological devices close to one person.
	
- [Local Area Network (LAN)]: A network that connects computers and devices in a limited geographical area such as a home, school, office building, or closely positioned group of buildings. Wired LANs are most commonly based on Ethernet technology.
	
- [Home Area Network (HAN)]: A residential LAN used for communication between digital devices typically deployed in the home, usually a small number of personal computers and accessories, such as printers and mobile computing devices. An important function is the sharing of Internet access, often a broadband service through a cable Internet access or digital subscriber line (DSL) provider.
	
- [Storage Area Network (SAN)]: A dedicated network that provides access to consolidated, block-level data storage. SANs are primarily used to make storage devices, such as disk arrays, tape libraries, and optical jukeboxes, accessible to servers so that the storage appears as locally attached devices to the operating system. A SAN typically has its own network of storage devices that are generally not accessible through the local area network by other devices.
	
- [Campus Area Network (CAN)]: Is made up of an interconnection of LANs within a limited geographical area. The networking equipment (switches, routers) and transmission media (optical fiber, Cat5 cabling, etc.) are almost entirely owned by the campus tenant or owner (an enterprise, university, government, etc.).
	
- [Backbone Network]: A part of a computer network infrastructure that provides a path for the exchange of information between different LANs or subnetworks. A backbone can tie together diverse networks within the same building, across different buildings, or over a wide area. When designing a network backbone, network performance and network congestion are critical factors to take into account. Normally, the backbone network's capacity is greater than that of the individual networks connected to it. 
	
- [Metropolitan Area Network (MAN)]: A large computer network that interconnects users with computer resources in a geographic region of the size of a metropolitan area.
	
- [Wide Area Network (WAN)]: A computer network that covers a large geographic area such as a city, country, or spans even intercontinental distances. A WAN uses a communications channel that combines many types of media such as telephone lines, cables, and airwaves. A WAN often makes use of transmission facilities provided by common carriers, such as telephone companies. WAN technologies generally function at the lower three layers of the OSI model: the physical layer, the data link layer, and the network layer.
	
- [Enterprise Private Network]: A network that a single organization builds to interconnect its office locations (e.g., production sites, head offices, remote offices, shops) so they can share computer resources.
	
- [Virtual Private Network (VPN)]: An overlay network in which some of the links between nodes are carried by open connections or virtual circuits in some larger network (e.g., the Internet) instead of by physical wires. The data link layer protocols of the virtual network are said to be tunneled through the larger network.
	
- [Global Area Network (GAN)]: A network used for supporting mobile users across an arbitrary number of wireless LANs, satellite coverage areas, etc.
## Organization Scope

- [Intranet]: A set of networks that are under the control of a single administrative entity. An intranet typically uses the Internet Protocol and IP-based tools such as web browsers and file transfer applications. The administrative entity limits the use of the intranet to its authorized users.
	
- [Extranet]: A network that is under the administrative control of a single organization but supports a limited connection to a specific external network.
	
- [Internet]: An internetwork is the connection of multiple different types of computer networks to form a single computer network using higher-layer network protocols and connecting them together using routers. The Internet is the largest example of internetwork. It is a global system of interconnected governmental, academic, corporate, public, and private computer networks. It is based on the networking technologies of the Internet protocol suite.
	
- [Darknet]: An overlay network, typically running on the Internet, that is only accessible through specialized software. It is an anonymizing network where connections are made only between trusted peers. Darknets are distinct from other distributed peer-to-peer networks as sharing is anonymous (that is, IP addresses are not publicly shared), and therefore users can communicate with little fear of governmental or corporate interference.
## Network Performance

- [Bandwidth]: In bit/s may refer to consumed bandwidth, corresponding to achieved throughput or goodput, i.e., the average rate of successful data transfer through a communication path. The throughput is affected by processes such as bandwidth shaping, bandwidth management, bandwidth throttling, bandwidth cap and bandwidth allocation.
	
- [Network Delay]: A design and performance characteristic of a telecommunications network. It specifies the latency for a bit of data to travel across the network from one communication endpoint to another. Delay may differ slightly, depending on the location of the specific pair of communicating endpoints. Engineers usually report both the maximum and average delay, and they divide the delay into several components, the sum of which is the total delay:
	
	- [Processing Delay]: Time it takes a router to process the packet header.
		
	- [Queuing delay]: Time the packet spends in routing queues.
		
	- [Transmission delay]: Time it takes to push the packet's bits onto the link.
		
	- [Propagation delay]: Time for a signal to propagate through the media.
	
- [Performance Metrics]: The parameters that affect performance typically can include throughput, jitter, bit error rate and latency. 
	
	- in circuit-switched networks, network performance is synonymous with the grade of service. The number of rejected calls is a measure of how well the network is performing under heavy traffic loads. Other types of performance measures can include the level of noise and echo.
	
- [Network Congestion]: Occur when a link or node is subjected to a greater data load than it is rated for, resulting in a deterioration of its quality of service. When networks are congested and queues become too full, packets have to be discarded, and participants must rely on retransmission to maintain reliable communications. Typical effects of congestion include queueing delay, packet loss or the blocking of new connections. A consequence of these latter two is that incremental increases in offered load lead either to only a small increase in the network throughput or to a potential reduction in network throughput. 
	
	- Network protocols that use aggressive retransmissions to compensate for packet loss tend to keep systems in a state of network congestion even after the initial load is reduced to a level that would not normally induce network congestion. Thus, networks using these protocols can exhibit two stable states under the same level of load. The stable state with low throughput is known as congestive collapse.
		
	- Modern networks use congestion control, congestion avoidance and traffic control techniques where endpoints typically slow down or sometimes even stop transmission entirely when the network is congested to try to avoid congestive collapse. Specific techniques include: exponential backoff in protocols such as 802.11's CSMA/CA and the original Ethernet, window reduction in TCP, and fair queueing in devices such as routers.
		
	- Another method to avoid the negative effects of network congestion is implementing quality of service priority schemes allowing selected traffic to bypass congestion. Priority schemes do not solve network congestion by themselves, but they help to alleviate the effects of congestion for critical services. A third method to avoid network congestion is the explicit allocation of network resources to specific flows.
	
- [Network Resilience]: Network resilience is "the ability to provide and maintain an acceptable level of service in the face of faults and challenges to normal operation.".

