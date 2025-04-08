<h2 style="color:#6290C3"><center> Introduction </center></h2>
## Advantages of Junos CLI

- [Junos OS]: Juniper Network Operating Systems for Junos Devices including Switches, Routers, and Firewalls. It manages the power and cooling of the chassis runs the protocols that power the network, and offers various different user interfaces that you can use to manages the device.
	
- [Junos CLI]: Junos OS Command Line Interface. It offers commands to mange the user computer, as well as commands to connect to remote devices.
	
- Junos runs on routers, switches, and firewalls-of all sizes.
	
	- There are specific build for each platform.
		
	- There are certain features that are only available on certain devices.
		
	- New features are consistent across major releases.
		
	- Most platform knowledge are interchangeable.
	
- Junos configuration is presented to you in text format. Information is placed in a predictable, consistent hierarchy. In `keyword { [information] }`, the word keyword is an example of "top-level" config hierarchies. 
	![[Pasted image 20250407204903.png]]
- Junos offer verification before deployment. It lets you compare your proposed changes to the current configuration, allows you to fix or scrap before it go live.
	
- Junos offers configuration rollback up to 49 instances, without needing to reboot. Comment to each of the configuration files is also available. With 0 being the newest, active config, 49 as the oldest historical config.
	![[Pasted image 20250407205630.png]]
- You can automatically roll back to the previous configuration if a problem has occurred.
	
- Ways to manage Junos Device:
	
	- Junos CLI. Powerful and Quick.
		
	- A built-in Web interface, J-Web. Easy administration for smaller devices.
		
	- Computer Code.
		
	- External controllers that can manage all the devices in your estate.
	
- You can write code to configure and verify Junos, with automation baked into Junos. It also has APIs that enable you to write computer code that can interact with the device. Juniper Networks also had PyEZ a Python Scripting library for prewritten code for scripting.
	
- Two type of script:
	
	- [On-Box Scripts]: Save code on the device, and run it automatically, It can verify device health, status, and config, based on certain conditions.
		
	- [Off-Box Scripts]: Choose from many scripting languages, and run your code from anywhere. It may gather information and deploy changes to thousands of devices.
	
- You can manage multiple devices from a single controller to view and maintain your entire estate.
	
	- [Platform By Juniper Networks]: Has many powerful controllers for different kinds of network. Including Mist AI, Paragon Pathfinder, ...
		
	- [Third-Party Platform]: Many options that all give you the same results. Including Ansible, Puppet, ...
	
- Junos OS is modular, meaning the process inside Junos is independent from each other. 
	
	- It also contain separate hardware for processing transit traffic, and traffic that is destined to the device it self, such as traffic from protocols or management traffic. This gives you extra protection. If a routing protocol is overwhelmed, transit traffic continues to be forwarded.

## Fixed-Port Chassis, Modular Chassis, and Routing Engine

- There are two broad categories of devices that run Junos OS. Fixed-Port Devices, Modular Devices.
	
- [Fixed-Port Chassis]: A device that have physical interfaces built into the chassis. Perfect when you only need these port. Found in enterprise networks, service provider networks, data center networks.
	![[Pasted image 20250407214047.png]]
- [SFP]: Small Form-Factor Plugable (mostly for Fiber).
	
	- [QSFP]: Quad Network ports, 100GBPS. Send traffic to the core of your network.
		
	- [SFP+]: 10GBPS. For aggregating up all local traffic.
		
	- [Manage Ports]:
	
- All ports have number to identify them.
	
- [Modular Chassis]: Comes in large number of empty slot. It can be used to plug in ports or line cards. Prioritize customization.
	![[Pasted image 20250407214028.png]]
- Line cards are numbered from bottom to top. It can have Line Cards with Network Interfaces for transit traffic. Line Cards with extra features. Line Cards that host smaller interface cards that give you many custom options.
	
- [Line Cards for Routing Engine]: These cards host Routing Engine, the brain of the device. It is responsible for running protocols, deciding the best path to an IP, management traffic, chassis management, ...
	
- Fixed port have only one routing engine, while Modular chassis may host spare RE with hot-swappable feature.

## Juniper Product Set

- Based on Unit Chassis, Feature Set, Ports.
	
- [MX Routers]: Learning huge quantities of router/Macs, very fast forwarding, many protocols running at once, virtual private networks VPNs applications,  many built-in security feature.
	
	- Highly popular at the edge of the network due to lots of learning, lots of security. Often called PEs, Provider Edge.
	
- [PTX Routers]: Prioritize Speed, Packet Manipulation, Routing capabilities.
	
- [ACX Routers]: Used for aggregating multiple device up to a central location. An aggregation deice accepts many connections, and bundles that traffic along a small number of much faster connections.
	
- [SRX Firewalls]: Offer security at high-speed. Next generation firewall service, advance traffic filtering, such as application visibility and control, which means that the firewall can drill down into the actual payload of the packets to identify what kind of traffic it is.
	
	- Traffic Filtering, Anti-malware, antispam, antivirus, Advanced Threat Prevention service which includes anti malware service, traffic insights, threat profiling, Domain Name Security.
	
- [Virtual Junos OS]: Used for Cloud Environments, Virtual Labs, Hardware Routers with Virtual Capabilities.