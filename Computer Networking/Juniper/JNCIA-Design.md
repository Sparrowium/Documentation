Associate Design

<h2 style="color:#6290C3"><center> Network Design Fundamentals </center></h2>
## The Architect/Designer Role

- Assess the customer's current environments and its ability to satisfy their current business and technology requirements.
	
- Identify the technology shortfalls that need to be addresses.
	
- Develop a core technology roadmap that will achieve the customer's required endgame environment.
	
- Evaluate what is necessary for migrating successfully from one environment to another.
	
- Create high-level architectural designs and low-level detailed designs of network devices, configurations, and interconnections.
## Doing the Research

- Research about the customer:
	
	- The business and industry the customer is in.
		
	- What sets the customer apart from competitors.
		
	- What network design will meet their approval.
		
	- Business requirements and goals, state of the current network environment, analyze current and future network behavior.
	
- Engaging with the customer;
	
	- Recognizing and understand their management hierarchy.
		
	- Identify who makes the decisions. Work closely with the customer to learn their overall goal.
		
	- Understand the criteria or a successful design. Know where the risks are and consequences for failure.
	
- **Expect some Back-and-Forth.**
## Creating a Network Design

- [Juniper Network's Lifecycle Service]: Consist of three main phases and it's often cyclical throughout the design's lifetime.
	![[Pasted image 20250504204713.png]]
	- [Planning Phase]: Assess the current environment and determine if it can satisfy the requirements proposed by the consumer. After evaluating the current setup, it will then move on to designing high-level architectural plans as well as low-level details of devices, configuration, and interconnection.
		
	- [Build Phase]: Deploying both test and production environments. Migrate from the existing environment to a new one, taking care of installations, configuration, system testing, and system enablement.
		
	- [Operate Phase]: Supporting the customer by making sure we have the most effective use of the solution and will provide assistance for any issues and faults, and carry out proactive maintenance. Optimize over time.
	
- [Plan Methodology: Data Analysis]: The design or plan phase of the service life cycle. Consist of two key subphases.
	![[Pasted image 20250504204702.png]]
	- [Assess Sub-phase]: Evaluate the current environment and its ability to meet the customer business and technological needs. 
		
		- Identify technology gaps that need addressing and develop a core technology roadmap to achieve the customers desired in game environment. Determine what's necessary for successful migration from one environment to another. 
			
		- Define a scope of design projects, which could range from a small network segment to an entire network, also determine if it's a simple upgrade or an entirely new network.
			
		- Conduct a Data Analysis to assess the current networks condition and also identify improvements based on customer requirements and the project scope. Examine how the business drives data usage on the networks and the number of users accessing the network both internally and externally.
		
	- [Design Sub-phase]: Create high-level architectural plans and detailed plans for network devices, configurations, and connections.
		
		- Develop a project plan, outlining responsibilities, timelines, and dependencies.
			
		- Work on the high-level design, which is usually a logical topology that identifies protocols used, network addressing, security, and naming conventions.
			
		- Focus on the low-level design, which deals with the physical aspects, including the specific devices to be used, cabling, and wiring considerations.

<h2 style="color:#6290C3"><center> Routers and Switches </center></h2>
## Juniper Routers

- Include: PTX Series, MX Series, ACX Series, SSR Series (Sessions Smart Routers).
	
- [Core Routers]: Specially design to function in the backbone or core of the network.
	
- [Edge Routers or Access Routers]: Serve as gateways at the network edge. They facilitate connectivity between internal networks and external networks.
	
- [PTX Series]: Packet Transport Routers, designed to optimize IP/MPLS core, peering, metro, and converged IP and optical networks. They support high-density 100-Gigabit Ethernet and 400-Gigabit Ethernet environments, and they're fairly energy efficient with less than half a watt per gigabit. The PTX routers are available in fixed form factor models with up to 16 Tbps throughput, as well as modular chassis models with up to 14.4 Tbps per slot.
	![[Pasted image 20250504214134.png]]
- [MX Series]: An impressive collection of SDN-enabled routers designed to deliver top-notch capacity, density, security, and performance. These routers play a crucial role in the digital transformation process for service providers, cloud operators, and enterprises. It allows you to implement a variety of services, such as carrier-grade NAT, stateful firewalls, and deep packet inspection. Juniper has teamed up with Corero Network Technologies to provide real-time DDoS protection. By combining the MX with Corero's SmartWall Threat Defense Director.
	![[Pasted image 20250504214207.png]]
- [ACX Series]: Specifically designed for backhaul access and aggregation, which means they help link remote sites to a central hub.
	![[Pasted image 20250504214449.png]]
- [SSR Series]: Session Smart Routers, a networking solution aimed at helping businesses make use of SD-WAN. This router is a practical option for businesses seeking secure and adaptable WAN connectivity that is both efficient and easy to manage. 
	![[Pasted image 20250504214414.png]]
	- The SSR enables the creation of a flexible, application-aware network fabric that caters to specific performance, security, and availability needs. Being an SDN solution, it can be deployed on white-box CPE, data center network servers, or even in the cloud. You can manage and orchestrate the SSR through the Juniper Session Smart Conductor or the Juniper Mist Cloud.
		
	- The white-box SSR solution consists of two primary components: the Session Smart Router and the Session Smart Conductor.
## Juniper Switches

- [EX Series]: Divided into three categories: access, aggregation, and core. Access switches, such as the EX2300, EX3400, EX4300, and EX4400, let users and devices connect to the network. Aggregation switches, like the EX4600 and EX9200, consolidate connections from multiple access switches and link to the core. Lastly, core switches like the EX4650 and EX9250 are high-capacity switches at the center of your network.
	![[Pasted image 20250504213900.png]]
	- The EX2300 and EX2300-C switches are ideal for smaller network environments with limited space and power. The EX4300 and EX4400 switches are excellent for high-performance campuses and data center access requirements. They both are Multigigabit switches that are perfect for advanced branch or campus deployments. The EX4600 and EX9200 lines of switches are well-suited for enterprise campus distribution and data center top-of-rack environments. The EX4650 switch is designed for midsize to large enterprise campus distribution deployments. The EX9200 line of switches, including the EX9204, 9208, and EX9214, offers a programmable, flexible, and scalable foundation for mission-critical applications. Meanwhile, the EX9250 line of switches, such as the EX9251 and EX9253, provides compact, programmable, and scalable core and aggregation devices for enterprise environments.
		
	- EX Series switches are an integral part of the  Mist AI-driven enterprise solution, and you can set up, deploy, and manage them through the Mist Cloud. 
	
- [QFX Series]: Designed to make data center operations more straightforward and efficient. They use a two-tier spine-and-leaf architecture, also known as a Clos fabric, which means data only passes through three devices to reach its destination. The QFX5100 Series works well for top-of-rack, end-of-row, and spine-and-core deployments, while the QFX5200 switches suit spine-and-leaf fabric deployments in data centers and metro use cases.
	![[Pasted image 20250504213727.png]]
	- The QFX10000 line can be used in various designs and fabrics for Layer 2 and Layer 3 networks, such as EVPN/VXLAN-based overlays on an IP fabric underlay. The QFX10002 fixed configuration switch provides several interface options in a compact 2U form factor. The QFX10008 and QFX100016 are modular data center spine and core Ethernet switches that are capable of transitioning between 10-Gigabit, 40-Gigabit, and 100-Gigabit Ethernet interface speeds.
	
- [Juniper Mist Cloud]: A cloud service offers a variety of features, such as Wi-Fi Assurance, Wired Assurance, WAN Assurance, Premium Analytics, Marvis, User Engagement, Asset Visibility, and Risk Profiling. 
	![[Pasted image 20250504214007.png]]
	- The wired and wireless infrastructure is composed of several components. Mist Access Points are deployed on-premises for Wi-Fi, Bluetooth Low Energy (BLE), and IoT access. Juniper Mist Edge extends the microservices architecture to the campus.
	![[Pasted image 20250504214013.png]]
- [Juniper Mist Assurance]: A cloud service that streamlines managing your wired Ethernet switches, IoT devices, access points, servers, printers, and other equipment. Wired Assurance assists with onboarding and auto-provisioning. As your network grows, it continues to ensure everything runs smoothly with simplified operations and management. Plus, with EX and QFX switches, you'll gain access to insightful streaming telemetry, providing valuable information about your network's performance.
	![[Pasted image 20250504214036.png]]
	- Some of the key features include the ability to set up, configure, and manage EX and QFX switches from Mist Cloud. It also utilizes open APIs for automation across third-party integrations, and offers AI-driven insights into switch performance.

<h2 style="color:#6290C3"><center> Security and Wireless </center></h2>
## Juniper Security

- To assist customers in creating a network that's aware of potential threats. Keep in mind that means that the network is aware, which means you don't have to examine the network for threats 24 hours a day manually. It does this by extending security measures to every point of connection on the network, allowing for better protection of users, devices, applications, and also infrastructure.
	
- Instead of focusing solely on traditional network chokepoints for attack detection and mitigation, we use routers, switches, and access points to strengthen network defense. By making the entire network an integral part of its own protection, attacks can be identified and addressed more rapidly, leaving more room for legitimate traffic to flow smoothly.
	
- [SRX Series]: Are high-performance with advanced security features on a dependable platform. There are models designed for small enterprises and branch offices, mid-size enterprises and data centers, large data centers, and service providers.
	
	- Virtual version called vSRX, which offers the same features in a virtualized format for added flexibility. Moreover, the cSRX containerized firewall delivers advanced security for applications running in containers and microservices.
	
- [NGFW Series]: Integrates extra security services like IPS, SSL inspection, URL filtering, and unknown threat detection.
	
- [Juniper ATP]: An effective security solutions hat protects against advanced malware and cyberthreats. Deployable on cloud or as an on-site appliance, and its integrates smoothly with SRX series devices to deliver threat intelligence, malware analysis, and mitigation capabilities.
	![[Pasted image 20250506185052.png]]
- [Juniper Network Cloud Workload Protection]: A security solution aimed at safeguarding application workloads in any cloud or on-premises environment. It actively defends against attempts to exploit application vulnerabilities, including the OWASP Top 10 and memory-based attacks.
	![[Pasted image 20250506185107.png]]
	- By controlling application execution and monitoring the application's behavior and context, it compares the intended actions with what's happening in real-time. This approach helps ensure that applications always have a safety net against vulnerability exploits, keeping important business services connected and protected. What's more, Juniper Cloud Workload Protection automatically defends against targeted vulnerabilities without requiring any administrator intervention.
	
- [Juniper SecIntel]: Keeping your network secure by offering threat intelligence at every point of connection. This covers the WAN edge, wired and wireless LANs, and enforcement points within the network, helping you block harmful traffic and create a more secure network environment. And so, by aggregating data from various sources, including Juniper devices and third-party sources, SecIntel provides curated, consolidated, and actionable intelligence. This information is then delivered to SRX, MX, EX, QFX, and Mist devices.
	![[Pasted image 20250506185128.png]]
- [Juniper Secure Analytics (JSA)]: A fantastic tool for managing and analyzing security events. It helps you sort through loads of data from different devices, endpoints, and applications in real time. Thanks to its advanced big data analysis capabilities, it's quick at spotting potential threats.
	
- [Juniper Secure Connect]: An SSL VPN application that helps remote workers securely access their corporate and cloud resources. It's compatible with a range of devices like Windows, MacOS, Android, and iOS.
## Juniper Wireless

- [Mist  AP]: Mist Access Point, are designed to work with Juniper Mist Cloud Services and Mist AI. They support 802.11ax (Wifi 6), 802.11ac Wave 2, BLE, and IoT.
	
- [Mist Edge]: Extends the microservices platform to the campus, bringing agility and scale while also enabling new applications at the edge. This solution is deployed as a standalone appliance, available in multiple variants for different-sized deployments. This way, organizations can easily manage and monitor their wireless APs.
	
- [Mist Cloud Service]: Designed to simplify network management and automate business operations. They come with a range of programmable features using open APIs, making it easy to integrate them with your IT applications.
	![[Pasted image 20250506184948.png]]
	- It is a versatile and entirely programmable solution that can be integrated with IT applications to streamline both network and business operations. Thanks to open APIs, you can access all Mist Cloud functions, like provisioning, monitoring, and alerts, with the API, giving you full control over your network.
		
	- [Wi-fi Assurance]: A cloud-based service that leverages machine learning and Mist AI to make Wi-Fi more predictable, reliable, and measurable while providing unique visibility into user service levels.
		
	- [Wired Assurance]: Another feature that introduces Mist AI to access layer switching, improving the experience of devices connected through EX and QFX switches.
		
	- [WAN Assurance]: Simplifies operations, enhances visibility into end-user experiences, and shortens the mean time to repair for both wired and wireless devices.
		
	- [Marvis]: A virtual network assistant, uses Mist AI to proactively transform network operations for enterprise WLANs, LANs, and WANs.
		
	- [Mist Premium Analytics]: Provides network visibility and business intelligence.
		
	- [User Engagement Cloud Service]: Utilizes Virtual BLE array technology and cloud-based machine learning to boost the accuracy of real-time indoor location services.
		
	- [Asset Visibility]: Makes locating key assets and people simple.
		
	- [Risk Profiling]: Brings network security to the distributed access network edge by evaluating the risks associated with each connecting device and implementing access and security policies.

