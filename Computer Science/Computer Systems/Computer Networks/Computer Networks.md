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
	
- The topological structure of a network and may be depicted physically or logically. It is an application of graph theory wherein communicating devices are modeled as nodes and the connections between the devices are modelled as links or lines between the nodes.
### Topologies

- [Physical Topology]: The placement of the various components of a network. Or, the transmission medium layout used to link devices is the physical topology of the network.
	
- [Logical Topology]: How data flows within a network or the way that the data passes through the network from one to another without regard to the physical interconnection of devices.
	
- Distances between nodes, physical interconnections, transmissions rates, or signal types may differ between two different networks, yet their logical topologies may be identical.
	
- A network's physical topology is a concern of the physical layers of the **OSI Model**.
### Links

- [Transmission Media]: Are resources used to link devices to form a computer. These includes:
	
	- [Electrical Cables]: Ethernet, Power Line Communication, etc.
		
	- [Optical Fiber]: Fiber optic communication.
		
	- [Radio Waves]: Wireless networking. 
		
	- These are defined at layers 1 and 2 - the physical layer and the data link layer.
