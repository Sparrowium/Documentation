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
		
	- Make sure to use the exact keyword at the end of the command if you only want to see the exact prefix you're searching for.
		
	- Note that `/32` is listed as a Local route. This means that the IP is indeed configured on the actual interface itself. The address is local to the device. This sometime protect you against an incorrect static route.
	
- Type `show route table [content] protocol direct` to see all directly connected routes. 
	![[Pasted image 20250513203035.png]]
- The process for viewing and reading the `inet6.0` is identical to `inet.0`. 
	![[Pasted image 20250513203358.png]]
	- Noted that `/64` give the first half for network portion, second half for host identifiers. `/128` refers to a specific host address, since IPv6 is 128 bits long.