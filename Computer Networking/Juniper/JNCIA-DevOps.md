Associate Automation and DevOps
<h2 style="color:#6290C3"><center> Introduction to Juniper Platform Automation and NetDevOps </center></h2>
## Network Operations

- Modern applications are evolving and require the network to keep pace. To deploy applications at scale, network and service configuration must be automated. Applications running in virtualized environments, such as private, public, and hybrid clouds, require networking to be virtualized as well. Instead of deploying and managing physical hardware devices, software-based virtual switches, routers, and firewalls are used. Modern networks are also able to dynamically adjust and optimize traffic flow based on the analysis of network telemetry data.
	
- The primary reason for changing the traditional approach to networking comes from the fact that computer networks often exist as parts of larger projects, and must evolve in unison.
	
- [Waterfall Model]: A classical way to approach software development.
	![[Pasted image 20250605231317.png]]
	- The waterfall model works if you know your requirements very well at the beginning of the development process. When requirements change during the development process, and a need to develop new functionality arises, the waterfall model shows some weaknesses. It is not the most flexible development model and requires more time before new application functionalities can be deployed to production.
		
	- Additionally, the waterfall model takes into account that there is a significant interval of time between releases of software. Each new release contains a large volume of code changes because multiple features are typically released at the same time. This increases the probability of issues at deployment time.
## DevOps: Principle and Practice.

- DevOps is a combination of technologies, design concepts, mentalities, and ideals that enable high-performing IT teams to move quickly while maintaining stability.
	
	- DevOps aims to unite development, operations, and other teams in your organization to improve communication, collaboration, and integration. DevOps creates a tight loop between product release and feedback, with the ultimate goal of decreasing the time to market while increasing organizational performance and customer satisfaction.
		
	- Using DevOps, changes in functionality can happen frequently, and are moved to production quickly. Automation and orchestration play a critical role, and if errors are encountered, a system can be quickly rolled back to a known state.
	
- [DevOps Principle: The Three Way]: It's a culture, it consists of Flow, Feedback, Continuous Experimentation and Learning.
	![[Pasted image 20250605232007.png]]
	- Work flows from developers to operations. Feedback is returned to the development team, and adjustments are made. Continual experimentation and learning is a frequent, recurring process.
	
- [The First Way (Flow)]: In DevOps, the flow begins when a new software product, feature, or change is requested, and ends when the software, feature, or change is delivered to the customer. To improve process flow, all participants need to understand the production flow and how what they do affects others later on.
	![[Pasted image 20250605232519.png]]
	- Do not permit local improvements to degrade the process as a whole. Always seek to increase rate of flow, and avoid technical debt.
	
- [The Second Way (Feedback)]: The second way is feedback. Continuously gather feedback from each stage in the flow process. You utilize this feedback to know what is working, what is not, and what needs to improve. Collect feedback from developers, operations, customers, and anyone else who may have information that can help you improve the flow or quality of the product. You can collect feedback from people as well as from automated monitoring and measuring systems. Feedback is a primary method for identifying ways to shorten and improve the flow.
	![[Pasted image 20250605232911.png]]
	- Using feedback to shorten your process flow includes shortening the time it takes to collect and analyze feedback. The sooner you get feedback, the sooner you can integrate positive changes into the system.
	
- [The Third Way (Continuous Experimentation and Learning)]: Continuous focus on improvement includes, allocate time for process improvement, find fault with processes not people, reward risk-taking, introduce faults to stress-test the system.
	![[Pasted image 20250605233208.png]]
- [Continuous Integration (CI)]: is the practice of frequently committing code to a shared central repository and automating the build and test process of the code each time someone pushes new code into the repository. The goal of CI is to provide rapid feedback. If a defect is introduced into the code base, it should be identified and corrected as soon as possible. For CI to work, a version control system (VCS), such as Git, is used. Some additional tools that automatically perform tests on the code might also be required.
	![[Pasted image 20250605233435.png]]
	- A major aspect of CI is that developers routinely reintegrate the code with which they are working, back into the primary or main branch of code in the VCS. The longer a developer waits to integrate their code with the main branch, the more likely it is that there will be incompatibilities that slow the flow of production. Submitting code for integration at least once a day is recommended.
		
	- With continuous building and testing, the primary code is theoretically in a releasable state at any time. Quality, compliance, and security testing are performed at each step of the process. Reserving extra time for testing at the end of the process is unnecessary since testing occurs throughout the process.
	
- [Continuous Delivery and Continuous Deployment]: Are natural extensions of CI. These terms are often used to describe the DevOps model. The difference between the two is that Continuous Delivery makes sure that the code is ready to deploy at any time, while Continuous Deployment is a way to automate the code deployment. The most important aspect of Continuous Delivery and Continuous Deployment is that operations, security, and compliance teams are brought into the conversation much earlier than before. Being a part of the process early enables these teams to give valuable input and visualize the process from beginning to end.
## NetDevOps

- [NetDevOps]: Is the application of DevOps philosophies, principles, and behaviors to network operations (NetOps). DevOps principles counter the waterfall methodology, where extended planning, building, and testing cycles occur in long sequential stages. NetDevOps brings automation to the network resulting in increased speed, reduced cost, and a decrease in the number of configuration errors. Junos devices are completely programmable. Every capability baked into the Junos CLI is exposed to developers, making the platforms completely automatable.
	
	- Junos automation solutions support network engineers and operators to move at the rapid pace demanded by the DevOps community. Juniper Networks embraces various automation and orchestration tools, such as Ansible, Salt, and so on. Junos OS enables network engineers to use common NetDevOps tools for full orchestration of large-scale service deployments.
	
- [NetDevOps Cycle]: Reduces the time between design changes and production deployment. All network changes go through the same pipeline to ensure consistency. 
	![[Pasted image 20250605234212.png]]
- [Infrastructure as Code (IaC)]: This term is used both inside and outside of DevOps circles. IaC is a very popular method to manage cloud-based resources because it provides complete infrastructure lifecycle management. All infrastructure is managed and provisioned using code. This generally includes deploying new virtual servers, applications, and networking, and also terminating those resources when they are no longer needed.
	![[Pasted image 20250605234349.png]]
	- Using code, you can create a new virtual router, switch, firewall, or any other virtualized network function (VNF). You can then configure and monitor the virtual device using code, just as you would do for a physical device. Virtual devices are also easy to move and duplicate when needed. This makes it possible for your development, test, staging, and production environments to be identical. Juniper Networks® cSRX Container Firewall and Juniper Networks® vSRX Virtual Firewall are examples of virtual network devices.
	
- Depending on the size of your organization and the exact field of activity, DevOps principles can be implemented differently.
	![[Pasted image 20250605234655.png]]
	- [Site Reliability Engineering (SRE)]: The site reliability engineer implements DevOps for applications and platforms. Google's Site Reliability Engineering (SRE) started as a software engineer's way to manage repetitive tasks, and is now an extended set of principles, practices, and incentives, which helps to manage large and complicated services at scale. One can view SRE as a specific implementation of DevOps with some extensions. DevOps can also be thought of as a generalization of several core SRE principles to a wider range of use cases.
		
	- [Network Reliability Engineering (NRE)]: Can be thought of as a DevOps implementation for networking. It has its own specifics and yet, still uses many of the common DevOps ideas, approaches, and tools.
	
- NRE focuses on customer satisfaction and service availability. Networking is inseparable from connected systems and applications. NRE embraces failure to ensure the same error does not happen again, relies on proactive testing, and is a continuous journey.
	![[Pasted image 20250605234836.png]]
- DevOps enables quicker integration of new software, especially software upgrades and patches. It enables developers to deliver software in smaller portions using a faster cadence. The overall result of adapting DevOps practices is faster time to market for new functionality, and an overall increase in organizational performance, product quality, and security. The DevOps practice of maintaining identical development, testing, staging, and production environments creates confidence that the new software will deploy successfully.
	![[Pasted image 20250605234957.png]]

<h2 style="color:#6290C3"><center> Junos Automation </center></h2>
## Junos Automation APIs

- The main Junos processes responsible for automation are the management process `mgd` and the Juniper Extension Toolkit (JET) service process `jsd`. The `mgd` process handles automation requests received using the Junos XML API, Yet Another Next Generation (YANG) language, and Representational State Transfer (REST) APIs, as well as some SNMP functions.
	![[Pasted image 20250606225951.png]]
- Junos works well in development and operations (DevOps) environments for these reasons. Junos has a rich set of APIs. Junos uses transactional configuration updates (the Junos commit model). Junos configuration and operational data are based on a consistent XML data model, such as internal Data Definition Language (DDL) and Output Definition Language (ODL), YANG, and OpenConfig. Junos supports popular IT automation and configuration management systems such as Ansible, Salt, and Terraform. In addition to remote management through APIs, Junos supports on-box scripts and applications.
	
- [Junos Extensible Markup Language (XML) API]: Is an XML representation of Junos configuration statements and operational mode commands. The client applications use Junos XML Management Protocol, an XML-based protocol, to manage the configuration on Junos devices. Client applications request information and change the configuration on a switch, router, or security device by using the Junos XML management protocol and the Junos XML API to encode the request and send it to the Junos XML protocol server on the device. The Junos XML protocol server is integrated into the Junos OS. The Junos XML protocol server directs the request to the appropriate software modules within the device, encodes the response, and returns the result to the client application.
	
- The Junos XML API provides on-box automation (commit, operation, event, and SNMP scripts), as well as off-box automation using third-party automation tools. To retrieve data from the Junos XML API, off-box solutions must leverage a protocol to transmit XML documents. NETCONF is one protocol used for Junos off-box automation.
	![[Pasted image 20250606230509.png]]
- The `mgd` is the nexus of the Junos OS user interface. The `mgd` process is central to the NETCONF-based automation of Junos devices.
	
- [NETCONF]: Is an open, standards-based protocol (RFC 6241, Network Configuration Protocol [NETCONF]), and is used by multiple vendors. NETCONF contains mechanisms that provide full programmatic access to Junos devices. Using XML documents and remote procedure calls (RPCs), you can transport configuration data and operational commands to network devices. NETCONF has been Juniper Networks' automation protocol of choice for many years, and is supported on all Junos devices.
	![[Pasted image 20250606230943.png]]
	- It is the foundation upon which many Juniper automation technologies are built including, Junos PyEZ, YANG, and OpenConfig. In most cases, NETCONF uses SSH as the transport protocol, although RFC 6241 enables other options (for example, Transport Layer Security [TLS]).
	![[Pasted image 20250606231039.png]]
- [REST API]: Provides HTTP clients access to objects that correspond to unique URLs on a REST server. REST clients use HTTP methods, such as GET, PUT, and POST, and data in the request body to perform actions on the REST server. REST is considered stateless because no client context is stored on the REST server. All session state is maintained on the REST client.
	![[Pasted image 20250606231218.png]]
	- Each request from a REST client contains all the information necessary to process the request. You can access a REST API using any program or programming language capable of generating HTTP commands. Tools like Postman or cURL are commonly used for testing. For actual programming, libraries have been developed for many programming languages, like Python, that simplify the generation of REST API requests.
		
	- Junos provides a REST API on Juniper Networks® MX Series Universal Routers, Juniper Networks® PTX Series Routers, Juniper Networks® QFX Series Switches, and Juniper Networks® SRX Series Firewalls, including the Juniper Networks® vSRX Virtual Firewall. It exposes Junos configuration and operational mode capabilities to REST HTTP clients.
	![[Pasted image 20250606233408.png]]
- [JET]: Is an evolution of the Junos software development kit (SDK), that provides a modern and programmatic interface for developers of third-party Junos applications. Using JET, Junos devices can host one or more third-party applications, such as monitoring tools, a Git client, or even a X client that generates tweets when triggered by specific device events.
	
	- The JET applications interact with Junos OS through request-response and notification services over standard-based transport channels. JET contains tools that aid in programming the Junos control plane. The Junos control plane has always been programmable, but JET makes it easier and faster. Customers can use JET to create customized CLI commands and SNMP MIBs, instead of waiting for Juniper to add the functionality to Junos OS. The flexibility of JET broadens the ability of Junos to meet market demands for Juniper and customers.
	
- All communication generated using the CLI, NETCONF, and the REST API passes through the management (mgd) process. An additional automation process is available in Junos called the JET Service process (jsd). The jsd process aggregates the individual APIs belonging to the routing protocol process (rpd), the Firewall Filter Daemon (dfwd), and other Junos processes, and exposes those APIs with a consistent look and feel. It exposes the same APIs that Juniper programmers use for internal development and provides another set of APIs to use for automation. Remote procedure calls that utilize jsd are transported using the gRPC protocol instead of NETCONF.
	![[Pasted image 20250606233718.png]]
	- Some of the benefits of the JET APIs include faster commit times, improved device telemetry, and a wider range of possible languages available for automation.
	![[Pasted image 20250606233836.png]]
	- JET supports multiple programming languages for off-box application development. On-box JET applications can be developed in Python, C, or C++. If an application that you plan to develop has a dependency on C or C++ modules or the application needs to be signed, then you can use the JET virtual machine provided by Juniper to develop the application. As mentioned earlier, JET uses gRPC, an RPC framework, as a mechanism to provide the request and response service. The gRPC server is part of the j.sd process.
		
	- To keep up with the rapid configuration changes that automation systems can generate, JET applications can configure the ephemeral configuration database. The Ephemeral database can commit over 1,000 configuration changes per second. To reach this magnitude of commits per second, commits are not validated. This means that you need to ensure that the app is pushing a valid configuration.
## Junos Automation API Overview

- Junos OS enables you to customize the behavior of a device with commit, operation, event, and SNMP scripts that run on the Junos device. These scripts take XML input, process it, call the Junos functions specified in the script, and output the instructions to Junos. The type of input accepted and the information returned is different for each of the different script types.
	![[Pasted image 20250606234158.png]]
	- The programming languages used for Junos on-box scripting are Extensible Stylesheet Language Transformations (XSLT), Stylesheet Language Alternative Syntax (SLAX), and Python.
		
	- [XSLT]: Is a standards-based language for processing XML data. XSLT was developed by the World Wide Web Consortium (W3C).
		
	- [SLAX]: Is an open-source language that mimics the semantics of C and Perl languages. SLAX is a pre-processor that converts its SLAX syntax to XSLT. Therefore, scripts written in SLAX are executed the same way as scripts written in XSLT.
		
	- The Junos OS supports Python on-box scripting. This also includes support for the Junos PyEZ library on-box.
	
- On-box Junos Scripts: Types.
	![[Pasted image 20250606234316.png]]
- Junos PyEZ is a powerful open-source Python library that is easy to learn and use. It enables you to automate all aspects of Junos device management including configuration, monitoring, software upgrades, file system maintenance, and so on using Python.
	![[Pasted image 20250606234401.png]]
	- Junos PyEZ enables you to retrieve or upload the device configuration in several formats, including text, XML, JavaScript Object Notation (JSON), or Junos set commands. It parses all XML remote procedure call (RPC) outputs automatically. Multiple utilities are also included to help with maintenance tasks.
	
- Automation management systems, also known as IT automation platforms or configuration management systems, refer to software used in DevOps environments. Junos integrates with some of the most widely used automation management systems in the industry, including Ansible and Salt. An automation management system provides multiple benefits: 
	
	- Manages hundreds or thousands of devices.
		
	- Enables you to take a declarative approach to configuring your network. You define the desired final state of the system, and the automation management system performs the low-level configuration.
		
	- Most automated management systems support some type of configuration templating. The automated management system renders the templates to create the actual configuration that is uploaded to managed devices.
		
	- Operations like software upgrades, file uploads, file downloads, and so on, are also typically available.
		
	- Platforms such as Salt enable you to react to events, and take actions based on the event type and severity.
		
	- Note that all automation management systems use the Junos XML API and Network Configuration Protocol (NETCONF) over SSH to manage Junos devices.
	
- [Ansible]: Is an automation platform that makes deploying and managing Junos devices easy. Ansible enables you to avoid writing complex scripts or custom code. Instead, Ansible enables you to automate using simple to understand YAML Ain't Markup Language files. Another Ansible advantage is that no agent is required on the managed devices.
	![[Pasted image 20250606234811.png]]
	- Ansible can perform operational and configuration tasks on devices running Junos OS, including, installing and upgrading Junos OS, deploying devices in the network, loading configuration, retrieving information, and resetting, rebooting, or shutting down managed devices.
	
- [Salt]: Is a powerful configuration management platform that was created and maintained by the SaltStack company. It was purchased by VMware in 2020. Salt enables you to define the desired state of a system and enforce that state on managed devices. You can also use Salt to execute commands on remote devices. It is Python-based and utilizes a Salt Proxy minion to connect to Junos devices.
	![[Pasted image 20250606234940.png]]
	- The Salt Proxy minion supports the ability to gather facts from Junos devices, manage and commit configurations, execute RPCs and CLI commands, install software, and copy files. Salt is event-driven and popular for use with Junos platforms because of its ability to perform event-driven closed loop automation.
	
- [Junos Snapshot Administrator in Python (JSNAPy)]: Captures and audits runtime environments of network devices running Junos OS. It automates network state verification by capturing and validating the status of a device. It takes pre-modification and post-modification snapshots and compares them based on provided test cases. JSNAPy can also be used to audit the runtime environment of a device against pre-defined criteria. JSNAPy is an open-source project, and the source code is available on the GitHub website.
	![[Pasted image 20250606235056.png]]
- [Zero-Touch provisioning (ZTP)]: Enables you to setup new devices in your network without manual intervention. When you connect a device to the network and boot it with a default configuration, it attempts to upgrade the Junos OS software and load a pre-existing configuration file from the network. The device uses information that you configure on a Dynamic Host Configuration Protocol (DHCP) server to determine whether to perform these actions and to locate the necessary software image and configuration files on the network. If you do not configure the DHCP server to provide this information, the switch boots with the pre-installed software and default configuration.
	![[Pasted image 20250606235151.png]]

