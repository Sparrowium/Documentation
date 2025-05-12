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

