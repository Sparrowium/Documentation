[[Junos Lab]]
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

<h2 style="color:#6290C3"><center> SSH and Operation Mode </center></h2>
## Understanding the Network

- Internet connection is connected to the Router because the Router connect many subnets together while the switch connect devices within a subnet.
## Using SSH to Remotely Connect to the Junos CLI

- Using Protocol, Username, Password, Router's IP Address.
	
- There are two protocols that can create remote CLI connections:
	
	- [Telnet]: Unencrypted, insecure. Operates on TCP port 23.
		
	- [SSH (Secure Shell)]: Encrypted, secure. Operates on TCP port 22.
	
- When SSH or Telnet do a device, a user account is needed, which consist of username and password. Then you use terminal application to access the local command line.
	
- For remote connection you will need a Protocol, Username, Password, Router's IP. To SSH to a device, it can be done via Terminal Application.
	
- Syntax: `ssh username@{ipv4 address}`.
	![[Pasted image 20250414185052.png]]
	- A successful SSH session will show The Last Login Date, The JunOS version, A shell prompt.
		
	- When SSH to a device for a first time a warning will appear.
		![[Pasted image 20250414185403.png]]
	- If this warning appear when a device is already trusted. It could be a hardware fault, or a fake device. 

## Junos CLI: Operation Mode

- Are the default mode if you SSH with a non-root username. You can verify and troubleshoot almost anything in operational mode, this includes clear statistics and perform administrative tasks such as rebooting the device. Whenever the CLI program ends in a **greater-than sign (>) you are in operational mode**, you will also get a new blank shell prompt every time you press the return key.
	
	- [Verification]: Confirm an interface is working, verify any protocols, read the configuration, verify system/hardware status, ...
		
	- [Administration]: Upgrade device software, shut down/reboot the device, clear up old files, generate "support information", ...
		
	- [Troubleshooting]: Ping and trace-route to IPs, read log files, clear interface counters, view protocol traffic in real time, ...
		
	- However, configuration can't be changed.
	
- To configure the device, you go into a dedicated "configuration mode".
	![[Pasted image 20250414190534.png]]
	- The configuration mode is separated from the operational mode to prevent deploying changes by mistake, keeping different commands in different mode.
	
- [Four Important Operational Mode Command]: The basic and essentials command for Junos CLI. 
	
	- [show and monitor]: To verify things, such as, Interface info, device status, protocol state, ... The commands begin with `show` or `monitor`, followed by the name of the protocol, and perhaps an extra keyword to specify the information.
		
		- The show commands show information about an interface such as: error counters at the initial state, total count of packets in and out at initial state.
			![[Pasted image 20250414191147.png]] 
		- The monitor commands show the interface throughput at real time and see the actual messages that protocols are sending and receiving in real time.
			![[Pasted image 20250414191336.png]]
		
	- [clear and request]: Are used in advanced situations such as troubleshooting, performing admin tasks.
		![[Pasted image 20250414191522.png]]![[Pasted image 20250414191529.png]]
	
- Some useful show commands: 
	
	- `show system uptime`
		![[Pasted image 20250414192213.png]]
	- `show system information`
		![[Pasted image 20250414192302.png]]
	- `show route`: Show the routing table.
	
- [LLDP]: Link Layer Discovery Protocol. Discovers directly connected devices. Devices can send LLDP messages to advertise their hostname, port-names, macs, poe, vendor name, ...
	![[Pasted image 20250414193413.png]]

## CLI Built-in Command Reminders, Auto-Completion, Junos Hierarchy

- Pressing up and down to browse your command history.
	
- Type `show system ?` to view available commands.
	
- Typing the first few letters and then pressing *tab* or *space*, junos will auto complete the rest. *tab* also auto-completes objects you've configured-firewall rules, named lists of IPs, ...
	
- If the first few letter words isn't unique, Junos CLI will gives a list of options that begin with that letter.
	
- Everything in Junos is hierarchical.
