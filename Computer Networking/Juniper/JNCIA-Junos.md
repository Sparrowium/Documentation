Associate Routing and Switching.
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

<h2 style="color:#6290C3"><center> Network Interfaces </center></h2>
## Junos Interface Naming Convention

- [Network Interface]: Process all incoming and outgoing network traffic-including traffic due to the device as well.
	
- Every network interface in Junos has a name. The letters indicate the physical interface presentation. The numbers indicate the location on the chassis. Ex: `xe-0/0/1`.
	
	- The first interface will usually be named 0.
		
	- The names do not distinguish between copper and fiber. There are 4 Ethernet names: `fe-` Fast Ethernet (100Mbps), `ge-` Gigabit Ethernet (1Gbps), `xe-` 10Gbps Ethernet, `et-` Ethernet (40Gbps and above).
		
	- In `4/1/3`, number 4 indicates the Line card slot, number 1 means an interface card within a line card or a specific section of a line card, and the number 0 means the port number itself.
	
- [PICs]: Physical Interface Card, the interface card within a line card, or a specific section of a bigger line card.
	
- [FPCs]: Flexible PIC Concentrator, the actual line card itself.
	![[Pasted image 20250415151116.png]]
- The interface naming scheme is used on all Junos devices. Every single devices has one consistent naming convention, this also includes devices without line cards.

## The show interface terse Command 
via Operational Mode

- [MTU]: Maximum Transmission Unit, the largest size packet or frame allowed on an interface.
	![[Pasted image 20250415151713.png]]
- Commands for viewing basic info, or viewing detailed statistics
	![[Pasted image 20250415152432.png]]
- Use `show interface terse` to verify the IP info and interface state.
	![[Pasted image 20250415152242.png]]
	- The local address is listed under Local.
		
	- The protocol is listed under Proto.
		
	- Junos uses *inet* for IPv4 and *inet6* for IPv6. The term inet stand for internet, which it self is short for internetwork. This word describes the process of connecting networks together, to create an even bigger network.
		
	- fe80 stands for link-local address. It is generated immediately by Junos, to talk with other devices on that link.
		
	- Admin means has this interface been shutdown through configuration, physical interface shutdown through configuration will make all logical interface shutdown, logical interface shutdown is separated. Link means is there a live cable plugged into this interface, if the physical is down, the logical will also be down.
		
	- Ex: `ex-0/1/1` is a physical interface. Handles Physical properties includes speed of the interface/duplex. copper or fiber setting, Layer 2 MTU.
		
	- Ex: `ex-0/1/1.0` is a logical interface. Handle protocol and addressing, vlan tags, and Layer 3 MTU.
		
	- Junos Interface always have at least one logical unit on a physical interface. Physical properties always go on the physical interface, logical properties always go on the logical interface. 
	![[Pasted image 20250415155309.png]]
	- This will show every interface on the device. The output also includes other interfaces such as internal, virtual, service, loopback, tunnel, management, and more.
		
	- You can use asterisk `*` as a wildcard to search for anything that begin with that text. Ex: `xe-0/1/*`.
		![[Pasted image 20250415155722.png]]
	
- Type `show interfaces descriptions` to add text descriptions to physical interfaces and logical units.
	![[Pasted image 20250415155904.png]]

## Reading show interfaces Command Output
via Operational Mode

- Type `show interfaces`. The output is split into 2 section. 
	
	- The first section is the Physical Interface Output. This includes Interface speed and status, Layer 2 MTU, MAC Address, The last time the interface flapped, and more.
		![[Pasted image 20250415161732.png]]
	- The second section is the Logical Unit Output. This includes IPv4 & v6 address info, Layer 3 MTU, Traffic statistics-packets in and out, and more.
		![[Pasted image 20250415161751.png]]
	
- Type `show interfaces extensive`, will show you everything about an interface. This includes status, traffic stats, traffic port priority, error counters, ip settings, and more. But it is recommended for troubleshooting, logging, and monitoring.

## Filtering Output with CLI Pipe

- Ex: `show interfaces terse | ?`
	
- Using pipe `|` to filter the output of any command. This includes filter the output to only show lines containing certain text, exclude lines containing certain text, save the output to a text file, count the number of lines of output, drill down to only the exact output.
	
- Use `match` to show only lines of output that contain certain text. Ex: `show interfaces terse | match "text"`. The search is not case sensitive.
	![[Pasted image 20250415163044.png]]
	- You can even search for multiple strings of text at once. In order to do this put a pipe between each string of text and wrap the whole thing in quotes. Ex: `show interfaces terse | match "physical|flapped"`. The pipe in quotes is a logical *OR*, this means that a line matches if it contains either word.
		![[Pasted image 20250415163107.png]]
	
- Use `except` to filters out any lines that contain your text. Ex: `show interfaces terse | except "text"`.
	![[Pasted image 20250415163318.png]]![[Pasted image 20250415163344.png]]
- Use `count` to count the lines of output. Ex: `show interfaces terse | count`.
	![[Pasted image 20250415163540.png]]
- Use `find` to start the output at the first occurrence of your text. Ex: `show interfaces terse | find "text"`
	![[Pasted image 20250415163729.png]]
- In Junos you can **pipe as much as you want**.

<h2 style="color:#6290C3"><center> Reading a Junos Configuration </center></h2>
## Hierarchy View and Set View

- [Active Configuration]: The configuration that is currently running/"active" on the device. This config is stored in a database but it is viewed as a text file. 
	
- When a configuration changes was made, they are not immediately deployed and saved until a "commit" was operated.
	
- Two common ways to display Junos Configuration:
	
	- [Hierarchy View]: Displays the configuration as a series of indented tabs. Config is nicely spaced out, so individual elements get a chance to stand out.
		![[Pasted image 20250417145348.png]]
	- [Set View]: Displays the actual commands that you type to configure the device via `set`. Easy to read small configs, displays lots of info at once.
		![[Pasted image 20250417145425.png]]
	
- Type `show configuration` to view the config in hierarchy view. If you export the config to a back up server as a text file, it is exported as a hierarchy view.
	![[Pasted image 20250417160030.png]]
	- This shows the system login user account.
		![[Pasted image 20250417160157.png]]
	- This shows the interfaces via `show configuration interfaces`.
		![[Pasted image 20250417160320.png]]![[Pasted image 20250417160407.png]]
	
	
- Type `show configuration | display set` to view the config in set view.
	![[Pasted image 20250417150408.png]]
	- In addition, you can specify pieces of the configuration hierarchy via `show configuration {text}`.
		
	- To show system configuration type `show configuration system`.
		
	- This show the hostname in set system. 
		![[Pasted image 20250417152457.png]]
	- This show the management protocols in the services sub-hierarchy.
		![[Pasted image 20250417152545.png]]
	- This shows the user accounts.
		![[Pasted image 20250417152738.png]]
	- This shows the final pieces of set view configuration. Including the password for root account and log files.
		![[Pasted image 20250417152958.png]]
	- To show interface configuration type `show configuration interface`.
	
	- These four lines define the interface settings of an interface.
		![[Pasted image 20250417153503.png]]
		- In some settings the configuration might be customized such as `family inet mtu 900` (means the IPv4 traffic on this interface will have a Layer 3 MTU of 900 bytes), or `family inet6` (means that IPv6 will be configure to have link-local address only, without also requiring an explicit address.)
		
	- In some interfaces they might have a different MTU configuration. The first line affects the physical MTU. The second line affect the IPv6 MTU on the logical unit.
		![[Pasted image 20250417154701.png]]
	- To show protocols configuration type `show configuration protocols`. Note that interfaces hierarchy is for settings on the interface it self, while protocols is for protocols that you enable on an interface.
		![[Pasted image 20250417155455.png]]
	- To enable protocols in Junos. Log in via configuration mode and type `set protocols {protocol name} interface {interface name}`.
		![[Pasted image 20250417155620.png]]
	- To display configuration for an interface of your choice, type `show configuration | display set | match {interfce name}`.
	
- By reading a configuration file in set view, you're learning the exact same configuration statements you'll type to configure the device. By reading a configuration file in hierarchy view, you're learning the actual structure and layout of the configuration. It is best to learn and master both type of view.
