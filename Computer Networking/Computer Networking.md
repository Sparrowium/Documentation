
<h2 style="color:#6290C3"><center> Getting Started with Networking </center></h2>

## How Networks Work
### What is a Network?

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
- 