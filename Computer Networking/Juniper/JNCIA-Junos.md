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

<h2 style="color:#6290C3"><center> Configuring JunOS </center></h2>
## The JunOS Candidate Configuration

- Junos Configuration is done in configuration mode, the config is written into a text file and it is stored in a separate location called the Candidate Configuration.
	
- The configuration mode is a barrier that separates the actual configuration. If offers the chances to verify your syntax and fix your mistakes, the ease of scrapping changes, and deploying multiple changes at exactly the same time.
	
- Type `configure` or `edit` in Operation mode (Default) to enter configuration mode. The CLI will display `Entering configure mode` and `[edit]` box that display your current position in the hierarchy. Second, you will see that the greater-than sign `>` after the host-name has changed. It is now a `#` sign.
	
	- In this mode you will be able to Add and Delete configurations, Change and Rename things, Move and Copy things, Deactivate, ...
	
- [Changing the Hostname]: In configuration mode type `set system host-name [name]`.
	![[Pasted image 20250501192353.png]]
- [Viewing Propose Changes]: Type `show | compare`. Notice that the `+` signs means added, and the `-` means removed.
	![[Pasted image 20250501191744.png]]
- [Scrapping Proposed Changes]: Type `rollback`.
	![[Pasted image 20250501192542.png]]
## Utilizing the Commit and Rollback Commands

- [Deploying Changes]: Type `commit` or `commit and-quit` to exit to Operational Mode.
	![[Pasted image 20250501192903.png]]
- [Showing Previous commit]: Type `show system commit`.
	![[Pasted image 20250501193516.png]]
	- Junos save up to 49 previous configuration starting with 0 (latest) to 49 (oldest). Any new commit will deleted the 49th commit. 
	
- [Rolling Back to a Historical Configuration]: Type `rollback [n]`, with n being the previous config number you wanted. Typing `rollback` is the same as `rollback 0`, meaning that you are rolling back the latest config.
	![[Pasted image 20250501193803.png]]
- [Comparing Current and Old config]: Type `show configuration | comapre rollback [n]` in operational mode, with n is the previous config you wanted to compare.
	![[Pasted image 20250501194157.png]]
- Junos checks syntax as you type but it does not check variables. This checking is perform during the commit staging, if an error is found, the commit will fail.
	![[Pasted image 20250501194442.png]]
- [Validating Commit]: Type `commit check` to verifies the current changes on the candidate configuration. This command does not save the configuration or updates it. Useful in long and complicated changes.
	![[Pasted image 20250501194737.png]]
- [Configuring New Interfaces]: Type `set interfaces [interface_name] unit [number] family inet/inet6 address [IP address]`.
	![[Pasted image 20250501195203.png]]![[Pasted image 20250501195218.png]]
- Some commands in Junos is redacted due to screen display limitation or terminal sizing limitation. Just simply press `<-` key and it will show the first half of what has been type.
	
	- Or simply type `set cli screen-width 1000` to adjust the screen width. The limit is 80-1024 characters. This command is only available during the current session, it is not saved internally.
	![[Pasted image 20250501195632.png]]
- [Adding Changes]: Type `set` to add configuration to a list or overwrite existing configuration. 
	![[Pasted image 20250501200352.png]]
- When dealing with IP Addresses, typing `set` will just simply add more Addresses since an interfaces can have multiple IP addresses.
	
	- [Removing Configuration]: To avoid this problem simply remove the unwanted config via `delete`.
	![[Pasted image 20250501200841.png]]
	
- When using `delete` commands remember to specify the level of hierarchy that you wanted. Because the `delete` operates on the deepest level of hierarchy you specify.
	![[Pasted image 20250501201611.png]]
	
- [Confirming a Commit]: Type `commit confirmed [number]` to set a timer in minutes to confirmed the commit in a certain time intervals, if a commit is not confirmed, it is automatically rolled back.
	![[Pasted image 20250501202427.png]]
	- Pressing `Enter` will show the remaining time before reverting back to the latest commit.
		![[Pasted image 20250501202552.png]]
	- To confirm the commit simply type any variant of commit to cancel the rollback. Bare in mind that using commit confirmed will save the commit 2 times, so use commit check instead.
		![[Pasted image 20250501202713.png]]
	
- [Commenting a Commit]: Type `commit comment "[content]"` to add comments to your commit.
	![[Pasted image 20250501203005.png]]
- [Running Operational Commands in Configuration]: Type `run`, useful for prototyping/probing in home-labs cases, avoid in production.
	![[Pasted image 20250501203516.png]]
## Way To Lock the Candidate Configuration

- The candidate configuration is shared among user's. Many engineers can add configuration at the same time, meaning a bigger change. When another user enter the candidate configuration, the system will automatically display all user that is currently in the candidate configuration.
	
- During candidate configuration, other's commit will also affect the state of the current candidate configuration of others, this will involve unexpected changes and behavior.
	
	- [Locking the Candidate Configuration]: Type `configure exclusive` to lock the candidate configuration. This will prevent others user to commit other's incomplete configuration, they still be able to enter the configuration mode but unable to make changes.
	![[Pasted image 20250504175333.png]]
	- [Privatizing Candidate Configuration]: Type `configure private` to create a unique candidate configuration. This will enable multiple users to configure **different** hierarchy at the same time. These commit are temporary and will be discarded when exit happens.
	![[Pasted image 20250504175836.png]]![[Pasted image 20250504175955.png]]
	- [Commit at a Different Time]: Type `commit at` to deploy the commit at a chosen time. To clear the pending commit type `clear system commit`.
	![[Pasted image 20250504180154.png]]
## Deactivate and Disabling Different Pieces of the Configuration 

- [Disabling a Physical Interface]: Can be as easy as unplug the cables or turn it off and on again. Another method would be shut it down through configuration known as putting the interface into an "admin-down" state `set [content] disable`.
	![[Pasted image 20250504180537.png]]
	- Remembers that in `show interfaces terse` will show which device has been shut down through configuration (admin column) and which device is actually live and working (link column).
	![[Pasted image 20250504181415.png]]
	- To bring a status back up type `delete [content] disable`.
	![[Pasted image 20250504181622.png]]
	- You can also disable individual logical unit.
	![[Pasted image 20250504181913.png]]
	- Reminder that the **Admin** output tells you about the administrative state, **Link** tells about the physical interface status.
	
- You can disable many other things such as protocol.
	
- [Deactivating a Hierarchy]: Type `deactivate [content]` to deactivate any piece of hierarchy. It just like commenting out a piece of configuration without affecting the rest. Even though it is still technically up, but its logical unit and content have all disappeared. In some platforms, Junos might inserts a dummy unit on empty interfaces.
	![[Pasted image 20250504182823.png]]![[Pasted image 20250504182835.png]]
- [Activating a Hierarchy]: Type `activate [content]` to reactivate/activate a configuration.
	![[Pasted image 20250504183113.png]]
- Reminder: Use `rollback` if the configuration goes out of hand.
	![[Pasted image 20250504183203.png]]
## Deploying Configuration within a Hierarchy

- [Using Hierarchy to Deploy Shorter Commands]: Type `edit [hierarchy-level]` to edit at a deeper hierarchy, this will short up commands.
	![[Pasted image 20250504193046.png]]
- [Moving Back Up the Hierarchy]: Type `up [number]` to move back up. Or just `top`.
	![[Pasted image 20250504193240.png]]
- Keep in mind that `show | compare` will only show the changes in that certain hierarchy level.
	![[Pasted image 20250504193422.png]]
	- `commit` is unaffected in terms of hierarchy's depth. But in `configure private` mode, `commit` is only allowed at the top of the hierarchy level.
	![[Pasted image 20250504193619.png]]
## Using rename and replace Commands to Edit the Configuration

- [rename]: Changes one occurrence of a user-defined element in the configuration. 
	![[Pasted image 20250504194301.png]]
- [replace pattern]: Changes all mentions of a user-defined element, anywhere in the configuration. But it is hierarchy-sensitive.
	![[Pasted image 20250504194340.png]]
	- It is used to change the names of firewall filters and policies that apply to routing protocols. It is also used to search for an incorrect IP and subnet mask and replace it with the correct IP and subnet mask.
	
- In large routers that host services for multiple customers, `rename` is the preferred method in case of IP overlap used by customers.
## Keyboard Shortcuts

- Useful Keyboard short cut.
	![[Pasted image 20250504195803.png]]
	- `ctrl-w` delete a whole word.
		
	- `ctrl-a` move the cursor to the start of the command line.
		
	- `ctrl-e` move the cursor to the end of the command line.
		
	- `ctrl-k` delete everything from the cursor to the end of the command line.
	![[Pasted image 20250504200157.png]]

<h2 style="color:#6290C3"><center> Routing Tables, Route Preference, and Longest Prefix Matches </center></h2>
## Directly Connected, Static, and Dynamics Routes

- Routes define how to get to a destination. As such they are the combination of a subnet, and knowledge of how to get to that subnet. Routes contains information for what is known as the "next hop" in the path, destination subnet, outgoing interface, IP address of the next-hop router.
	
- Routers does not magically learn all subnets in the network, even if they are directly connected. These are the methods to create a route:
	
	- Configure subnet on a local interface, If the interface is up this creates something called a directly connected route. The routers has learned about the existence of a subnet because it has interface that is directly connected to that subnet.
		
	- Configure a route to a remote destination. Configured routes that point to a next-hop router are called static routes.
		
	- Enabling routing protocol. These protocols automatically learn and advertise subnets in the network, The routes that these protocols learn are known as dynamic routes. These protocols are rarely enabled by default - you need to choose a protocol and then configure it yourself.
	
- [Directly Connected Routes]: Are routes to subnets that are configured on local interfaces that are up and working. If an interface on a router is up, and the interface is given an IP address and a subnet mask, then the router clearly knows that this entire subnet can be found out of that interface. As long as these interfaces are up, your router learns that these subnets exist out of these interfaces. If the interface goes down, then these routes disappear until the interface comes back up.
	
- [Static Routes]: Are routes to remote subnets that were added through configuration. You have to manually telling a router to get to a remote subnet, in other word forward all traffic destined from a subnet to another subnet. 
	
	- Static routes are simple to deploy, easy to understand. They're ideal in small networks.
	
- [Host]: Are just any device that can be given an IP address.
	
- [Dynamic Routes]: Enabling your router to learn subnets automatically. By doing this your router will advertise its own local subnets, and it will re-advertise remote subnets that they've learned about from other routers.
	
	- They adapt dynamically to topology changes.
		
	- There are many routing protocols, each with its own different features and advantages, and trade-offs. 
		
	- Some protocols are open standard, meaning anyone can use them. 
		
	- Some are proprietary, specifically on particular devices. 
		
	- Some are designed for specialist for specific situations. 
		
	- Some protocols are quick to react to network changes, but have limited scope in what they can learn. These protocols can learn a lot of information about one single network, but they cannot scale to learn very single subnet on the entire internet.
		
	- Other protocols are much slower to react to changes, but this is a good thing because it gives them the ability to learn multiple routes to every single subnet on the public internet.
		
	- Four well known protocols: OSPF, IS-IS, BGP, RIP.
## Route Preference

- When a router learns how to get to a subnet, engineers call the subnet a "prefix". This is a more precise word to describe a block of IPs, specifically in the context of routing.
	
- Take `192.168.10.0/24`. 
	
	- Routers only care about the "network part" of this subnet, in other words, the section of the address that actually refers to the subnet itself, which is `192.168.10`.
		
	- The `.0` is the "host identifiers" which can be anything from `.0` to `.255`, but the first and the last are preserved. 
		
	- The `/24` is the prefix length which is used to defines the number of bits used by the prefix. The IPv4 are 32 bits long, so a prefix of `/24` means that the first are used for the prefix, which is `192.168.10`, and the rest for the host identifier.
	 
- `subnet` are used most often when talking about the actual allocation of block of IPs to a part of the network. `prefix` in regards to routing information. Most of the time, they are interchangeably and loosely used by engineers.
	
- [Routing Table]: Junos routing tables store all known prefixes, learned from all sources. There are separate tables for IPv4, IPv6, and many advanced features.
	![[Pasted image 20250513193629.png]]
- Once the routing table has received all information from all sources, Junos then analyzes this information, and choose the one single best way  to get to a particular destination. This best routes, the winner out of all the possibilities , is known as the "active route".
	
	- [Concept of Route Preferences]: By default, Junos assigns a unique number to every method of learning a route. This includes all routing protocols, as well as static routes, and directly connected routes. If a router learns exactly the same prefix from two different protocols, then the route preference number is used as a tie-breaker to decide which route is best. In other words, this number indicates how believable the protocol is. The numerically lower the preference, the more believable that protocol is.
	![[Pasted image 20250513194629.png]]
	- If the Direct route goes down, other routes will be used for forwarding.
		
	- It is important to use **numerically lowest route preference**.
## Longest Prefix Match Lookup

- You can divide the subnet into even smaller subnets.
	![[Pasted image 20250513195141.png]]
- An important rule of routing is that the **most specific route always win**. Take this case as an example.
	![[Pasted image 20250513195619.png]]
	- As `/25` is more specific than `/24`, `/25` is chosen for forwarding if the host identifiers lies within .0 to .127. If it exceeds .127, `/24` is chosen for forwarding since it is out of scope for `/25`.
		
	- This process is called **longest prefix match lookup** because `/25` in binary is longer than `/24`.
	![[Pasted image 20250513195916.png]]
	
- [Forwarding Table]: Responsible for looking up the destination IP of incoming packets, and deciding how to forward it. The forwarding table is create by importing all of the active routes in the routing table and ports it onto the forwarding table. Junos utilize the routing table and then decide the best path and give it to the forwarding table, where transit traffic is actually processed.
## The inet.0 and inet.6 Routing Tables

- The table `inet.0` contains all known IPv4 prefixes, learned from all protocols, and the table `inet6.0` performs the same job for IPv6 prefixes. Tables names like `inet.1`, `inet.2`, `inet.3`, and so on are used in more advanced networks such as networks that use multicast or MPLS (multi-protocol label switching).
	
- Type `show route`, which will first show you the `inet.0` table then `inet6.0` table. Specifying `show route table [content]` will show the specified table only. Typing `show route [ip address]` will also work.
	![[Pasted image 20250513201552.png]]![[Pasted image 20250513201749.png]]
	- You can also see the length of time that route has been in the table. This can be helpful for troubleshooting IP problems in your network. If a route has only been there for a very short amount of time, then perhaps there is a chance that the route is appearing and disappearing very rapidly. 
		
	- The `*` (asterisk) indicate active routes, and the last active routes or the most recently active route. The `>` involved in indicating which route is the active route, in addition to the asterisk. The `>` is also used to indicate the best path.
		
	- Make sure to use the `exact` keyword at the end of the command if you only want to see the exact prefix you're searching for.
		
	- Note that `/32` is listed as a Local route. This means that the IP is indeed configured on the actual interface itself. The address is local to the device. This sometime protect you against an incorrect static route.
	
- Type `show route table [content] protocol direct` to see all directly connected routes. 
	![[Pasted image 20250513203035.png]]
- The process for viewing and reading the `inet6.0` is identical to `inet.0`. 
	![[Pasted image 20250513203358.png]]
	- Noted that `/64` give the first half for network portion, second half for host identifiers. `/128` refers to a specific host address, since IPv6 is 128 bits long.

<h2 style="color:#6290C3"><center> Static Routes </center></h2>
## Advantages and Trade-offs

- Advantages: Simple to create, easy to understand, useful in small networks, ideal if there is only one path to the destination prefix.
	
- Important trade-offs:
	
	- Statics routes cannot react intelligently to changes in the topology.
		
	- If a new subnet is added, you must manually update each router in the network with a new static route pointing to that subnet.
		
	- Routers do not communicate to verify that their static routing knowledge is accurate. If you forgot to configure a router, then it will drop the packet sent by another router. To be more precise they send a ICMP, which is purely informational, for routers to communicate. In situation where the router receives packets to a destination it does not know, it will send a ICMP Destination Unreachable to the sender and drop the packet. 
		
	- These are consequences to use static routes correctly, not to avoid it.
	
- Static Routes use case:
	
	- Very Small Networks
		
	- Low-Powered Routers.
		
	- Situations where there is only one path to a destination.
## Configuration and Verification

- [ping]: Type `ping` to test connectivity at the end of the link. Pings are very small packets that gives you the visibility of whether end-to-end connectivity is successful.
	
	- Pings runs forever until `ctrl + c` is pressed.
		
	- Use `count` to limit the ping result.
	
- By default, the source address of a ping is taken from the outgoing interface. To override use the `source` options, which lets you specify a directly connected interface IP address to use as the source of the ping. This is useful for testing configuration.
	![[Pasted image 20250513221147.png]]
- [IPv4 Routing Syntax]: Type `set routing-options static route [ip address] next-hop [ip address]`. This will create a static routes (next-hop) to another routers that contains the IP address.
	![[Pasted image 20250513222041.png]]
- [RIB]: Routing Information Base. A formal term for routing table.
	
- [FIB]: Forwarding Information Base. A formal term for forwarding table.
	
- [IPv6 Routing Syntax]: Type `set routing-options rib inet6.0 static route [ip address] next-hop [ip address]`.
	![[Pasted image 20250513222631.png]]
## Default Routes

- Two prefixes that contains every single IP address possible for IPv4 and IPv6:
	![[Pasted image 20250513223039.png]]
	- `0.0.0.0` is the first theoretical IPv4 address. The `/0` subnet means "every single IP address". If there isn't a more specific entry in the routing table, then a packet's destination address will math this entry.
		
	- When you see 2 colons. It means that you expand the address to however many zeroes are required. In this case it is 32 zeroes in a row.
		
	- This special kind of prefix is used to create a default route.
	
- Configuring Default Static Routes.
	![[Pasted image 20250513223525.png]]
- In real world, some devices do not respond to `ping` by default, and some devices are explicitly configured to ignore pings. If your pings fail, this does not necessarily mean there is a routing or IP problem.
	
	- A ping failure could be an indication of incorrectly configured Network Address Translation (NAT, the process of converting private IPs to public, and vice versa), or that the destination does not reply to ping traffic, or any number of problems.
	
- Type `show route protocol static` to display all static routes on a device.
	![[Pasted image 20250513224044.png]]

<h2 style="color:#6290C3"><center> Dynamic Router </center></h2>
##  Routing Protocols, and The Problem They Solve

- The advantages:
	
	- They automatically find the best path to all destinations.
		
	- They dynamically react to changes in the network.
		
	- They know the routing info of their next-hop router.
		
	- Routing protocols also bring integrity to the routing knowledge in a network. Before routers exchange prefixes, they first agree on how the protocols works, this includes timers, packet size, and other important configurations. If the routers agree, they "form an adjacency", also known as "becoming neighbors".
	
- The trade-offs:
	
	- First, routing protocols can be more complicated to learn. Having said that, the basics of most protocols are still very easy. There is additional knowledge you need to learn when compared to static routes but this extra knowledge is trivial compared to the advantages that you get from a routing protocol, such as the ability for your router to automatically find alternative paths in response to changes in the network.
		
	- Second, routing protocols use up more of your router's CPU and memory resources, when compared to static routes.
		
	- Third, it may not be necessary to run a routing protocol in a very small network, or if you only have one path to a remote subnet.
## Interior and Exterior Gateway Protocols

- There are protocols for different situations, with different advantages.
	
- [IGP (Interior Gateway Protocols)]: Are designed for use internally, within one single organization's network. It is use for your routers to learn everything about the subnets and the best paths within your own network. IGPs are often said to learn your "infrastructure prefixes", this is opposed to the prefixes in the global internet;s routing table.
	
	- These protocols react very fast to network changes. They can also discover detailed information about the paths available in the network. However, the speed of these IGPs comes at a cost-these protocols are not designed to advertise or learn the entire internet's routing information.
		
	- Two IGP categories: Distance Vector Protocols, Link-State Protocols.
	
- [Distance Vector Protocols]: Very basic. They only care about how many hops it takes to get to a prefix. The best path is the shortest number of hops away regardless of link speed. For this reason they are mostly considered legacy in the modern era.
	
	- The word "vector" comes from graph theory.
	
	
- [Link-State Protocols]: Offer more features and intelligence. These protocols learn the topology of the network, including the speed of the links. This gives them the ability to find the best path based on this network visibility. They care about the number of hops, but also how believable those hops are. Given the choice between a path with fast links and more hops, or slow links and less hops, a link-state protocol is very likely to choose the path that offers more bandwidth.
	
- [RIP (Routing Information Protocols)]: First routing protocols.
## Link-State Protocols

- Each routers generates and advertises data about its place in the network such as the prefixes connected to that router, and the connections it has to other routes. They can be refer as "jigsaw pieces", and if all "jigsaw pieces" do the same thing, the results is that each router can put the pieces together and form the full topology back together.
	
- "Jigsaw Pieces" contains unit of data that advertise various pieces of information about that router's place in the network. It includes: a unique router ID number, the prefixes connected to the router, the router's links to other routers, and the metrics on the links. The metric is a representation of how good and believable the link is.
	
- The metric number on each link is used to decide the best path to any destination. The lower the metric the better  and more believable the link. In other words, the best path has the lowest total end-to-end metric.
	
	- It is advise and important to use metric in representation of link speed. The lower the metric the higher the link speed, because of unit differences in link speed (bps).
		
	- You should configure your devices to override the default metric allocations, so that the metric is calculated based on the extremely fast link speeds of the modern era.
	
- These metaphorical "jigsaw puzzle" are flooded throughout the network. At the end of the process, each router has its own copy of all the information that has been generated. They then put them together to build the full topology, this results that they all have the same view of the network since they do it in exactly the same way.
	
	- This makes each router has the same map of the network in its memory. This is called **LSDB**, Link-State Database.
		
	- Each router can calculate the shortest path to get to any particular prefix using this network map. This path is guaranteed to be loop-free, because each router is able to see where loops might occur. This process is suitably called Shortest-Path-First Algorithm, SFP for short.
	
- Two link-state protocols:
	
	- [OSPF( Open Shortest Path First)]: "Open" means it's open standard. Popular in enterprises, service providers, and data centers.
		
	- [IS-IS (Intermediate System to Intermediate System)]: An older term for router to router. Popular in service providers and data centers.
		
	- Both protocols use "jigsaw pieces" to build a full view of the topology, assign metrics to links so the SPF algorithm can calculate loop-free paths, can react quickly to topology changes (despite being slow on default, config is needed), have ways of dividing large networks into smaller topologies (useful for small, less powerful router).
		
	- OSPF calls "jigsaw pieces" LSAs (Link-State Advertisements), IS-IS calls them LSPs (Link-State PDUs (Protocol data unit/chunk of data)).
## Configuring and Verifying a Basic IPv4 OSPF Deployment

- Deleting Static Routes
	![[Pasted image 20250515204506.png]]
	- The next-hop is hierarchically so by deleting the prefix, you also deletes the next-hop.
	
- When configuring OSPF you need to put them into an area. OSPF area enables you to divide a topology into smaller sections. This is helpful if have a lower-powered routers, because it means that the router does not need to learn the entire topology. Instead they just learn a small portion of it.
	
	- However, multiple areas is not needed. One single OSPF Area 0 is enough for hundreds of routers.
		
	- IS-IS call this concept as "levels". IS-IS Equivalent is Level 2.
	
- For IPv4 type `set protocols ospf area 0 [content]`.
	![[Pasted image 20250515205431.png]]
	- Area 0 is converted to Area 0.0.0.0. Area numbers are 32 bits just like IP address but they are not IP address.
		
	- This mostly lies under protocols hierarchy. The interface is under Area 0, which is under OSPF. And OSPF is under protocols.
	
- When you commit your OSPF configuration. The devices send a `OSPF HELLO`, this is the name given to a periodic series of small packets that the router regularly transmits to discoverer other OSPF speakers on the link. By default, these hello message are sent every 10 seconds. 
	![[Pasted image 20250515210932.png]]
	- In addition to discovering other potential OSPF neighbors, it is also used to maintain existing neighbors.
		
	- The mechanism sent packets to the address `224.0.0.5`, which is a special reserved address called the "All OSPF Routers" multicast address (one to many).
		
	- These hello messages contain various pieces of information that both routers must agree on before they can exchange routing information.
	![[Pasted image 20250515210943.png]]
	
- Type `show ospf neighboor` to see OSPF neighbor. `Full` status mean the process is completed.
	![[Pasted image 20250515211133.png]]
	- The `Dead` column is a countdown for the Dead Interval Timer, when it reaches 0, your router assumes that the neighbor has disappeared and that the OSPF neighbor should be torn down. 
		
	- The `ID` is a unique number that identifies each OSPF device in the topology, `Pri` is short for priority which is a number used on Ethernet Interfaces that helps to improve OSPF efficiency when there are more than two routers connected to the same subnet, via a switch.
	
- Verifying OSPF type `show route protocol ospf`.
	![[Pasted image 20250515212052.png]]
	- OSPF has priority of 10.
	
- Remember that routing protocols do not just automatically advertise every single prefix in the routing table. OSPF only advertise what the user tells it to advertise.
	
	- Do not send OSPF through LAN interface.
	
- Use `passive` keyword to enable OSPF without hello messages.
	![[Pasted image 20250515212827.png]]
## Configuring and Verifying a Basic IPv6 OSPF Deployment

- IS-IS can advertise both IPv4 and IPv6. OSPFv2 Advertise IPv4 only via `ospf`. OSPFv3 advertise both or separated via `ospf3`.
	
	- OSPFv2 and OSPFv3 is identical.
	
- Type `set protocols ospf3 area 0 [content]` to configure OSPFv3.
	![[Pasted image 20250515213451.png]]
- Type `show ospf3 neighbor` to see neighbor.
	![[Pasted image 20250515213557.png]]
	- Note that device configure for OSPFv2 will not be recognized on OSPFv3.
	
- Type `show route protocols ospf3` to verify.
	![[Pasted image 20250515213735.png]]
- Additional Changes that is advantageous:
	![[Pasted image 20250515214003.png]]

<h2 style="color:#6290C3"><center> Junos OS Switches </center></h2>
## Introduction

- The Switches usually has 3 PIC, PIC 0 and PIC 2 are in the front, PIC 3 are in the back and mostly used for VC (Virtual Chassis).
	
- [VC (Virtual Chassis)]: Gives you the ability to configure two or more switch as if they were one logical switch, with one management IP and one configuration. 
	
- The T in "EX4300-24T", means Copper Twisted Pair Ports.
## Configuring and Verifying VLANs

- All Modern Jun OS switches are Layer 3, which means that they have the capabilities to forward traffic on both Layer 2 (Ethernet) and Layer 3 (IP). 
	
- [Management Interface]: An interface where you can give it an IP address, and you can send management traffic to it, such as SSH or Telnet. 
	
	- Some interface have this IP address, but the interface is not a part of the network. This is called **out-of-band** which means that it does not take part in regular transit network.
	
- Type `show vlans` to view all existing VLANs.
	
	- [VLAN Name]: A column that show VLAN names. Default is a default VLAN name that will always exists.
		
	- [Tag]: Unique number. That identifies the VLAN
		
	- Asterisk next to the port, means that it is up.
		
	- The default VLAN creates one large broadcast domain. If one device in the Guest VLAN sends a broadcast, it will send out to other ports that are suppose to be in the VLAN. 
	
- Type `show configuration vlans` to show all VLAN. Each VLAN is associated with a name and a tag number.
	![[Pasted image 20250520092935.png]]
- Type `set vlan {vlan name} vlan-id {number}` to configure a VLAN.
	![[Pasted image 20250520093713.png]]
## Configuring Access Port and Verifying MAC Tables

- [Access Port]: When a physical ports belong to only one VLAN. By default all port on a switch are access port.
	![[Pasted image 20250520094628.png]]![[Pasted image 20250520094712.png]]
- Type `set interface {interface name} unit {number} family ethernet-switching vlan members {vlan name}` to add an interface to a VLAN.
	![[Pasted image 20250520094951.png]]
- Type `show ethernet-switching table` to view all MACs on all ports, on all VLANs.
	![[Pasted image 20250520095455.png]]![[Pasted image 20250520095229.png]]
	- Noted that "D" in the MAC Flags column stands for dynamic, which means that all MAC address are learned by listening to incoming traffic.
## Trunk Ports

- [Trunk Ports]: Belongs to multiple VLANs at once, and traffic in and out of the trunk port is tagged with relevant VLAN number. The tags map incoming frames to the relevant VLAN-and therefore, the relevant broadcast domain.
	
	- Access port have no need to tag traffic with a VLAN number, because the outgoing traffic only belong to one VLAN. By contrast, VLAN tags are the magic that makes trunk interfaces works.
	
- Type `edit interface {interface name}` to edit a deeper of the hierarchy that is only related to that interface. Then type `set unit {number} family ethernet-switching interface-mode trunk` to turn the interface to a trunk port.
	![[Pasted image 20250520104033.png]]
	- Type `set unit {number} family ethernet-switching vlan members {vlan name}` to add VLAN to the trunk port.
	![[Pasted image 20250520104156.png]]
	- Another way to do this is to utilized `[ list of vlan names separate by space]` to add multiple VLAN to a trunk port. Or alternatively type `all` but avoid this since it could possible configure every single existing VLAN, this is catastrophic if a broadcast storm appears and affect every single trunk link.
	![[Pasted image 20250520104817.png]]
- Type `show configuration interfaces {interface name}` to verify the trunk port.
	![[Pasted image 20250520105020.png]]![[Pasted image 20250520105158.png]]
	- Noted that it doesn't matter if you add the VLAN members manually or in terms of a group, they will always appear inside the `[]` brackets.
	
- When it comes to Link Layer Discovery Protocol. They are enabled by default on all interfaces. Switches comes with LLDP by default because there are some hosts that rely on LLDP information to automatically configure their network settings in the most optimal way.
	![[Pasted image 20250520105440.png]]
## Configuring Multiple Logical Unit on IP Interfaces

- Verifying The Router LAN configuration.
	![[Pasted image 20250520110010.png]]
- To add multiple LAN configuration onto a single interface, we utilize multiple Logical Unit to separate those LAN configuration. Then you bind each Logical Unit with the VLAN tag number, and place IPs on each unit.
	![[Pasted image 20250520111239.png]]
- To configure a single interface with multiple unit, you first need to delete existing interfaces that you wanted to add to that unit by simple `delete` or `deactive` as an alternative.
	![[Pasted image 20250520111445.png]]
- Type `set interfaces {interface name} vlan-tagging` this enables the interface to process VLAN tags. To be more precise, this command strictly enforces the use of frames that have only one VLAN tag. 
	![[Pasted image 20250520113132.png]]
	- There are also two other options. First is `stacked-vlan-tagging`, which strictly enforces the use of two VLAN tags on a frame. Second is `flexible-vlan-tagging`, which gives an interface the ability to accept either one or two VLAN tags on a frame.
	
- When using `show configuration | display set | match {interface name}[]` you can use `[]` to list the number of interfaces you want.
	![[Pasted image 20250520135101.png]]
- [STP (Spanning Tree Protocol)]: Used to avoid catastrophic problems in your network caused by switching loops.
	
- [Port Security and Storm Control]: It shutdown switch port if certain conditions are met.
	
- [Link Aggregation Group (LAG)]: Increase bandwidth by bundling multiple cables into one logical link.
## Juniper EX and QFX Switches

- [EX Series Switches]: High performance devices that can sit at the access layer and at the aggregation/core layer. These switches are "cloud ready", meaning they can be utilize by Mist AI.
	![[Pasted image 20250520141655.png]]![[Pasted image 20250520141702.png]]
	- EVPN Ethernet Virtual Private Network, VXLAN Virtual Extensible LAN.
	
- [QFX Series Switches]: Commonly used as **leaf devices**, switches that offer connectivity to servers. They can also be used as **spine switches**, devices that connect leaf switches together.
	
- [Mist]: A management platform. It offers complete visibility, control, and automation. It learns your network using AI (Artificial Intelligence) and ML (Machine Learning). And finally, it monitors all traffics, and identifies problems and deploy fixes before you even notice.
	
	- It can correlate seemingly unconnected events. Mist AI can learn when Wifi drivers are causing poor signal strength, it can identify when a laptop software update produces connectivity problems, it can bounce problematic interfaces, and it can keep track of configuration inconsistencies.
	
- [Marvis]: A natural language interface that is powered by AI.

<h2 style="color:#6290C3"><center> Jun OS Device Configuration </center></h2>
## Out-of-Band Management Interfaces

- [In-Band-Management Traffic]: This means that your SSH traffic shares the same network as your data traffic. This is fine when your network is healthy. Indeed, the majority of SSH sessions are usually in-band.
	
- [Out-of-Band Management Traffic (OOB)]: This interface is designed to provide the user remote access to a device, even when network connectivity is down. This interface has it own subnet, which is totally separate from your transit network. 
	![[Pasted image 20250520200524.png]]
	- One way to make a use of out this interface is to connect it to a dedicated management network,. This network could also host monitoring servers or backup servers. Your entire management network is protected from any issues on the data network, which gives you a greater chance of accessing the devices you need to restore access in times of crisis.
		
	- Junos does not allow traffic to travel between the management interface and any network interfaces. The out-of-band network cannot communicate with the in-band network.
	![[Pasted image 20250520200713.png]]
- The name and the physical presentation can vary between devices. It is usually presented as a copper port.
	`EX Series: me0, vme`
	`SRX Series: fxp0, ge-0/0/0`
	
- No special configuration is needed to configure the management interface-you configure it just like any other interface.
	![[Pasted image 20250520201241.png]]
	- To test the interface connect a computer to it and `ssh` into it.
	![[Pasted image 20250520201334.png]]![[Pasted image 20250520201348.png]]
- Real world use of the Management Interface:
	
	- First, you can configure the interface and leave it unplugged, and connect a computer directly into it whenever you need it.
		
	- Second, you could connect the management interface into a separate, dedicated internet connection. This solution is useful when you can only access your device remotely. This options comes with an additional expense for the cost of the WAN link, and potentially with the cost of an additional router to terminate the WAN connection, and potentially a firewall to offer additional security-but depending on how crucial this device is, the cost may be worth it.
		
	- Third, you could connect the management interface to a separate management LAN. This is a good option if you have a lot of devices that have dedicated management interfaces. It is also goof choice if you have multiple devices that deal with management in some way.
## Accurate Time on a Jun OS Device

- Internal logs and configuration changes all have timestamps-and this information is crucial to troubleshooting process. By contrast, when the device is working off of an incorrect time, this incorrect time will be stored with every commit on the box. This would make it much more difficult to establish if a particular commit caused the network fault-especially if you are troubleshooting across multiple devices, each with a slightly different time.
	
- The "time" on a device is characterized by three elements: the date, the time, and the time zone. There are two ways to set this information:
	
	- First, is to configure the time manually, this will create a permanent time. The advantages is that it is easy. The disadvantages is that time will slowly become out-of-sync over time, it is also difficult to set precisely the same time on multiple devices simultaneously.
		
	- Second, acquire time through NTP (Network Time Protocol). This method is always precisely accurate, across all of your devices. But you need a reliable NTP servers, whether it be on your local LAN or our on the Internet.
	
- Type `set system time-zone {time zone}` and `set date {year/month/day/hour/minute}` to set timezone and time.
	![[Pasted image 20250520205124.png]]
- Type `show system uptime` to show current time.
	![[Pasted image 20250520205237.png]]
- Type `set system ntp server {server ip  address}` to configure the NTP server on your device. When you commit the work, the Router becomes an NTP client. It synchronizes with the NTP server to find the correct time. This server is on the Internet, but it could also be on tour local LAN.
	![[Pasted image 20250520205445.png]]
- Type `show system uptime` and `show ntp associations` to verify the configured time.
	![[Pasted image 20250520205547.png]]![[Pasted image 20250520205720.png]]
	- The `st` column, which is short for stratum. This is the number of NTP servers you are away from an authoritative atomic clock. The lower the better.
## DNS Solution Process

- [DNS]: Domain Name System, a distributed database that translate domain names to IP addresses and vice versa.
	
	- It is distributed because there are thousands of name servers all around the internet that collectively host all of this information. Name servers are responsible for hosting the authoritative answer to a particular DNS request.
	
- [FQDN (Fully Qualified Domain Name)]: Consist of a sub domain `www`, domain name `juniper.net`.
	
- The device will end the DNS query to something called a DNS resolver, this server is tasked with receiving queries from multiple devices, finding answer from name servers, and also caching those answers for a short time so that the DNS requests from other devices can be answered in the most optimal way.
	
- Type `set system name-server {dns server address}` to configure DNS server. It is best to have at least 2 DNS servers.
	![[Pasted image 20250520210829.png]]
	- Use `ping` to test the responsiveness.
	![[Pasted image 20250520210844.png]]
## Creating User Account

- Showing user account.
	![[Pasted image 20250520212543.png]]
- Ways to set a password in the authentication section:
	![[Pasted image 20250520213102.png]]
	- First, use `authentication plain-text-password`. You use this option when you want to type the password in plain text directly into the CLI. Noted that the CLI will not show your password when you type it in. When you have confirmed the password, Junos encrypts this password for you. You type `plain-text-password` but Junos changes it into `encrypted-password` in the configuration file.
		
	- Second, use `encrypted-password` directly. You use this when you already got a user configured on one device, and you want to quickly add them to another device by copying and pasting the configuration.
	
- [Hash]: The final encrypted string of text. This is the result of an encryption algorithm. A hash is a kind of way mathematical function cannot reverse. Junos uses SHA-512, Secure Hash Algorithm, refers to the length of the hash measured in bits. The `$6$` indicates SHA-512.
	![[Pasted image 20250520213430.png]]
- Type `set system login user employee authentication {password type}` to change existing password on a user. It also require a confirmation by typing the same password again.
	![[Pasted image 20250520213548.png]]
## Setting User Permissions

- [Login Classes]: Collection of permissions that you assign to user, to permit or restrict access to any part of your device.
	![[Pasted image 20250520214631.png]]
	- You can configure a user with only one class. Custom class is allowed.
	
- Every single command and configuration statement is placed into a category, these are used to create custom classes. There are called "permissions flags". 
	![[Pasted image 20250520214918.png]]
- A user may have the correct username and password, but they might not have permission to access every single device. If you want to access and modify anything on a device, configure your user with `super-user` class. If you don't want a user to do anything just configured them with `unauthorized` class, this is useful when it comes to members that are new to the network that are taking assessment.
	![[Pasted image 20250520215233.png]]
- `operator` class is designed for basic troubleshooting.
	![[Pasted image 20250520215323.png]]
- `read-only` class is only for viewing the status of the network via `show`.
	
- Type `set system login user {username} class {class options} authentication {password type}` to configure a user privileges. 
	![[Pasted image 20250520215542.png]]
## J-Web Graphical Interface

- A graphical interface that offers management and monitoring. It has less feature than the CLi, but it is more simplistic and easier to use.
	![[Pasted image 20250520220401.png]]
- J-Web Menu Bar.
	![[Pasted image 20250520220459.png]]
- SRX Series comes with J-Web, other devices need to enable J-Web through configuration.
	
- [HTTP and HTTPS]: HTTP Hypertext Transfer Protocol, the name of the protocol that your web browser uses to request and download Web pages-in other word, the protocol that enables two-way communication between you and a web server. The S in HTTPS stand for secure, its the same but with additional security layers.
	![[Pasted image 20250520220833.png]]
- Type `set system services web-management {http/https}` to configure J-Web on a device. A `system-generated-certificate` is needed when configuring for HTTPS.
	![[Pasted image 20250520221052.png]]
	- HTTP is using the standard TCP port of 80 for unencrypted web traffic, HTTPS using the standard TCP port of 443 which requires a digital certificates which can be obtain through a third party authority or self-signed.
	
- To verify type `https://` or `https://` along with the IP address of the interface you are using to access J-Web.

<h2 style="color:#6290C3"><center> Setting Up Brnad New Junos Device </center></h2>
## Default Junos Configuration

- Each platform comes with different default settings from the factory. You must log in, read the default config, and choose that to change
	
	- Beware that firewalls will have additional security and configurations compared to routers. 
	
- Some devices come pre-configured with protocols that make sens only on that platform.
	
	- Switches usually comes with RSTP (Rapid Spanning Tree Protocol) preconfig to prevent loops on Layer 2.
## Using the Console Port, and Implementing the Mandatory Configuration on Jun OS Devices

- Connect to the CLI using the console port, using a special cable called console cable, and sometimes called a serial cable.
	![[Pasted image 20250522165433.png]]
	- The console port does not use IP and nor does it use Ethernet. When you connect your computer to the console port, you can think of this as a direct connection into the Routing Engine-directly into the brains of the device directly onto the CLI.
		
	- The console port uses RS-232, stands for **Recommended Standard**. 
	
- There are few ways to open up serial connection from your computer to the console port of a device. 
	
	- Terminal Apps, some terminal apps have a button that you can click to access your computer's serial port such as PuTTY.
		
	- [Baud Rate]: Unit for symbol rate of modulation rate in symbols per second for serial communication. 9600 Baud rate is the standard for RS-232.
		
	- For other connectors, like DB9, USB, additional software is required.
	
- After setting up the connection, press Enter/Return to enter the CLI environment.
	![[Pasted image 20250522170537.png]]
	- When the device is new, and has a factory-default configuration, you CLI login prompt will contain the word **Amnesiac**, meaning it does not have a host name.
		
	- To log in for the first time on a brand new device, simply type `root`. To set a password, simply type `set system root-authentication` in configuration mode.
	
- Jun OS is based on FreeBSD.
	
	- Noted that when you log in Jun OS via root, it will log into the UNIX Shell. Type `cli` will log into JunOS CLI.
		
	- Type `exit` will log out of Junos CLI and brought you back to UNIX Shell. Type it again will log out completely.
	
- Root password must be establish before configuring the system.
## Recommended Initial System Settings

- Some useful settings for new device.
	![[Pasted image 20250522171352.png]]
- It is recommended to set up a message banner when someone is attempting to log in.
	
	- Type `set system login message "{content}"` to show a banner before the user logs in.
		
	- Type `set system login announcement "{content}"` to show a banner after login.
		
	- Text/string formatting is available.
	
- Type `load factory-default` to load it into the candidate configuration and restore the "configuration" back to factory default, this does not restore it to factory settings as files and keys remain untouched.
	![[Pasted image 20250522192113.png]]
	- Make sure to `delete system commit factory-settings` to fully restore to factory configuration.
	![[Pasted image 20250522192459.png]]
- [Rescue Configuration]: A configuration where you can roll back in-case something catastrophic happens. This rescue configurations tends to be basic/safe enough to handle most of the user cases. Type `request system configuration rescue save` to take a snap shot to create a rescue config, `rollback rescue` to roll back to rescue commit, `request system configuration rescue delete` to delete the rescue rollback.
	![[Pasted image 20250522192857.png]]
- Two ways to reboot or shutdown via the CLI:
	
	- Type `request system reboot` to reboot the device. This process can vary between devices in total length of time. If you're connected via SSH, you will need to create a new SSH connection after the device completes the reboot. If you are connected via the console port, you will eventually be greeted with a new login prompt.
	![[Pasted image 20250522193158.png]]
	- Type `request system halt` to gracefully shutdown Junos OS, so that you can then safely power-off the device at its source of electricity or by pressing the power-off button on the device. You will receive a message on the CLI telling you when the shutdown is complete, and the it is safe to power off the device.
		
		- If you have a modular chassis with two routing engine, use the command `request system halt both-routing-engines`. This will shut the primary RE then the backup RE.
		
	- Another options is to `request system power-off`, which you can do remotely if the device have a physical button. If not it will remain the same status as `request system halt` and remain powered.
## Zero Touch Provisioning

- [ZTP (Zero Touch Provisioning)]: A way for a new Junos device to automatically find a server on a network that can tell it how to get a configuration file, and whether there is a new version of Junos that it can upgrade to. If there is, then the ZTP server will reply with the requested info.
	
	- This configuration file can be a regular configuration, or it can be a script that gives you much more flexibility in terms of device specific configuration pieces. This can happen at the moment the device is physically connected to the network, whether it be via the management port or via a network port. Some Junos devices are configured out-of-the-box to attempt this automatic ZTP discovery process.
		
	- The ZTP server itself doesn't usually give the device its configuration and Junos upgrade directly. Instead, the server tells the device where to find this information on the network. And if a ZTP server does not exist on a network, then the device boots in the usual way, with its standard factory-default configuration.
	
- [DHCP (Dynamic Host Configuration Protocol)]: A protocol that automatically offers network configuration to hosts on a network. A protocol that drives ZTP.
	
	- DHCP server receive DHCP requests, and reply with IP information about the network, such as an IP address for the machine, a subnet mask, a default gateway, and the IPs of any DNS servers that can translate domain name into IPs. 
		
	- DHCP servers are configured with a block of IP addresses that they can allocate to machine that need one. This block is often called a "pool"-and unlike a regular subnet you can chose any starting and ending address that you like for your pool of IPs.
	
- DHCP is a 4 step process.
	![[Pasted image 20250522195711.png]]
- When a ZTP-enabled Junos device joins a network, it sends out a DHCP message asking for the various IP pieces that are required for it communicate on the network. This IP information is not permanent-it's there as long as it takes to make the full ZTP process works.
	
	- In addition, the DHCP messages contain a field called "DHCP Options", which are a series of numbered items that can be requested and offered. Ex: Option 1 is subnet mask, 3 is default gateway, 51 is length of time that this information is valid before it is refreshed, ...
		
	- Using these DHCP options, a DHCP server can communicate everything that is needed. To be clear, the software and the configuration does not need to be on the DHCP server itself. Instead, these pieces are usually hosted elsewhere in the network.

<h2 style="color:#6290C3"><center> Junos OS Architecture </center></h2>
## The Routing Engine

- A routing engine is a regular computer that has CPU and Memory. It performs a variety of tasks such as running and maintains monitoring, management, system settings, chassis settings, protocols, and more.
	![[Pasted image 20250522203019.png]]![[Pasted image 20250522203043.png]]
	- Routing Engine can be found on the two main types of device: Modular Chassis which has dedicated line card slot for RE, and Fixed Port Device.
	
- The RE is not responsible for processing transit traffic, but only for creating and maintaining the forwarding table.
	![[Pasted image 20250522203537.png]]
## The Packet Forwarding Engine

- [PFE (Packet Forwaring Engine)]: The pieces of infrastructure that have designed to forward traffic in the most optimal way. The PFE performs Layer 2 (Ethernet) and Layer 3 (IP) packet switching, frame switching, lookups, data manipulation, and packet forwarding. The PFE chooses the next-hop for incoming traffic, it rewrites and manipulates packet and frame headers as needed at lightning speed.
	
	- By contrast, the PFE is the muscle of the device. It forwards traffic as fast and efficiently as possible. It has very little intelligence of its own. Instead, the job of the PFE is to follow the instructions given by the RE. But it does have its own table.
	
- The engine of the PFE is a special chip that is known as ASIC.
	 
	- [ASIC]: Application Specific Integrated Circuit, are purpose-built to perform a very specific task, and to perform it in the fastest and most optimal way possible. EX: the PFE.
	![[Pasted image 20250522205530.png]]
- The main job of the PFE is to look up each incoming frame or packet against the forwarding table and decide how to forward the traffic. Another job of the PFE is to manipulate packets and frame in transit.
	
	- The PFE takes care of services that have an impact on transit traffic, such as rate-limiters, firewall filters, and the ability to prioritize one kin of traffic over another during times of heavy network congestion.
		
	- The PFE ASICs also report back to the RE with hardware and environmental status message so the RE can act on them as appropriate. Actually, the PFE doesn't talk to the RE directly, this is doe via an onboard line card CPU.
	
- [Control Plane]: Refers to the function performed by the routing engine, which is the hardware. 
	
- [Forwarding Plane/Data Plane]: The processing of transit traffic, the abstract idea of the functions performed by the PFE.
	
- The Separation of the Control Plane and Data Plane:
	![[Pasted image 20250522210746.png]]![[Pasted image 20250522211723.png]]
- Broadly and Specifically of PFEs:
	![[Pasted image 20250522211915.png]]
	- Sometimes, you will hear the term "PFE Complex". In fact, advancements in hardware mean that some ASICs nowadays are "sliced" into two. Each receives a copy of the forwarding table, and each slice offers its own dedicated bandwidth.
## Transit Traffic and Exception Traffic

- [Line Card CPU]: Responsible for managing the components on that PFE, and for connecting the PFE to the Routing Engine. It sends counters, status, and logs up to the RE, and receives the copy of the forwarding table from the RE. The line card CPU will install it into all of the ASICs that it controls on that line card. In other words, if a lie card had multiple forwarding ASIC chips, this one CPU would be responsible for managing all of them.
	
	- It can also refer to a single fixed line card inside a chassis.
	
- [Transit Traffic]: Describes the packets that pass through a networking device, from a remote source to a remote destination. If a packet enters one ingress port, is looked up in the PFE's forwarding table, and then exits out of an egress interface, then it is called transit traffic, this includes multicast traffic which may egress out of multiple interfaces.
	![[Pasted image 20250522212847.png]]
- [Exception Traffic]: Refers to traffic that needs to be sent to the Routing Engine for processing, using the internal link.
	![[Pasted image 20250522212932.png]]![[Pasted image 20250522213112.png]]
	- Thanks to advancement, some exception traffic can be processed on the line card cpu itself, this help the routing engine to focus on more important task and de-load the routing engine tasks.
		
	- Things that are not considered as a Exception Traffic:
		
		- Transit Packets that comes in on one network interface and go out of another network interface. These packets are processed only by the forwarding plane. and require no special handling above and beyond the kind of processing that is required to forward traffic to a destination, or the kind of processing that is required to perform the usual rewrite and manipulation tasks on the data.
			
		- Internal Control Packets, like the kind of traffic that is sent between the line card CPU and the Routing Engine CPU. This includes traffic containing updates to the forwarding table, and it also includes interface traffic statistics and counters, logs, environmental information about the line card.
	
- Useful Exception Traffic Knowledge:
	![[Pasted image 20250522213903.png]]
## FreeBSD and How It Relates to Junos OS

- Junos OS is based on FreeBSD kernel. The code is based on FreeBSD, and runs on top of FreeBSD.
	
- Junos gives you direct access to the Junos FreeBSD shell via `start shell` if in operational mode. When you're in the shell, you can access Unix commands to verify the underlying device.
	![[Pasted image 20250522214430.png]]
- Each version of Junos OS is based on a particular version of FreeBSD.
	
	- First, the Junos file naming convention may change between FreeBSD versions.
		
	- Second, when you upgrade Junos, there is an option to roll back to a previously installed version of Junos. However, this options is sometimes removed then the underlying FreeBSD kernel also been upgraded. If the underlying FreeBSD kernel has radically changed, then Junos rollback may not be possible.
		
	- Third, sometimes FreeBSD version change is so significant that you may need to do incremental upgrades to get from one Junos version to another.
## Junos OS Daemons

- [Daemons]: Background process that always runs. These individual processes each run in their own protected memory space, which mean that a failure of one daemon will not affect the rest of the system. Indeed, individual daemon can be restarted, which is more convenient than restarting the entire device.
	
- Networking functionality in Junos is a set of daemons that run on top of the kernel. The kernel then handles all the communication between these applications along with OS functionality, such as memory allocation and scheduling.
	
- [Monolithic Architecture]: The entire OS is like one single application, running in a single flat memory space, with the entire single OS using all the resources.
	
- Type `show log messages` to view logs.
	![[Pasted image 20250522215646.png]]
- [rpd]: The Routing Protocol Daemon. It controls routing protocols, maintain routing tables, determines the active routes, and creates the forwarding table. It also implements routing policy, which is a configuration that controls what prefixes are learned and advertised. Each routing protocols runs as a separate task within this daemon.
	
- [mgd]: Management Daemon. This controls more than just the CLI-it's the glue that binds together all management methods, including the J-Web and external code or controllers. It enables all of these methods to interact with the true underlying architecture of the device, which uses something called XML.
	
- [dcd]: Device Control Daemon. Responsible for pushing physical interface configuration to the actual ports on the device. A handy feature of this daemon is that it gives you the ability to configure interfaces that don't yet exist.
	
- [chassisd]: Chassis Daemon. Handles chassis, alarm, and environmental processes, detects the line cards and interfaces, and monitors the hardware, power, temperature, and cooling. Under extreme temperature conditions, this daemon may also shutdown components to avoid damage.
	
- [snmpd]: Simple Network Management Protocol Daemon. Generates SNMP message that can be sent to external monitoring systems.
	
- [ppmd]: Periodic Packet Management Daemon. Process that enables the line card CPU to handle some trivial tasks that were once exclusively the job of the Routing Engine.
## Junos OS Evolved

- FreeBSD is replaced with Linux. Not tied to underlying hardware. Can be integrate with third-party applications since it run on hypervisor Linux.
	
- Daemon are now individual applications, no longer tied to the kernel. Data are stored in a distributed database that applications can access, no longer internally and locally.
	![[Pasted image 20250522221507.png]]

<h2 style="color:#6290C3"><center> Logging, Troubleshooting, and Monitoring </center></h2>
## Viewing Log Files

- [Syslog]: A way of logging events on Unix-like systems. There are three broad elements to creating a syslogs:
	
	- The facility describes the class of events that you want to log.
		
	- The severity levels is a number between 0 and 6 for different log levels. Each level signifying increasingly detailed logging information. You can also use log level 7 to represent all levels.
		
	- The destination of the log could be a local file, an external syslog server, or your CLI session.
	
- Type `show log {file name}` to view logs files. `show log messages` to view general system events.
	![[Pasted image 20250527154605.png]]
	- Notice that each log entry starts with a timestamp. New log are added at the end of the file, and hey are listed from the earliest to latest. You can also pipe this command for further uses. 
	
- Type `show log interactive-commands` to track all typed CLI commands. Make sure to pipe `match user` to show cleaner logs or show commands that are produced by other users. You can also pipe with the keyword `last` to limit the amount of output.
	![[Pasted image 20250527155023.png]]
- When a log file is full, Junos archives the files and compressed it, then a new file is created. The compression that Junos use is Gzip `.gz`. In addition, Junos also has default limits to the number of archive files that it will create. Mind you that these log files are custom-able. To show all existing log files type `show log mess?`.
	![[Pasted image 20250527155535.png]]
- Type `show configuration system` to see all default syslog information that is configured under the `system syslog` hierarchy.
	![[Pasted image 20250527155820.png]]
	- On each new line, the first word is the facility level being logged. The second word is the logging level.
	
- Example of syslog facility options in Junos.
	![[Pasted image 20250527160023.png]]
- Example of syslog severity levels.
	![[Pasted image 20250527160159.png]]
	- Note that notice is more than enough for everyday events since it doesn't place unneeded strain on the routing engine.
	
- Type `set system syslog file {file name} {facility name} {severity name}` to create a new syslogs. You can also use archive the define the number of files, size of files, and whether all users can view it.
	![[Pasted image 20250527161720.png]]
- Type `monitor start {file name}` to view log in real-time, `monitor stop` to end process or `esc-q` to halt and resume the real-time output.
	![[Pasted image 20250527161915.png]]
- Type `help syslog {syslog code}` to decode a message code, or show a detail explanation of a message code.
	![[Pasted image 20250527162016.png]]
- Type `set system syslog host {ip address} {severity levels}` to stream logs to an external server. It is very helpful when storing logs because it prevents rogue actors from getting the chance to delete the logs, and therefore delete the evidence of their wrongdoing. 
	![[Pasted image 20250527162309.png]]
	- Or you can send logs directly to the CLI using the `user` option.
	![[Pasted image 20250527162318.png]]
## Network Connectivity Troubleshooting Commands

- Adding the keyword `rapid` to the `ping {ip address}` to send many rapid pings in a very quick succession. This will send the next ping as soon as a reply has been received for the previous ping. If a response is not received, Junos waits up to a maximum of 500ms before declaring the ping has timed out, and then sending the next ping.
	![[Pasted image 20250527163014.png]]
	- You can combine this with the `count` option to send hundreds of quick pings to the remote destination, and perhaps even thousands, ...
	![[Pasted image 20250527163308.png]]
	- Although it is important that the control planes of some devices do not prioritize the generation of ICMP replies. As such, if the device at the other end of the link happens to be busy processing a large and important routing update, there;s a chance that your pings will not receive a reply. This does not indicate any kinds of problem on the link itself because transit traffic will not be affected.
		
	- Similarly, remember that Junos applies rate-limiting to the link between the Packet Forwarding Engine and the Routing Engine. This is a good thing because it protects you from denial of service attacks. It also means that there's a chance of your rapid pings being dropped by a remote Junos device and indeed by any device with a similar architecture.
	
- You can also use `ping` to check for MTU problems. Make sure to use the `size` to specify how big the payload of the ping should be.
	![[Pasted image 20250527164127.png]]
	- Additionally, use the `do-not-fragment` options to set this flag in the IP header. This is perfect for testing MTU problems with some downstream device because it will guarantees that the ping will not be fragmented in transit if the Layer 3 MTU is smaller than the packet. If you don't set this option, it might succeed and you will tested nothing from this test.
	![[Pasted image 20250527164145.png]]
- [Traceroute]: Gives he visibility of each hop in the path from source to destination. It sends three packets with a TTL (IPv4) or Hop Limit (IPv6) of 1. These packets contain a UDP payload on most vendors, and an ICMP ping payload on Windows. When the next hop receive the packet, it sets the TTL to 0, and then generates an "ICMP Time-to-Live Exceeded" that it sends back to the source IP in the packet of this reply. And with that you know the first hop in the path. Each round of three packets increases the TTL/Hop Limit by 1 until the traceroute finally reaches the destination. In doing so you get visibility of every hop in between the source and the destination.
	![[Pasted image 20250527184815.png]]
- Common misunderstandings about `traceroute {ip address}`:
	
	- Sometimes the hop is configured to not accept or reply to traceroute traffic, if it was faulty then the whole traceroute would fail.
		
	- Sometimes the hop is slower then the rest of the result. This does not indicate that the responding hop is the blame for slow speed,because if it is then all the hops after that hop would be slow. But in fact it is configured to not prioritize traceroute replies. If all the bandwidth afterwards are fast, then it is not the bandwidth bottleneck.
		
	- Remember that a traceroute shows the path from source to destination-but the return traffic could have taken a completely different path. To successfully diagnose problems you need both ends of a connection to run a traceroute to each other.
	
- Checking ARP and NDP is an easy way to verify hosts on the LAN. For IPv4 use `show arp` to check all IPV4/MAC bindings learned by a Junos gateway. Notice that the entries are listed in numerical order of the IPv4 address.
	![[Pasted image 20250527185749.png]]
	- For IPv6 type `show ipv6 neighbors` to check IPv6/MAC bindings. THis reveals all MACs learned via NDP.
	![[Pasted image 20250527185849.png]]
- SSH from Junos itself. 
## Viewing Live Traffic Statistics and Exception Traffic

- Type `monitor interface traffic` to show live traffic stats across all interfaces and will help you find the one interface that requires further exploration.
	![[Pasted image 20250527190305.png]]
	- Note that type `monitor interface {interface name}` shows you information about the interface that you want to monitor. It offers general packets statistics and error counters.
	![[Pasted image 20250527190535.png]]
- Note that `monitor` give you live statistics (real time), `show` give you snapshots (initial).
	
- Type `monitor traffic {interface name}` for a summary of all the control plane traffic on the interface that you specify, both in and out of the interface. You can also add the keyword `detail` and `extensive` options on this command to look inside the contents of the messages to get full visibility.
	
	- In addition, you can also use the `write-file {file name}` options to save the packets to a packet capture file, so that you can export it to your computer and open it up in a packet capture viewer such as Wireshark.
		
	- By default, Junos will try to be helpful by performing a reverse DNS lookup search on any IPs to find their hostname. It is recommended that you turn this off using the `no-resolve` option in the command. This will speed up your output.
## Built-in Help Documents

- Type `help apropos {keyword}` to reveal every single command that contains your keyword. 
	![[Pasted image 20250527191519.png]]
- Type `help topic ?` to browse for a topic and `help topic {topic name}` to learn about a topic.
	![[Pasted image 20250527191629.png]]
- Type `help reference ?` to reveals help configuration syntax options and `help reference {configuration options}` to displays a complete list of related configuration options and it also offers other details and things to bear in mind.
	![[Pasted image 20250527191853.png]]

<h2 style="color:#6290C3"><center> Junos OS Firewall Filters </center></h2>
## Stateful Security Policies and Stateless Firewall Filters

- [Stateful Traffic Rules]: It have the ability to look across multiple packets to understand which packets belong to the same session (called a flow in Junos).
	![[Pasted image 20250527201332.png]]
	- They do this by recording information about each packet in a session table. They then compare every new packet to the information already recorded. In other words, they keep track of the state of these sessions, hence the name stateful rules.
		
	- This stateful tracking means that stateful rules can bring some intelligence to your configuration. 
		
	- These rules are typically used on hardware firewalls, and on virtual software firewalls. This is because the stateful maintenance requires additional processing of each packet as it transit the device. It's important to have specialist hardware that is up to the task performing this additional processing-or, to allocate enough additional memory and processor capacity for accommodate for this additional processing.
		
	- Another reason is that it is common for a hardware firewall to perform many more security checks, other than simply checking source and destination IPs and ports.
	
- [Stateless Traffic Rules]: Process each individual packet on its own merit. In other words, stateless rules do not care what traffic has come before or what is going to come afterward. 
	![[Pasted image 20250527204430.png]]
	- Stateless rules have no idea if the packet belongs to an existing session. Each packet is processed in isolation, and no state is tracked.
		
	- In fact, stateless rules are rarely used to control every single aspect of the traffic flow through a device. This is really the function and purpose of a firewall, rather than a router or a switch. Instead, you use stateless rules to perform "quick and easy" filtering. Meaning that there is no need for extensive data processing here, or to keep track of some kind of stable table, just drop it and move on.
	
- Stateful rules are called security policies as they are created under a dedicated `security` configuration. Stateless rules are called firewall filters, as they are configured under a dedicated `firewall` hierarchy.
## Firewall Filter Terms, and the Actions They Take on Packets

- Basically just a tons of `if/then` statements, but in Junos they are `from/then` statements. Each statement is called a `term`, a firewall can contain as many terms as you like, each term is processes from top to bottom.
	![[Pasted image 20250527205402.png]]
	- A term contains zero or more match conditions, and one or more actions.
	
- [Match Conditions]: You specify your match conditions using the `from` keyword. Firewall filters can match on almost any field in any header.
	![[Pasted image 20250527205648.png]]
	- You can even match multiple elements on one term. Some conditions are logical `AND` others are a logical `OR`.
	![[Pasted image 20250527205759.png]]
- [Terminating Actions]: You use the `then` statement inside your term to decide your actions. You can divide all of the available actions into two categories. The first category contains something called terminating actions. 
	![[Pasted image 20250527210031.png]]
	- If you use one of these actions, then processing ends, and no more terms are analyzed. In other words, the processing of the firewall filter is terminated.
		
	- Reason to favor `discard` is it is easier to drop the packet (lower the work load), and preventing malicious attacks by sending back a reply.
	
- Firewall filters give you total control over how packets are processed and manipulated.
	![[Pasted image 20250527210325.png]]
- [Nonterminating Actions]: These actions still terminate processing by default. This is because these actions all come with a default, implicit actions of `accept`, and they also offer you the ability to use an action of `next term`. 
	![[Pasted image 20250527211111.png]]
	- However, if you were to configure both `log` and `next term` then the traffic would be logged, but the processing would continue to the next term. You could use this to log a wide range of traffic, regardless of whether another term decides to accept or deny it.
	![[Pasted image 20250527211309.png]]
## Processing Terms in a Firewall Filter

- Firewall filters are made active by applying them to an interface. You can either apply them inbound or outbound. When a firewall filter is active, every single packet is inspected against each individual term in the filter. This happens in the order that the terms are configured, from the first filter to the last.
	
- If an interface has a firewall filter applied to it in a particular direction, then every packet in that direction will be inspected against the firewall filter. If a packet does not match any term, it will be dropped. This is because firewall have an implicit term at the very end which matches all traffic, and has an action of `discard`. If you want to allow all other traffic, you will need to configure an explicit final term with an action of `accept`.
## Junos OS Firewall Filter Configuration

- All stateless filters are configured within the `firewall` hierarchy. Within that you configure the firewall filter within the address `family` of your choosing. This is very help for keeping tour filters organized. It also means Junos will only offer you match conditions that make sense for that address family. The firewall filter is then given a unique name of tour choosing.
	![[Pasted image 20250527213245.png]]
	- Within one term, there are two sections-you have a `from` section for your match conditions and a `then` sections for your actions.
		
	- Type `set firewall family {ip version} filter {filter name} term {term name} from {match conditions}` to set up match conditions for a term. and `set firewall family {ip version} filter {filter name} term {term name} then {actions}` to set an actions for that term.
	![[Pasted image 20250527213550.png]]![[Pasted image 20250527213628.png]]
-  When it comes to well-known applications, Junos gives you the ability to refer to many of them by name in your `from` conditions. 
	![[Pasted image 20250527214232.png]]
	- In additions, it's good to know the options of how to apply this. As you can see, you can choose to filter just one the `source-port`, or just on the `destination-port`. You can also say `from port` if you want to match either.
		
	- It's worth saying that when you refer to a port number, then your configuration actually matches both TCP and UDP traffic. You can choose to be more specific by using the `from protocol {tcp/udp}` options. Indeed, there is a good argument to say that you definitely should mention the protocol alongside the port, so that you don't accidentally allow traffic through that you intended to block.
	
- Type `show configuration firewall family {IP version} filter {filter name} | display set relative` to show the set commands as if you were at that point in the hierarchy.
	![[Pasted image 20250527214437.png]]![[Pasted image 20250527214451.png]]
- Type `set firewall family {IP version} filter {filter name} term {term name} then accept` to explicitly allows all other traffic since it has no `from` conditions.
	![[Pasted image 20250527214708.png]]
- You can choose to apply the filter to either inbound traffic or outbound traffic. If you want to filter both kinds of traffic, then it's a good practice to make two separate firewall filters-one for each directions. 
	
	- As a general rule, you should apply your filters as close to the traffic as possible. The reason for this is that it gives you the opportunity to block forbidden traffic as early as possible.
	
- Options to apply filters:
	
	- Apply the filter outbound on the WAN Interface. This is a good choice when you need to refer to multiple sources of LANs that come  into the router on multiple different interfaces. You can use one single firewall filter that applies to all traffic outbound to the internet. However, the downside is that it does not filter your traffic as early as possible. When you think about it, packets will enter from a LAN interface and will be processed in the forwarding table. It's only when the packet is almost ready to leave the WAN interface that the packet is dropped.
		
	- Create multiple firewall filter. Mistakes, inconsistency might happens. It allow you to drop traffic as early as possible.
		
	- Apply same firewall filter to multiple LAN interfaces. This makes your device to have a finite amount of room in its PFE to store firewall filters.
	
- Type `set interfaces {interface name} unit {number} family {IP version} filter {output/input} {filter name}` to create either an outbound or inbound to an interface. Note `output` means that it will be processed at the point when the traffic is almost ready to leave the interface, `input` is vice versa and for inbound firewall filter.
	![[Pasted image 20250527220019.png]]
- Use `ping` to test and verify the firewall filter traffic.
	
- Type `show firewall counter {counter name} filter {filter name}` as an alternative to verify your traffic via counter. 
	![[Pasted image 20250527220227.png]]
## The insert Command

- Use `insert family {ip version} filter {filter name}` to move terms within a filter. You use it in combination with the `before` and `after` keyword to insert the term before or after any other term of your choice.
	![[Pasted image 20250527220624.png]]
