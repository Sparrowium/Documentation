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
	
- --Expect some Back-and-Forth.--
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

<h2 style="color:#6290C3"><center> SDN and Network Management </center></h2>
## Juniper SDN

- [SDN]: Software Defined Networking, an approach to network virtualization and containerization that seeks to optimize network resources and quickly adapts networks to changing the business needs, applications and traffic.
	
	- With SDN, the functions of network orchestration, management, analytics, and automation become the job of the SDN controllers. Because these controllers are not networking devices, they can take advantage of the scale, performance, and availability of modern cloud computing and storage resources.
	
- [Contrail Service Orchestration]: A powerful software platform bridging many enterprise and multitenant service provider solutions including SD-WAN, NFV, telco cloud, as well as others. It also available as an on-premises and as a cloud-managed service.
	
	- Contrail Service Orchestration designs, secures, automates, and runs the entire SD-WAN service life cycle across SRX and NFX devices. And it integrates with Mist Cloud for seamless Wi-Fi management. It also a service orchestrator for the vSRX in public cloud marketplaces such as AWS and Azure.
	
- [Contrail Networking]: Solves networking challenges for different cloud environments. With its scale-out microservices architecture and distributed control and data planes, Contrail Networking orchestrates virtual networks and network services at the performance and scale required of the largest, most dynamic clouds. service providers, enterprises, SaaS providers, and hosting and cable providers. These networks use Contrail Networking to connect heterogeneous cloud environments, accelerating the deployment of cloud applications and services.
	
- [NFX Series]: Are designed to enhance the flexibility and security of a network, with helpful features like ZTP and advanced network security.
	
	- A notable feature of NFX is its role as a key component in Juniper's automated SD-WAN and next-gen firewall solutions. It's a universal CPE platform that's capable of handling multiple Juniper and third-party VNFs on a single device, simplifying the deployment of new applications and services across an organization.
## Juniper Network Management

- [Paragon Automation]: A suite of software tools designed to help businesses optimize their network services. Regardless of whether you're working in a private data center or public or private clouds.
	![[Pasted image 20250506184756.png]]
	- A standout feature of Paragon Automation is its use of AI and machine learning. Think of these as your behind-the-scenes techs, working around the clock to identify and fix problems before they impact your business. This allows businesses to adopt a more proactive approach to maintaining their network services, helping to prevent disruptions and keep everything running smoothly.
		
	- [Paragon Insights]: Designed to keep a network performing at its best by providing consistent and comprehensive operational intelligence. The easy-to-use interface comes with widgets for configuration and dashboards for data visualization and network monitoring. It's designed to be approachable, so you can get the most out of it without a steep learning curve. At the heart of Paragon Insights is its ability to collect data from multiple sources. It can pull from JTI, SNMP, syslog, and OpenConfig telemetry. This tool doesn't just gather a lot of data; it aggregates it to provide a multi-faceted view of your networks and services. But it doesn't stop at data collection. Paragon Insights is equipped to analyze this data in real-time and turn it into actionable insights. It's like having a personal network analyst at your disposal, continuously working to ensure your network is optimized.
		
	- [Pathfinder Controller]: Focuses on simplifying the often complex world of traffic engineering. It collects a bunch of information from your network, including topology, configurations, LSP state information, and telemetry data. The data is made available through the user interface, reports, or the API. With this clear and comprehensive view of the network, operators can manage LSP design in a way that aligns with their specific goals. A important aspect of the Pathfinder controller is its close working relationship with Paragon Planner. It feeds regular snapshots of the network into the Paragon Planner, allowing for offline modeling.
		
	- [Paragon Planner]: Designed to assist network operators in ensuring their networks perform optimally. It's a traffic management solution compatible with various types of networks and protocols, including IP, MPLS, and segment routing. It allows you to forecast how these changes will affect your network without any disruption to your ongoing operations. In addition, you get a transparent view of your entire network and the ability to visualize routing paths, model video-on-demand flows, define Class of Service based application flows, and create VPN models.
		
	- [Paragon Active Assurance]: Designed to simplify network management and orchestration. It is composed of two main software components: the Control Center and virtual test agents.
		![[Pasted image 20250506185446.png]]
		- [The Control Center]: Serves as the central hub for managing the entire system. It can be delivered as a SaaS solution, or if SaaS isn't suitable for your needs, it can also be deployed on-premises. Functionally, both options are identical, offering the same set of features. 
			
		- The Control Center supports northbound APIs like NETCONF and YANG, as well as REST APIs. These APIs simplify integration with network automation tools which can orchestrate the solution and gather results from Paragon Active Assurance for analytics and fault correlation with other sources like Paragon Insights.
			
		- Moreover, the Control Center features a web interface that includes dashboards that display the results of the measurements you conduct and allow you to define templates for easy management and orchestration of the solution.
			
		- [Test Agent]: Are deployed across the network. These lightweight agents are versatile and can be deployed in a variety of scenarios and environments, including on KVM Hypervisor or VMware, in private clouds like OpenStack, or on public clouds with cloud-specific images. They can also function as containers in Docker or be integrated within a Kubernetes environment.
			
		- Test agents work by sending synthetic traffic across the network and then measuring the quality of the links between the client and server agents. Alternatively, they can utilize the reflection capabilities of endpoints on third-party devices using a protocol like the two-way active measurement protocol, or TWAMP. This method, particularly useful for monitoring mobile backhaul as a single test agent to cover thousands of receivers and report any issues.
	
- [Juniper Apstra]: A software-based, intent-driven networking solution that relies on closed-loop automation and assurance, coupled with multi-vendor support, to deliver a comprehensive fabric management solution. This solution can be implemented on any virtual machine or server, and is capable of connecting to and managing devices through agents installed either directly on the devices or remotely. It simplifies and accelerates the processes involved in designing, deploying, and operating data center networks.
	
	- Apstra gives you the flexibility to define multiple logical devices and racks during the network design phase, which can then be assembled into a template. 
		
	- Aspects such as rack types, routing policies, EVPN/VXLAN, IPv4, IPv6, among other resources can be incorporated into these templates and associated with compatible physical device profiles. One amazing thing about Apstra is the multi-vendor support it has. Vendors like Juniper, Cisco, Arista, Cumulus, and many others are all supported.
	
- [Junos Space]: A comprehensive network management solution that has been developed by Juniper to aid in the management of your routing, switching, and security devices.
	![[Pasted image 20250506191234.png]]
	- [Security Director]: Is an application designed to streamline the management of network security. And it acts as an on-premises solution. Its main function is to maintain the security of your network by automating the implementation and orchestration of security policies. This is applicable across a range of devices such as SRX devices, both physical and virtual, EX and QFX switches, MX routers, and even Mist APs. Furthermore, it can also manage third-party network devices.
		
	- Another valuable feature of Security Director is its ability to log and correlate events, generating easy-to-understand charts. This data can then be used to produce reports that are delivered directly to your organization's stakeholders. This insight lets decision-makers develop precise security policies based on user and security trends observed over time. Basically, Security Director is a powerful tool that simplifies the task of managing your network security.
	
- [Security Director Cloud]: A cloud-hosted version of Security Director that allows companies to manage their security policies irrespective of the location of their users, devices, and applications. By using Security Director Cloud, you can establish policies once and implement them across the board, thereby reducing the need for multiple rule sets and simplifying the overall security management process.
	![[Pasted image 20250506191731.png]]
	- One of the major advantages of Security Director Cloud is its ability to synchronize bi-directionally with on-premises and cloud-based firewalls. This helps businesses to have a unified management experience as they shift towards the cloud. The feature of unified policy management ensures that security policies continue to follow the user, device, and application even when they change locations. This eliminates the necessity to manually copy or recreate rule sets, thereby providing a consistent security experience for all users, regardless of their location.
	
- [Juniper Sky Enterprise]: A cloud-based management platform that simplifies network complexity for branch and campus users. With Sky Enterprise, customers can do away with the need to buy, install, and maintain servers and management software on their own. This flexibility allows enterprises to adjust capacity according to their business needs. Sky Enterprise is regularly updated with the latest software and features, allowing the network to be managed centrally with minimal involvement from IT staff. This allows them to concentrate on key business activities, ultimately leading to considerable cost savings. The platform automates tasks such as pre-staging or applying configurations. And new managed devices are securely onboarded automatically and constantly monitored to ensure optimal network performance.
	![[Pasted image 20250506192317.png]]

<h2 style="color:#6290C3"><center> General Requirements </center></h2>
## RFP Requirements

- [RFP (Request for Proposal)]: A mechanism that customers use to request network design proposals from potential vendors. Each RFP is unique, reflecting the specific requirements of each customer. An RFP can be brie or lengthy. An RFP includes:
	
	- Design requirements that detail business objectives, scope, and information about the existing network environments.
		
	- The solution required in the design, such as wireless, high availability, and security.
		
	- Warranty conditions for your products and any legal terms related to the solution.
		
	- Should be prompt, comprehensive, honest, and adhere to the customer's requested format.
	
- [RFI (Request for Information)]: Similar to RFP, it tends to be broad and generally covers only the technical elements of the design request.
	
- RFP Key Elements:
	
	- [Business Elements]: Portray what type of business the customer is in, planning for future expansion, and a rationale for the necessity of the new design.
		
	- [Environmental Requirements]: Facility specifications, number of users and workstations, server room specifications.
		
	- [Modular Requirements]: Hierarchical design consideration, reduction of information within each module, functionality of each module within the design.
		
	- [Connectivity and Throughput Requirements]: Number of wireless and wired connections needs, traffic analysis, calculation for theoretical and overhead traffic.
		
	- [Business Continuity]: Network efficiency, quality of service requirements, load balanced and highly available networks.
## Scoping the Network Design

- Every RFP is unique and you're likely one of several potential vendors. Your initial response is absolutely crucial to remain in the ring for the design contract. Aim to highlight your proposal's benefits in response to each RFP requirement, using the customer's specified format and familiar terminology. An RFP response should include things like:
	
	- [Executive Summary]: Concise outline of your design proposal emphasizing its advantages.
		
	- [Network Topology]: Logical and physical design of the proposed network.
		
	- [Design Details]: Details on devices, protocols, and technologies in the proposed design.
		
	- [Implementation Plan]: How and when the design will be implemented.
		
	- [Training]: Plan for employee training as the new network rolls out. The last thing you want is for the customer not to know how to use the new equipment.
		
	- [Support]: Support and maintenance strategy for the operational design. Something is always going to go wrong.
	
- Defining Key Stakeholders:
	
	- Understanding the Corporate Structure, figure out who holds the decision-making power. Understand their preferences to increase your design's chances of being accepted.
		
	- Engaging with the right individuals. Doing this ensures that there is alignment with the customer's needs, which is crucial for a successful proposal. Be proactive in seeking information about the existing network and the required technical aspects for the new network.
		
	- Navigate Corporate Dynamics, some might prefer other vendors or political divisions might obstruct consensus. Beware of potential resistance from employee if your design affects roles within the company. Being sensitive to the company culture is key.
	
- [Gathering Data]: Employ questionnaires, surveys, and interviews to learn what's critical to them and how they utilize the network daily. Gaining access to job aids detailing users' routines can provide helpful insights too. If possible, you should get copies of these job aids.
	
	- Consider goals, needs, and employee feedback, like a detective, distinguish facts from opinions. Understanding current network limitations and future requirements is crucial. Utilization and performance reports, historical trends, and even a traffic flow analysis can provide valuable insights for your proposal. If the client uses Juniper products, you can utilize them for network analysis. Junos devices offer troubleshooting tools like 'traceoptions' for logs and packet capturing. The data collected can be sent to Security Information and Event Management (SIEM) servers, such as Juniper Secure Analytics (JSA), which collects and parses events and flows, identifying threats and assets. JSA also supports a variety of third-party devices likely present in the client's network.
	
- [Identifying Applications]: Understand what applications are used. Record these applications in a spreadsheet or a table to understand their use and planned future use, also prioritizing traffic based on importance. This is particularly vital for bandwidth-hungry applications.
	
- [Understanding Scope]: When assessing the company's infrastructure, you must grasp the full scope of the design project. Even if the network initially seems small, it can grow significantly. Your design should foresee any capacity changes. And designing with modularity can help accommodate any network requested by the customer.
	![[Pasted image 20250511211403.png]]
- [Validating the Data]: The process of collecting, deciphering data until you understand the client's needs, a team consultation is also required.
	![[Pasted image 20250511211720.png]]
- [Analyzing the Existing Environment]: Design projects that usually new/existing systems, the main goal is to considering all the data analysis factors.
	
	- [Brownfield Projects]: Design projects that usually involve upgrades to existing systems. This is common due to factors like timing, training, and cost. If a customer's network is designed modularly, new requests can be added with minimal disruption.
		
	- [Greenfield Projects]: Design a network from scratch. These projects have fewer constraints, yet you can face challenges like infrastructural limitations or cost-prohibitive wiring.
	
- [Identifying Resources]: Include an equipment list or the Bill of Materials (BOM) detailing the components needed for the network design. For complex designs, BOMs may be modular or multi-level, associating costs with design functionalities.
	
	- Ideally, you want the customer to specify the budget. Understand it as you develop your proposal; aim to match the customer's needs and budget. Keep in mind the budget might change, necessitating constant communication with the customer. Consider other costs like staffing, testing, training, and potential changes in job roles. Communicate these possibilities to the customer for further instructions.

<h2 style="color:#6290C3"><center> Organizing Data </center></h2>
## Processing Data and Requests

- Process of planning the initial design.
	![[Pasted image 20250516234507.png]]
	- The data falls into three main categories: customer information, requirements, and project boundaries.
	
- Six main categories that are often vital areas, like functional sections and user groups.
	![[Pasted image 20250516234654.png]]
- Security Requirements
	![[Pasted image 20250516234933.png]]
	- [Network Access Control]: Juniper Identity Management Service (JIMS) or Integrated Firewall.
		
	- [Management]: Security Director or Security Cloud Director.
		
	- [Compliance]: JSA product which is a SIEM device.
		
	- [Bring your own]: Mist Wireless with Wifi Assurance.
	
- Availability Requirements:
	![[Pasted image 20250516235246.png]]
	- [Archival and Backup]: Security Director, Apstra, PyEZ scripts.
		 
	- [Resiliency]: JTAC.
		
	- [Failover]: SRX if its about security, EVPN/VXLAN with IP fabrics if it is for data center.
		
	- [Capacity]: More devices (scaling).
	
- Scalability Requirements:
	![[Pasted image 20250516235629.png]]
	- [User Base]: All about future growth. Modularity is the key. Some sort of network pod is recommended.
		
	- [Applications]: Vague, requires more information. Sometimes over-sized devices are the key to make sure the network can handle the next generation of bandwidth-hungry apps.
		
	- [Hardware]: Vague, requires more information. Modularity is the key.
		
	- [Performance]: Providing scaling numbers, or improving latency, such as using edge-routed bridging instead of centrally-routed bridging in a data center.
	
- Manageability Requirements:
	![[Pasted image 20250519090458.png]]
	- [Monitoring]: Paragon or JSA.
		
	- [Automation]: Automate with ZTP or other on-box or off-box scripting, maybe Security Director.
		
	- [Configuration]: Mist, or Security Director, or Apstra for managing configuration. This could also be about archiving configuration.
		
	- [Auditing]: Event logs, syslog, or administrative logs. These messages can all be sent to a centralized location, such as JSA or Security Director.
	
- Performance Requirements:
	![[Pasted image 20250519091038.png]]
	- [Bandwidth]: SSR device with SD-WAN, but most products support high bandwidth capacity.
		
	- [Latency]: Most Juniper products solves this problem.
		
	- [Quality of Service]: All Juniper devices support QOS with class-of-service feature such as DSCP, MPLS EXP.
		
	- [Optimization]: Offer a design that uses EVPN/VXLAN with IP Fabrics.
## Boundaries and Scope of the Design Proposal

- A step in organizing data is recognizing existing boundaries, that is, factors in customer requirements that may limit or change your design. Some of the common boundaries include things like:
	![[Pasted image 20250519091634.png]]
	- Defining the current and future user groups, their applications, data flows, and types.
		
	- Pinpointing the necessary parts of the network like campus, WAN, remote office locations, and data centers.
		
	- Documenting the current environment, if there is one, to know what to keep or change.
		
	- Factoring budget constraint. It doesn't do much good to pitch a design that is completely out of budget.
		
	- Recognizing unknown boundaries. These may involve hidden employees agendas, unidentified governmental laws, or limitations on existing physical media. Maybe something like running additional Ethernet cables in an old building doesn't make sense, wireless maybe the better options.
	
- Greenfield vs Brownfield:
	
	- Designing in a greenfield, like painting on a blank canvas, allows a fresh, modular design. However, these are really rare, given most customers already have a network component. Even when expanding to a new branch or data center, there's usually an existing network at the main campus.
		
	- Brownfield deployments, on the other hand, are far more common. Unless you're dealing with a start-up with no network, you'll probably encounter an existing network. You'll need to consider all aspects of the existing environment, such as building design, existing physical media layout, devices from other vendors, and any proprietary protocols used.
	
- User Groups and Applications:
	![[Pasted image 20250519094455.png]]
	- Different user groups may impose restrictions on your design. Balancing security enforcement, accessibility, user-friendliness, and performance benchmarks is absolutely necessary.
	
- Data Flow:
	![[Pasted image 20250519094532.png]]
	- Security, speed, and simplicity are important as resources are accessed via WAN connections, affecting data flow.
		
	- Identify the network's communication types using flow analysis tools. Traffic patterns may include user-to-user, user-to-machine, and machine-to-machine communications. Recognizing these existing traffic patterns and estimating future data flow is absolutely key to a successful network design.
	
- Exceeding Known Boundaries:
	
	-  Strive for designs that not only meet customer needs but surpass their expectations. Highlight areas where Juniper can offer substantial benefits.
		
	- There could be multiple solutions fitting the customer's needs, often separated by cost. Offering several options, good, better, and best, keeps you competitive when customers are considering various vendors. If a customer finds your "good" solution affordable, they might find extra funding for the "best" option.
## Creating Design Proposal

- Keep your design simple, create the logical structure before the physical structure, consider security throughout the design process, understand the design boundaries and scope, remember that every choice has a trade-off, ensure that your proposal is clearly documented.
	
- [Keeps Thing Simple]: Avoid overly complex designs that could be hard to implement or even understand. Document your design clearly and simply. Even if you believe your design is the best, if it's hard to comprehend, the customer may view it as too complicated, time-consuming, and costly to implement.
	
	- Always prioritize modularity in your design. It provides a better network structure, facilitates troubleshooting, and supports future growth. Modularity offers a hierarchical structure to your design, with each "module" serving a specific function.
	
- [Logical Design before Physical Design]: Regardless of the complexity inherent in most projects, make it easy for the customer with a logical network diagram followed by a physical one, both of which are crucial to your documentation.
	![[Pasted image 20250519095425.png]]
	- Embrace a "top-down" design method when crafting your design. This approach, guided by the OSI model, begins with the client data, documented requirements, and recognized boundaries. As you traverse from the OSI model's top down, you'll identify protocols, stability needs, and the needed network devices and physical media. This top-down method is preferable due to its improved scalability and modularity, unlike the "bottom-up" approach, which tends to focus on temporary fixes and overlooks the customer's true needs.
	
- [Incorporating Security]: Always security.
	![[Pasted image 20250519100617.png]]
- [Choices and Trade-off]: There will always be trade-offs.
	![[Pasted image 20250519100841.png]]
- [Capacity Planning]: Formulate a discussion group. The group should have broad representation from the customer and should help figure out acceptable and unacceptable network uses.
	
	- Then, measure user behavior. Identify all user populations and their locations. Summarize major user groups and their applications.
		
	- Next, gauge application behavior. Identify performance-affecting applications, their servers, and client devices locations and performance. Use this to determine key performance constraints.
		
	- Establish a network baseline. Profile the network behavior using packet traces, transaction rates, event logs, and statistics. 
		
	- Then, make traffic Projections. Gather data from a stable network, including bandwidth utilization, packet type, protocol, packet and frame size distribution, and error rates.
		
	- Finally, summarize the input data for the design. Consider the budget, categorize of all sites, user populations, and key applications and their behavior.
	
- [Design Stage: Design Specification]: A solid network design proposal comes with great documentation. This serves as a reference for design modifications, as changes are inevitable throughout the design process. The documentation should cover finalized design choices, changes, and their reasons. Since the document will go from a draft state to a final state, you should include a change log to track these changes for future maintenance. This document guides the implementation of the network, so ensure it's concise and easy to read.

<h2 style="color:#6290C3"><center> Securing the Network </center></h2>
## Basics

- While an indispensable tool, the Internet also opens the door for attackers across the globe to target your network. It takes just one overlooked vulnerability for the bad guys to breach your defenses. As network professionals, our job doesn't stop at just guarding the entrance; we must secure every potential point of weakness, both incoming and outgoing.
	![[Pasted image 20250519102220.png]]
	- Keep in mind that threats donâ€™t only come from the outside; internal risks are equally critical. There's a saying that our networks are 'Crunchy on the outside, soft and chewy on the inside,' this means that despite tough external defenses, the insider threat remains a concern.
		
	- Today's network landscape is besieged by security threats: viruses, trojans, worms, and the actions of cybercriminals intent on theft of intellectual property. These can impact any part of our networks, from WAN to data centers. Beyond these, we're also facing sophisticated social engineering and phishing techniques, SQL injections, ransomware, and targeted phishing threats like spear-phishing.
	
- Think back to a time not so long ago when the boundaries of managed networks were distinct and well-defined. The simplicity of network security during that era might seem enviable now. We had a robust firewall standing guard at the perimeter, straightforward user management protocols dealing with credentials and permissions, and the standard deployment of antivirus software. All these security measures were within the realm of our internal resources.
	![[Pasted image 20250519102332.png]]
- Let's consider today's network landscape, which has evolved dramatically. We're now overseeing a huge amount of devices from VoIP phones and conferencing systems to smartphones and tablets. Moreover, the surge of unmanaged devices and the ubiquity of remote work through VPNs has further complicated our security framework.
	![[Pasted image 20250519102441.png]]
	- Some of the intensified risks we face are things like:
		
	- The convenience of remote access, which introduces additional security vulnerabilities.
		
	- The rise of wireless devices demands robust security protocols.
		
	- Enforcing a comprehensive antivirus policy is increasingly complex, particularly with mobile devices where user awareness can be low.
		
	- The integration of virtual servers opens up new security considerations.
		
	- External storage devices like USB sticks bring their own set of challenges for data protection.
		
	- Security, in this dynamic environment, requires vigilance and adaptability as risks continue to evolve.
	
- [Assessing Security in Network Design]: When planning on the design of a network, it's crucial to start with a thorough 'assessment' of the current network security status. This foundational step encompasses grasping the customer's specific needs, establishing the project's boundaries, and meticulously reviewing the data provided by the customer. Right from this early 'assess' stage, security must be at the forefront of our design considerations. It's imperative that we pinpoint and fully comprehend the essential security aspects before moving forward with the network design.
	![[Pasted image 20250519102710.png]]
## Security Appliances

- Network Security is foundational, built into every fabric of the network from the outset.
	![[Pasted image 20250519103129.png]]
- [SRX Solutions]: A highlight of Juniper's security portfolio, goes beyond traditional firewall capabilities. It's at the core of Juniper's Security Intelligence, scaling with the needs of the business, capable of handling over a million custom threat data entries, and focused on enforcing the most pertinent intelligence. This means Juniper's customers get prompt, accurate threat mitigation with minimal false positives, embodying the smart, proactive defense they need.
	![[Pasted image 20250519103505.png]]![[Pasted image 20250519103618.png]]
- [Juniper Security Director]: offering a robust platform for managing security functions. It's a modular, scalable, user-friendly solution that not only simplifies operations but also paves the way for new business opportunities through application development and hosting that enhance network services and automation.
	![[Pasted image 20250519103714.png]]
	- This platform stands out for making security policy management more accessible and precise, offering a comprehensive web interface that covers the full policy lifecycle. It's equipped with advanced features for application control, content security, IPS, NAT, and VPN management.
		
	- With Security Director, network admins gain broad policy control, enabling consistent and compliant security across multiple SRX devices. This results in a more reliable network security posture that's easier and less costly to manage, cutting down on errors and streamlining administrative tasks.
	
- [Software Defined Secure Network (SDSN)]: Offers a unified approach to cybersecurity. This platform centralizes and streamlines protection, allowing for dynamic policy and enforcement across the network treated as one cohesive domain.
	![[Pasted image 20250519103836.png]]
	- The SRX devices, in conjunction with Security Director and Juniper Advanced Threat Protection (ATP) Cloud, orchestrate a swift, effective defense mechanism against threats, leveraging real-time communication to deploy necessary policies quickly.
		
	- SDSN adapts to emerging threats through Security Director Insights, which directs potential malware to ATP Cloud's sandbox for analysis. Upon confirmation of malicious activity, SD Insights promptly updates network defenses, enabling firewalls and switches to counteract the threat immediately.
	
- [ATP Cloud]: A robust cloud-based security solution. It benefits from the cloud's scalability and a shared intelligence model, delivering up-to-the-minute threat intelligence to all users.
	
	- Seamless integration with SRX devices or Secure Edge to bolster firewall efficacy.
		
	- Defense against zero-day threats through a sophisticated toolkit designed to combat advanced and elusive threats.
		
	- Inbound and outbound traffic analysis with policy enhancements to halt malware, isolate compromised systems, and prevent both data leaks and internal threat spread.
		
	- Ensured service continuity thanks to its high availability.
		
	- Capability to scale in response to greater demand for computing power, network bandwidth, and increased storage for malware archives.
		
	- In-depth inspection, actionable insights, and proactive blocking of malicious activity within web and email vectors.
		
	- Encrypted Traffic Insights that allow for threat detection in encrypted traffic streams without needing to decrypt them.
	
- [Juniper Network Secure Analytics (JSA)]: Serves as a pivotal network security management tool, offering an unparalleled view of network activity. It allows businesses to streamline operations with a comprehensive, web-based interface. JSA simplifies various aspects of network security management, through things like:
	![[Pasted image 20250519104056.png]]
	- Targeted threat detection, ensuring timely analysis of pertinent security threats.
		
	- Advanced log management, enabling secure, scalable log storage ranging from GBs to TBs.
		
	- Efficient log retention, allowing for easy archiving or integration with existing storage systems for enduring log preservation and accessibility.
		
	- Tailored compliance reporting with the ability to generate and schedule reports from a library of over 1300 templates.
## WAN and Edge

- Modern Enterprises have Complex WAN Networks.
	![[Pasted image 20250519170120.png]]
	- It is difficult to balance security, performance, and cost considerations.
	
- [Trouble Shooting Branch Issues]: Finding the root cause can devolve into a complex log parsing exercise. Juniper Mist AI Assurance can detect the cause of each of these issues.
	
- [From Have Branch To Heavy Cloud]: It is no longer realistic to run all security services at the branch.
	![[Pasted image 20250519171343.png]]
- [Secure Access Service Edge]:  Represents a shift to a cloud-centric security architecture, tailored to the demands of modern enterprises. It transcends traditional product boundaries, focusing instead on a holistic security framework.
	![[Pasted image 20250519171551.png]]
	- Central to Juniper's vision of SASE are two principles: First, it brings security into the cloud, closer to where applications reside, integrating protection directly into the network. Second, it offers adaptive, secure access to users, assessing risks in real-time to ensure consistent security regardless of location.
		
	- In essence, Juniper's SASE isn't just a set of security tools; it's a strategic shift to a network design that's secure by default, flexible, and in tune with today's cloud-oriented business environment.
	
- Juniper's approach to SASE integrates Mist AI-driven SD-WAN for network management with Juniper Secure Edge for security. Together, they form a cohesive SASE framework. Mist AI oversees network device configuration and health, from access points to on-premises equipment such as SRX or SSR devices. Secure Edge basically ensures robust security measures are in place.
	![[Pasted image 20250519171625.png]]
	- The operational flow is streamlined via Security Director Cloud, which is where you craft and manage policies. This platform also provides a unified view of devices through its integration with Mist, ensuring a harmonized and efficient SASE deployment.
## Cloud Approach

- [Zero Trust Access]: The Gartner model for cloud security is built around the concept of zero-trust network access, ensuring secure connections for users anywhere to applications everywhere. This model prioritizes context, which at its core considers user identity, application identity, connection type, and location all fundamental to Zero Trust Access (ZTA).
	![[Pasted image 20250519171809.png]]
	- Zero Trust Network Access, a broader term, extends ZTA principles, securing not just user-to-application interactions but also user access to internal resources, applying the same context-based security measures.
		
	- A critical piece not yet touched upon is the growing complexity of user identity management within modern networks. The diversity of user roles, locations, and access levels means authentication surpasses basic yes/no criteria. Security policies now must be dynamic, reflecting user identity alongside their location and connection method. A user at a corporate site may face different security policies than one using public Wi-Fi at a cafe.
	
- [Secure Web Gateway]: A critical security asset, merging firewall and proxy capabilities to monitor and safeguard your network's web traffic. It executes deep packet inspection, shielding against viruses, malware, and phishing threats. It also includes URL and content filtering to shield users from harmful or unsuitable material. As an SSL proxy, it decrypts sessions for deeper application insights and conducts malware checks on files, enhancing application-specific QoS and filtering.
	
- [FWaaS (Firewall as a Service)]: Provides all features of next-generation firewall delivered as a cloud service.
	
	- Layer 7 security policy enforcement, IPS/IDP, IPsec VPNs, Deep Packet Inspection, Integration with Advanced Threat Prevention (ATP).
	
- [Cloud Access Security Broker]: A CASB Provides a merged point of security enforcement between enterprise users and cloud services.
	![[Pasted image 20250519203558.png]]
- [Data Loss Prevention]: A combination of tools and best practices to prevent exfiltration of sensitive data.
	
	- Detect and encrypts sensitive data, machine learning based user and platform risk evaluation.
		
	- Dedicated tool for regulatory compliance such as HIPAA (Health Insurance Portability and Accountability Act), GDPR (General Data Protection Regulation), PCI DSS (Payment Card Industry Data Security Standard), CCPA (California Consumer Privacy Act).
	
- [Juniper Secure Edge]: A comprehensive tool kit for securing a cloud-based enterprise, delivered through a single service framework.
	
	- Single policy framework for managing security policies for all users, centralized policy management; POPs provide security enforcement closest to the protected users and applications, comprehensive user-aware and application-aware policy enforcement.
	
- [Secure Edge Architecture]: 
	![[Pasted image 20250519204158.png]]

<h2 style="color:#6290C3"><center> Campus Design </center></h2>
## Components of the Campus Network

- Campus comes in different shapes and sizes that has all the buildings and floors connected to share data centers resources, which could be off or on campus. A campus can also connect to other campuses, the Internet, regional sites, or branches via LAN. 
	![[Pasted image 20250525215744.png]]
	- Modern campus has evolve from supporting traditional client/server traffic to managing real-time applications like VoIP, video conferencing, and other unified communications tools while handling increasing users and devices. 
	
- Campus Topologies:
	![[Pasted image 20250525220732.png]]
- [Legacy Three Tier Design]: Overly complex, inefficient, and also costly. The 3-tier design approach was utilized due to oversubscribed interfaces, requiring more devices and hence more maintenance and management.
	![[Pasted image 20250525221409.png]]
- [Consolidating Security]: Enhances efficiency by reducing latency and device connections. Fewer devices also decrease power, cooling, and space costs. Instead of security embedded in the network, consolidation embraces security virtualization on a minimal amount of devices, providing it as a network service.
	![[Pasted image 20250525221637.png]]
- [Collapsing Layers]: Using Virtual Chassis, you can link up to ten switches, forming a single logical entity managed like a single switch. Virtual Chassis cuts operational complexity by minimizing the amount of managed switches.
	![[Pasted image 20250527082534.png]]
	- Then, we condense the core and distribution layers, flattening the network. By removing a layer, we get performance enhancements. With fewer devices to manage, operations are simplified. Core and aggregation layer consolidation also cuts down on the number of uplinks, easing cabling needs. Again, fewer devices translate to lower capEx, power, space, and cooling.
	
- [Modern Campus Network]: Uses a three-tier hierarchical network design which is different from the legacy three-tier structure we previously examined. The advantage of this modern design is that we can replicate it across a large network as pods. And then, each pod can connect to form a bigger network. It's common in campus networks to connect individual hierarchical pods to a core. Changes in a pod usually remain confined to that pod rather than the entire network.
	![[Pasted image 20250527082657.png]]
- [Segmentation]: Segmenting traffic into different broadcast domains is essential for security. Many hacks occur because a public device shares network segments with devices with sensitive data. Basically, if there's a vulnerability with the public device that gets exploited, then the hackers have access to the sensitive devices.
	![[Pasted image 20250527082815.png]]
	- You can use VLANs to segment traffic functionally. However, this has some limitations, given a Layer 2 network only supports 4094 VLANs. Security-wise, firewalls may need to sit between traffic flows to enforce security policies, potentially complicating network management as the network expands.
## Practices and Considerations for Campus Design

- General guidelines to consider when designing campus networks:
	![[Pasted image 20250527083034.png]]
- Traditional Campus Network Limitations:
	![[Pasted image 20250527083106.png]]
- [EVPN-VXLAN]: An Ethernet VPN, is a Layer 2 overlay mechanism using an IP underlay. Virtual Extensible LAN, is a overlay solution that expands the Layer 2 network space from 4096 broadcast domains to 16 millions.
	
- Modern Design with EVPN-VXLAN:
	![[Pasted image 20250527083701.png]]
	- Extends down to the access tier, offering Layer 3 benefits while maintaining Layer 2 device connectivity.
		
	- Widely adopted, standards-based tech in data centers as it can be readily designed, deployed, and managed within enterprises.
		
	- Isn't limited to two devices like MC-LAGs. You get scalability by simply adding devices.
		
	- With its Layer 3 underlay, EVPN-VXLAN leverages faster convergence technologies like BGP and BFD and enables microsegmentation without proprietary solutions like PVLANs.
		
	- Group-based policy (GBP) is compatible with EVPN-VXLAN. GBP summarizes policies across the network, translating them to network devices. GBP's segmentation is beneficial on campuses for creating network access policies, which simplifies the design and implementation of network applications and device security policies.
	
- [Making the Design Modular]: Embedding modularity in your network design reduces the data each device processes and eases the burden of designing, deploying, managing, and troubleshooting the network. In a modular design, devices have distinct roles. It promotes scalability and other benefits within the campus environment. Ex:
	![[Pasted image 20250527084209.png]]
	- Access switches grouped in a virtual chassis in a specific wiring closet, on a floor, in a building, serving a user or device group. Another virtual chassis depicted services with a different user and device group in a different location. Since all virtual chassis devices in the access layer perform the same function, they can have a similar configuration, making this modular element repeatable and familiar to those managing the network. This approach is also applied to the core layer with individual chassis-based systems or virtual chassis deployments.
	
- [Security Through Isolation]: A typical method is to associate unauthorized users with a unique VLAN, often termed a guest VLAN. Along with separating authorized and unauthorized users at Layer 2 via unique VLANs, it's recommended to segregate them at Layer 3 using unique VRF instances. This isolation is usually implemented at the first Layer 3 device, ensuring traffic stays in that isolated VRF until reaching the device at the Internet edge.
	![[Pasted image 20250527084542.png]]
- [VLAN Connectivity]: Standardize the design of your VLANs, create a standard VLAN schema used on all access switches.
	![[Pasted image 20250527084857.png]]
- [Subnet Design]: Map your VLANs to designated subnets.
	![[Pasted image 20250527085113.png]]
- [Device Naming Conventions]: A standardized naming convention that outlines the device's role, function, and location simplifies understanding of the network structure and assists in troubleshooting.
	![[Pasted image 20250527085306.png]]
- [Access Control Design]: The 802.1X Extensible Authentication Protocol (EAP) is suitable for wired and wireless users with an 802.1X client. It can authenticate users with an external RADIUS or LDAP server, such as Microsoft Active Directory, and enable dynamic VLAN assignment based on user or group attributes.
	![[Pasted image 20250527085631.png]]
	- For devices that don't support 802.1X, such as some IP phones or legacy devices, MAC address auth can secure specific device traffic on a switch port. However, MAC auth can be very challenging to manage in large deployments.
		
	- Devices like IP phones support LLDP-MED, which is used for automatically assigning IP phones to a voice VLAN and providing location data. 
		
	- Finally, decide which ports require 802.1X authentication and which devices will use MAC authentication.
	
- [CoS in the Campus Network]: Class-of-service often becomes essential due to the merging of voice, video, and data networks and the need to differentiate applications and user types. It optimizes bandwidth use by guaranteeing it to certain users or applications, especially on busy links.
	
	- CoS decisions shouldn't rely solely on packet drops on interfaces but should also consider user quality of experience and specific service requirements. Factors like application timeouts, delays, or voice/video issues, like choppy transmissions or buffering streams, should also influence the decision.
	
- [Using the Top-Down Design Approach]: Knowing users, applications, traffic types, and traffic patterns can help determine the best network design. Identifying baseline traffic flows throughout the network and assessing an acceptable quality of experience level for each flow type will provide you an idea of how the physical network that support those flows should be designed.
	
- [Oversubscription Ratios]: Identify the ingress-to-egress link bandwidth in a north-to-south-direction in the network.
	![[Pasted image 20250527090633.png]]
## Architectural Design Options for the Campus

- Legacy Campus Architecture:
	![[Pasted image 20250527090852.png]]
- [Mist Campus]: Three EVPN-VXLAN architectures that Juniper suggests:
	![[Pasted image 20250527091112.png]]
	- EVPN Multihoming or collapsed core is the first recommended architecture. It combines standalone switches or VC in the access tier and merges core and distribution tiers. By utilizing EVPN Multihoming, STP is completely eliminated via uplink aggregation from the VCs to distribution switches. This design is ideal for small and medium campuses with less than 5000 users.
		
	- The second design, is the campus fabric core-distribution architecture. Here, a Layer 3 fabric exists between the core and distribution tiers. The access tier comprises standalone switches or VCs, while EVPN-VXLAN is used in distribution and core tiers. This is suitable for larger setups, like multi-building campuses or universities with 5,000 to 10,000 users.
		
	- The final recommended architecture is campus fabric IP Clos. Here, EVPN-VXLAN extends from the core to the access. The access tier can include standalone switches or VCs, participating in EVPN-VXLAN with Layer 2 and 3 gateways. This design, recommended for very large deployments, allows EVPN-VXLAN usage from access to distribution and core, ensuring quick convergence and mobility.
	
- [Validated Fabric Designs]: 
	![[Pasted image 20250527091539.png]]
	- The EVPN multi-homing design, especially when utilizing ESI-LAG, is a practical tool often adopted in small-to-medium campus settings. It efficiently handles inter-campus traffic in collapsed core/distribution configurations. Serving a critical role in network infrastructure. One of its strong points is that it effectively removes the need for STP, simplifying overall network management. Additionally, if you're already using Virtual Chassis or MC-LAG, you'll find the migration to EVPN multi-homing with ESI-LAG relatively straightforward and beneficial.
		
	- The Campus Fabric Core-Distribution design, utilizing Centrally-Routed Bridging (CRB), is a beneficial approach for managing networks in smaller to medium-sized campuses, especially when dealing with inter-campus traffic. A key advantage of this setup is its simplicity: your L2/L3 gateway happens solely at the core, streamlining your network operations. This design even accommodates distribution switches that aren't capable of handling an L3 VXLAN gateway, offering more flexibility for different network equipment. This design excels when the majority of your traffic is north-south traffic.
		
	- The Edge-Routed Bridging (ERB) method, as part of the Campus Fabric Core-Distribution design, is great for medium-sized campuses dealing with a lot of intra-campus traffic. ERB provides notable advantages, such as lessening the need for gateway re-learning and minimizing the blast radius, which makes network management more efficient. Plus, it improves multi-vendor interoperability, allowing you to integrate various network equipment more smoothly. This approach not only enhances your network's effectiveness but also promotes flexible and diverse technology use within your campus. This design excels when the majority of your traffic is east-west traffic.
		
	- With the Campus Fabric IP Clos design, the End-to-End VPN technology is a great option for medium to large campuses dealing with intra-campus traffic, especially when Layer 3 is at the access. This technology works well when it comes to managing mobility and IoT devices, because of its efficient access layer segmentation feature. It efficiently isolates different user groups or device types, ensuring enhanced security and optimal network performance. This makes it an excellent choice for modern campuses that prioritize secure, efficient, and innovative network management.
	
- A note about Nomenclature: Data centers use an alternative naming scheme.
	![[Pasted image 20250527091737.png]]

<h2 style="color:#6290C3"><center> Campus WAN Design </center></h2>
## Components of the Campus WAN

- A WAN is a network covering a broad area used to interconnect business locations and resources. A WAN is a key tool permitting businesses to function effectively.
	![[Pasted image 20250527092215.png]]
- Campus WAN connectivity functions:
	![[Pasted image 20250527092309.png]]
	- [Internet Edge]: Typically seen in campuses, branches, and data centers, the Internet edge function serves as a gateway for users and applications. Sometimes, this function is remotely hosted for branch offices, like in a WAN site or a data center. It allows corporate Internet access, Web application connectivity, DMZ-hosted services, remote work access, backup WAN connection for the branch office, and Internet.
		
	- [WAN Aggregation]: Usually located in a regional campus or data center, the WAN aggregation function links remote branches to the enterprise WAN, typically in a hub-and-spoke layout. This design allows for policy management, offering modularization for easier deployment and problem-solving.
		
	- [Private WAN]: Links all enterprise sites via WAN aggregation, basically forming a company-managed backbone for the network. This backbone, often a hub-and-spoke or even a full mesh setup, includes devices like routers, switches, and firewalls, mostly managed by corporate network personnel, not the service provider offering the circuits and connections.
		
	- [DCI Function (Data Center Interconnection)]: Links data centers together. This connection usually employs a standards-based Layer 2 or Layer 3 solution using MPLS, like Ethernet VPN Virtual Extensible LAN (EVPN/VXLAN). Reasons for multiple, often mirrored, data centers and their interconnection include things like disaster recover and business continuity, DC consolidation and virtualization, geo-clustering, and other Layer 2 extensions.
## Practices and Consideration for Campus WAN

- Campus WAN design goals should be easy to deploy, flexible and scalable, resilient and secure, easy to manage, and service ready.
	![[Pasted image 20250527092855.png]]
- The preferred WAN connectivity might not be feasible at all locations. You might have to propose an alternate method for these sites. Although some locations might need exceptions to standard products and solutions, aim to keep these to a minimum.
	
- WAN connectivity between branch locations and the WAN aggregation device can be classified as: Private WAN, public internet, and provider-managed MPLS services.
	![[Pasted image 20250527093324.png]]
	- The private WAN is maintained by the enterprise, and typically deployed across dedicated Ethernet fiber links, with the potential for multiple QoS classes for traffic prioritization.
		
	- The Public Internet is a widespread and low-cost business-class Internet, deployed via something like fiber or Metro Ethernet. And with this, since it's public, you need an IPsec VPN to secure and authenticate traffic.
		
	- A Provider-Managed MPLS Service is a private VPN service by a provider that can replace the need for IPsec VPNs. However, just because your traffic is not regular internet traffic, it is still not encrypted by default.
	
- [WAN Device Roles]: WAN aggregation's main role is to merge connections from multiple sites to a central site. It provides access to central sites or data center services. The aggregation hub can be at a regional office, data center, or a service provider central office for localized core transport termination. Three typical router roles in an aggregation hub: WAN aggregation, Internet gateway, and VPN termination.
	![[Pasted image 20250527093613.png]]
	- The WAN aggregation role is an internal role that doesn't typically have a direct Internet connection. It is the termination point for private leased lines and private Layer 3 and Layer 2 VPN services managed through an attached service provider. Services like Web caching are hosted here.
		
	- The Internet gateway role is an external role that peers with the public Internet. Remote enterprise locations reach the IPsec tunnel termination router via the Internet gateway router.
		
	- The IPsec termination role terminates IPsec tunnels from Internet-connected remote locations. It's recommended to place tunnel endpoints in an Internet-facing virtual-routing instance.
	
- [Need for Routing]: Regardless of the WAN connection type used, a need for routing exists between the enterprise locations. Traffic destined to enterprise resources typically passes through the WAN aggregation site. Traffic destined to external resources may or may not pass through the WAN aggregation site depending on the connection type.
	
- [Determining Throughput Requirements]: The number of users and devices as well as applications and their associated traffic flows determine throughput requirements. When figuring out the WAN bandwidth for WAN aggregation sites and data centers, also consider remote users' bandwidth needs. Also, customers might want spare ports for future needs, avoiding delays in purchasing and installing new devices.
	![[Pasted image 20250527103046.png]]
- [Performance Considerations]: The WAN speed and latency are often the main bottlenecks between sites in an enterprise network. Applications like voice, video, and cloud computing need low latency, typically under 100 milliseconds. The major sources of latency include WAN propagation delay, serialization delay, and encryption/decryption delays. A hub-and-spoke VPN design may be impractical if latency is high due to double encryption/decryption and multiple serialization delays.
	![[Pasted image 20250527103036.png]]
- [VPN Design Considerations]: Tunneling packets in IPsec increases packets size, this make additional overhead can exceed 36 bytes, must limit the size of the packets pre-encryption, enforced by limiting the MTU size of IPsec traffic.
	![[Pasted image 20250527103017.png]]
- [Need for Quality of Service]: Even with careful consideration and planning, you will likely encounter oversubscription in the network. A well-planned QoS implementation is necessary to manage voice, video, and data convergence and differentiate applications and user types. Guaranteeing bandwidth to specific users or applications optimizes the use of available bandwidth, especially on congested links.
	![[Pasted image 20250527103338.png]]
- [Need for Security]: Identify the untrusted domains and determine a plan to monitor manage, and mitigate all security risks.
	![[Pasted image 20250527103500.png]]
- [Using Virtual Routers]: Great as they provide traffic isolation. 
	
	- Several enterprise scenarios exist where using VRs is beneficial. Such as: Separate WAN and edge routing from LAN routing domains when multiple protocols are running; Isolating guest networks with separate WAN connections for Internet access; and Separate point-of-sale networks and routing over a specific VPN.
		
	- Some other scenarios include things like: Merging organizations; Multi-tenant buildings; High-security facilities; and University campuses with lots of departments.
## Design Options for Campus WAN

- [Active/Passive Design]: A single WAN aggregation router has one of two data center links, with link cost and route preference dictating the choice. The active/passive approach often fits when the secondary path offers lower performance due to link speed or less direct routing. In this instance, the secondary path through another aggregation router is less direct. Ideally, both WAN aggregation sites balance traffic from branch offices, and all transit traffic for the data center uses the local, more direct path.
	![[Pasted image 20250527103926.png]]
- [Active/Active Design]: A remote branch's WAN router maintains two active connections with distinctly different Layer 3 VPN providers. The branch router uses default routes to the PE routers, balancing traffic across both links.
	![[Pasted image 20250527103959.png]]
- [VPN Design Options]: 
	![[Pasted image 20250527104039.png]]
	- First, a 2-tier hub-and-spoke IPsec VPN design connects branch offices (spokes) to one or more WAN aggregation sites or data centers (hubs). Its simplicity comes from the few tunnels needed per branch. However, traffic between branches must route via a hub, potentially doubling latency. If you want to use this deployment option, you need to find out if this latency is acceptable, especially with voice, video, or other latency-sensitive applications. In an MPLS-VPN design, branches often have direct connectivity within the MPLS network.
		
	- Second, a 3-tier hub-and-spoke IPsec VPN design has branches connecting to regional WAN sites and data centers. Devices between regions route through regional hubs, possibly adding more latency. This design has similar considerations as the last one.
		
	- Third, a fully-meshed VPN design provides direct routes from each branch to others, and to the WAN sites and data centers. Though it minimizes hops and latency, it increases complexity and configuration size as tunnels grow with branch count. Due to this, many enterprises shift to provider-MPLS networks for fully-meshed branch connectivity. If used, a best practice is to limit VPN tunnels to come up on demand. Dynamic routing protocols like OSPF or BGP are preferable over static routing due to scalability challenges.

<h2 style="color:#6290C3"><center> SD-WAN Design </center></h2>
## Approach

- [Distributed Services vs Centralized Control]: Packet forwarding is an inherently distributed process (physically moving signals around the globe). Traditionally every router has a local control plane to make forwarding decisions. By delegating routing decisions to a central authority we are distributing the data plane, and centralizing control plane.
	
- [SD-WAN]: Software-Defined WAN, an automated, programmable WAN that dynamically an securely routes traffic based on application policies, network conditions, or WAN circuit priority. It centralizes the control of all routing devices in a network to a single controller. This gives the controller a full view of the network, allowing it to dynamically update the forwarding tables of all routing devices.
	![[Pasted image 20250602232331.png]]
	- One cool feature of some SD-WAN systems is application-specific forwarding decisions. Unlike traditional routers, which find this task pretty tough and time-consuming, SD-WAN makes it simple. This means we can pick the best paths based on what each application needs. As network conditions shift, application-based routing can adjust the forwarding tables almost instantly, keeping everything running smoothly.
	
	- Key concepts: 1st, SD-WAN creates an 'overlay' network. This means it works on top of your existing network infrastructure, making it smarter without changing the underlying 'underlay'. 2nd, There's something called a 'local breakout'. This is like an exit point at the edge of your network, where data can go directly to the internet. There's the 'central breakout'. 3rd, Imagine a hub-and-spoke system, where internet-bound traffic from various branches (spokes) travels through a central hub before heading out to the internet.
		
	- Benefits: 1st, it allows for multiple, secure, high-performance connections, which is a big step up from traditional MPLS networks. 2nd, it boosts performance by spreading traffic across various connections and adapting to changing network conditions. 3rd, network changes, like adding VPNs or firewalls, become much simpler and automated as we have zero-touch provisioning (ZTP). 4th, adding a Juniper Secure Edge integrates a secure access service edge (SASE) architecture, enhancing security with zero-trust authentication. 5th, the network becomes more secure overall, with encrypted traffic and segmented networks to contain any potential breaches.
	
- [Juniper Networks Session Smart Router]: Focus on stateful, session-aware routing. This means it chooses paths based on what each specific application needs.
	
	- This router is key to tunnel-free SD-WAN and comes packed with essential features as it ensures that active sessions don't lose data, even if there's a need to switch over to a backup path. It's always keeping an eye on performance, ensuring everything runs smoothly. It balances loads dynamically, so no single link gets overloaded. It optimizes the WAN for better performance. It provides Elastic Quality of Service (QoS) to prioritize and manage network traffic efficiently.
		
	- It stands out for its software-based design, which emphasizes openness and adaptability. This approach means it's not tied down to specific hardware as it's hardware-agnostic. So, what does that mean for you? It means you can deploy this router on a variety of platforms, giving you lots of flexibility.
		
	- Juniper Networks offers a specialized range of security appliances that come with the Session Smart Router software already installed. But the beauty of this router is that you're not limited to these devices. You can also run this software on generic hardware, commonly known as 'white boxes', or even integrate it as a virtualized network function (VNF). This versatility extends to different environments, too, as it works just as well in both private and public cloud settings.
	
- [Session Smart Router WAN Assurance Models]: Two models for Juniper Session Smart Routing and Mist AI.
	![[Pasted image 20250602233246.png]]
- [The Mist Predictive Analytics and Correlation Engine (PACE)]:  uses data science and machine learning to get a deep understanding of how users interact with the network. It focuses on   seven key metrics to ensure everything runs smoothly, that is: 
	
	- How quickly users can connect.
		
	- The speed of data transfer (throughput).
		
	- Network coverage quality.
		
	- Network capacity.
		
	- How well devices switch between access points.(roaming).
		
	- Rate of successful connections.
		
	- Health and performance of Access Points.
	
- [WAN Assurance SLEs]: Metrics that measure the performance and health of your WAN, helping you understand how your network is affecting user experience. These metrics, such as WAN Edge Health, WAN Link Health, and Application Health, provide insights into potential issues and guide troubleshooting.
	![[Pasted image 20250602233421.png]]
	- SLEs pinpoint the root cause of issues in the WAN that affect user communication.
		
	- They simplify operations and give a clearer view of user networking, leading to faster problem-solving.
		
	- They provide insights for optimizing user, device, and application performance in various locations.
		
	- They represent the most advanced AI for IT operations in SD-WAN.
		
	- You can use the dashboard or ask Marvis, "Why isn't Teams working?", to quickly diagnose problems.
	
- [BFD Telemetry]: This tool monitors jitter, loss, latency, and the Mean Opinion Score (MOS), which are essential for assessing your network's performance.
	![[Pasted image 20250602233954.png]]
- The combo of SLEs and Mist Marvis AI offers precise insights into your network, such as pinpointing a bad cable. It can detect other things like MTU mismatches or problems with a bad WAN uplink. These three examples are just the tip of the iceberg. SLEs and Mist Marvis AI can actually reveal many more insights, acting as a powerful tool for diagnosing and resolving network issues efficiently.
## Inter-site Connectivity

- In a traditional network setup, we usually see a three-tier structure: access, core, and distribution, all leading to a single firewall at the WAN edge. This setup is straightforward to manage when it comes to policy enforcement and control, but it hits a snag with scalability, especially with older MPLS connections. Expanding these connections can be both costly and logistically difficult. As remote sites often rely on private circuits to connect back to the main hub via MPLS and many remote offices lack Direct Internet Access. Also, MPLS connections can be quite expensive.
	![[Pasted image 20250602234123.png]]
- The network's edge has expanded beyond a single point to include multiple WAN edges. Plus, with the rise of remote work, many sites now need to accommodate remote workers. SD-WAN addresses these evolving needs by offering more flexibility and scalability in network management.
	
- Modern SD-WAN gives us a network where multiple branches connect to redundant data centers and hubs. These hubs support front-end applications like Office 365 cloud workloads. The network also uses both local and central breakouts for internet access, avoiding reliance on a single failure point at the hub.
	![[Pasted image 20250602234253.png]]
	- Distributed Enterprise is oriented around distribution and cloud. As it spans remote sites globally. Some sites function as data centers or hubs. It uses a hybrid cloud approach, combining private and public cloud services. The transition from MPLS relies on broadband. Workloads are increasingly moving from the data center to the public cloud.
	
- Juniper Mist AI WAN Assurance offers two types of SD-WAN: Session Smart Secure Vector Routing (SVR), and the more traditional SD-WAN routing over IPsec/GRE on the SRX. It's important to understand how each of these works.
	
	- The Session Smart Router is all about creating dynamic pathways directly to applications. On the other hand, the SRX focuses on directing traffic to specific destination zones, where the sequence of policies plays a crucial role. This difference is significant. The SRX operates on a set of rules to form filters and policies and always needs traffic steering to direct network traffic.
		
	- In contrast, the Session Smart Router simplifies things. It only requires traffic steering when the data is leaving the network. Plus, it's designed to use the most specific matches for routing, which means local traffic steering isn't needed. This makes the Session Smart Router a more straightforward and efficient option in many scenarios.
	
- [SRX Series]: The SRX Series Gateway stands out as a secure SD-WAN router, perfect for global enterprises with remote sites. It's a zone-based firewall designed for reliable, secure tunneling, using ordered policies for efficient traffic management in Mist environments.
	![[Pasted image 20250602234920.png]]
	- Key differences from the Session Smart Router include the SRX's use of the Juniper Junos operating system, handling various routing protocols like IPv4 or IPv6, OSPF, BGP, and multicast. For WAN Assurance, the SRX employs industry-standard IPsec tunnels.
		
	- The SRX is adept at automating ZTP and supports Python scripts for agile security operations. Managing the SRX involves handling multiple policies and filters for precise routing. Mist AI WAN Assurance simplifies this with an intent-driven model that automatically creates the necessary policies and filters.
	
	- Key features of the SRX Series Gateway include things like: Mist AI WAN Assurance for simplified operations and enhanced visibility. Secure SD-WAN that manages various network interfaces, including MPLS, broadband, and 4G LTE. Flexible WAN modules. Network Segmentation for customized security and management policies.
	
- When you set up a Juniper SRX with WAN Assurance, you're bringing together the power of Mist AI automation and Juniper's Secure SD-WAN solution. The SRX comes equipped with Junos-based streaming telemetry, providing in-depth insights into your gateway's health and detecting any anomalies. This feature thoroughly analyzes gateway metrics right down to the port level, covering aspects like CPU and memory usage, data transfer amounts, traffic utilization, and power consumption. Plus, Mist AI-driven WAN Assurance can record gateway events, from configuration tweaks to system alerts, and offers detailed views into WAN and IPsec utilization by comparing tunnel traffic volumes with local breakout traffic.
	![[Pasted image 20250602234853.png]]
- [SSR Series]: The Session Smart Router-centric approach allows for precise monitoring of network aspects, such as jitter, latency, and loss, even in specific applications like Microsoft Teams calls. If a link doesn't meet its SLA, sessions smoothly transition to a better path with minimal disruption, ensuring critical apps maintain connectivity.
	![[Pasted image 20250602235120.png]]
	- The Session Smart Router is great at zero-trust dynamic routing. It routes packets by assessing their origin and destination and communicates with other Session Smart Routers to determine the best next hops. This process includes BFD for path health checks and a metadata exchange to inform routing choices.
	
- [Session Smart WAN Assurance]: The Session Smart approach to WAN Assurance is centered on how the Session Smart Router dynamically identifies the best next steps for applications or traffic destinations. As a native router, it uses the most specific matches, which means it doesn't require local traffic steering, making things simpler and more efficient.
	![[Pasted image 20250602235419.png]]
	- This approach brings together all life-cycle automation and ZTP within a single, easy-to-use dashboard. Additionally, the Session Smart Router is specifically designed for SD-WAN, enhancing its capabilities. When managed and orchestrated through the Juniper Mist AI Cloud, the Session Smart Router transforms into a robust SD-WAN solution, offering streamlined WAN Assurance.
	
- [WAN Design]: Like assembling a Lego project. Each piece, or 'block', plays a crucial role in creating the final, functional structure.
	![[Pasted image 20250602235500.png]]
- [WAN Assurance Design]: These are crucial components that come together to ensure an efficient and reliable WAN. Understanding each element can give us a better grasp of how WAN assurance works.
	![[Pasted image 20250602235627.png]]
	- 1st. **Topology**: This is all about the structure of your network. It's the blueprint that shows how different parts of your network are connected. Think of it as a map that guides the flow of data.
		
	- 2nd. **Core Routing Integration**: This aspect deals with how your network's core routing functions are integrated. It's like the main highway of your network, ensuring smooth and efficient data travel from one point to another.
		
	- 3rd. **Steering**: This refers to the direction of network traffic. Steering is crucial in managing the flow of data, ensuring it takes the most efficient route to its destination, much like traffic lights and signs on roads.
		
	- 4th. **Connectivity**: This is the backbone of your network. It's about how everything in your network is connected, ensuring that all parts can communicate with each other effectively.
		
	- 5th. **Application Policy**: Think of this as the rules of the road for your network. Application policies govern how different applications should be treated on the network, ensuring priority for critical apps and efficient resource allocation.
		
	- 6th. **Applications**: Finally, the applications themselves are key highlights. They're the reason why the network exists in the first place â€“ to support various applications that users need to perform their tasks effectively.
		
	- By focusing on these design highlights, WAN assurance can provide a more reliable, efficient, and user-friendly network experience. Each component plays a vital role in ensuring the network performs at its best, catering to the specific needs of the users and the organization.
	
- Design Consideration Summary:
	![[Pasted image 20250603000015.png]]
	- 1st. **Topology**: This is the layout or the structural design of your network. It's like a blueprint that shows how different components of your network are connected and interact with each other. A well-planned topology is crucial for smooth data flow and network stability.
		
	- 2nd. **Data Center Affinity**: This refers to the relationship and connectivity between your network and the data centers it relies on. It's about ensuring that your network aligns well with the data centers, facilitating efficient access and data exchange.
		
	- 3rd. **Underlay Routing**: Think of this as the foundation of your network's routing structure. It's the basic network infrastructure over which your higher-level services and routing protocols operate. Getting this right is crucial for the overall performance of your network.
		
	- 4th. **Transport Optimization**: This aspect focuses on making the most out of your network's transport capabilities. It involves optimizing the way data is transferred across the network, ensuring that it's done in the most efficient and cost-effective manner.
		
	- 5th. **Application SLAs**: This is about defining and adhering to the service level agreements for various applications running on your network. It ensures that each application receives the necessary resources and priority to function optimally, according to the agreed standards.
		
	- By paying attention to these design considerations, you can create a network that not only performs well but also aligns perfectly with the needs and goals of your organization. Each of these elements plays a vital role in ensuring that the network is robust, efficient, and capable of supporting the demands placed upon it.
	
- [SD-WAN and SSE Comprise SASE]: Emphasizes the advantages of integrating an AI-driven SD-WAN with Juniper's Secure Services Edge, offering a suite of features that enhance network security and management.
	![[Pasted image 20250603000126.png]]
	- 1st. **Firewall as a Service**: This provides cloud-based firewall protection, ensuring robust security against external threats while being flexible and easy to manage.
		
	- 2nd. **Secure Web Gateway**: SWG acts as a security filter for internet traffic, safeguarding against harmful web content and ensuring safer web browsing.
		
	- 3rd. **Cloud Access Security Broker (CASB)**: It serves as an intermediary for secure and compliant interactions between network users and cloud services, enforcing security policies for cloud-based applications.
		
	- 4th. **Data Loss Prevention (DLP)**: It focuses on protecting sensitive data within the network, preventing unauthorized access or sharing, and maintaining data privacy and compliance.
		
	- 5th. **Zero Trust Network Access (ZTNA)**: ZTNA adopts a stringent verification approach for every user and device attempting network access, significantly reducing internal threats and data breaches.
		
	- Combining these features creates a more secure and efficient network environment, offering a comprehensive and adaptive security framework.
	
- [SD-WAN and Security Positioning]: Here are some designs
	![[Pasted image 20250603000306.png]]
	- 1st, SD-WAN. Here we have On-Box Security, where the Session Smart Router is used at branches and hubs, equipped with URL Filtering and IDP capabilities built-in. This setup provides essential security directly on the router, filtering harmful content and detecting threats effectively.
		
	- 2nd, SD-WAN + Advanced Security. Here we have security in the Data Center. This setup combines the Session Smart Router at branches and hubs with the SRX at the Data Center or Public Cloud. Managed by the customer, this setup enhances security, particularly for sensitive data in data centers or cloud environments.
		
	- 3rd, SD-WAN + Secure Service Edge (SSE). Here we have SSE Integration with SD-WAN. In this model, the Session Smart Router at branches and hubs is complemented by cloud-delivered SSE components like CASB, DLP, RBI, FWaaS, SWG, and ZTNA. Offering a comprehensive cloud-based security solution. It addresses various security aspects, from data protection to zero-trust network access.
		
	- Each setup offers a different level of security with SD-WAN, ranging from basic on-router security to advanced, cloud-based solutions, allowing you to choose the best fit for your network's security requirements.
	
- [NAT Traversal]: 
	![[Pasted image 20250603000459.png]]
	- Mist AI WAN Assurance operates on a hub-and-spoke model, which is a common structure for SD-WAN networks. In this setup, the spokes initiate traffic to the hubs to create connections. However, not every SD-WAN device connected to the Internet has a static public IPv4 address, which can be costly and sometimes hard to get. Hubs need known static public IPv4 addresses, so spokes know where to connect. Typically, an SD-WAN network has fewer hubs but many spokes. This setup helps reduce overall service costs since only a few static public IPv4 addresses are needed, and spokes can function behind NAT.
		
	- Carrier-grade NAT, often used in 5G and 4G mobile connections, may include multiple layers of NAT. For Mist AI NAT, this is important because it operates on a one-to-one basis, regardless of the source and destination ports. This means overriding the destination IP address and ensuring it exits through the correct interface. The same applies in reverse for incoming traffic, where anything coming from that address is mapped back to the source IP.
		
	- In the context of the WAN edge for enterprises, both on-premises and cloud providers have their established network edges. While a static public IPv4 address is ideal, Mist also supports deploying hubs behind a 1:1 NAT. In the WAN settings, you can use the `Override` option and input the public IP. This tells Mist to direct spokes to that IP address instead of the one listed in the IP address field.