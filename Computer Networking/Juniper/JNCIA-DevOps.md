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

<h2 style="color:#6290C3"><center> XML and XPath </center></h2>
## XML Document Format

- [XML]: A standards-based way of structuring and communicating data. It was developed by the World Wide Web Consortium also known as W3C.
	![[Pasted image 20250611225441.png]]
	- XML appears similar to HTML because it uses tags in a similar fashion. XML is a language that is used to define a collection of markers known as tags.
		
	- These tags are applied to a data set or a document to define the function of individual elements and codify the hierarchical relationships between them. An XML document has three elements—tag elements, attributes, and namespaces.
	
- [XML Tags]:XML has three types of tags: opening tags, closing tags, and empty tags. XML tags are enclosed in angle brackets and are case-sensitive. XML appears similar to HTML because it uses tags in a similar fashion. XML documents are strictly hierarchical, so opening and closing tags showing the start and end of the data to which an XML tag applies must always be present. In HTML, there are exceptions to hierarchical statements.
	![[Pasted image 20250611230554.png]]
	- A tag element refers to a three-part set: opening tag, data, and closing tag. The data can be an alphanumeric character string. Here, is the XML data representing the course name between opening and closing tags. The text node is the formal identification of the XML data, whereas the element node includes the tags.
		
	- In some cases, there is no data to place between the opening and closing tags for a particular level in an XML hierarchy.
	
- [XML Hierarchy]: Just like HTML.
	![[Pasted image 20250611230635.png]]
- [XML Attribute]: XML elements can contain associated properties as attributes, that specify additional information about an element. Attributes appear in the opening tag of an element and consist of the attribute name and value pair.
	![[Pasted image 20250611230805.png]]
	- The attribute syntax consists of the attribute name followed by an equal sign and then the attribute value enclosed in quotation marks. An XML element can have multiple attributes. Multiple attributes are separated by spaces and can appear in any order.
	
- [XML Namespace]: XML namespaces are used to guarantee uniqueness for element names and data values in an XML document. Before using a tag, attribute, or function, include the namespace Uniform Resource Identifier (URI) in the style sheet declaration. Since the URI is often lengthy, a short prefix is mapped to the URI. The example shows an XML document namespace defined using the xmlns attribute for the URI "[http://xml.example.com/CBT](http://xml.example.com/CBT)".
	![[Pasted image 20250611230953.png]]
	- It is recommended that you define a unique document namespace because XML document data is frequently collected and merged into larger data sets and applications. Each document's unique namespace greatly reduces the probability of an element name or element value collision when the data is merged. In the example XML document, the `<course>` element node and all nodes that are within the `<course>` element node share the same namespace.
		
	- XML support more than one namespace, any elements that does not explicitly include the namespace prefix, uses the default namespace.
	![[Pasted image 20250611231223.png]]
- [XML schema definition (XSD)]: A file that ensures that everyone working with an XML document uses a standard set of tags to communicate the information. The XSD is what makes the XML document meaningful. XSD, like XML, is a standard developed by World Wide Web Consortium (W3C). XSD documents are themselves XML documents using a specific structure defined in the W3C standard.
	![[Pasted image 20250611231355.png]]![[Pasted image 20250611231412.png]]
## XML in Junos OS

- When you enter an operational mode command in Junos CLI, the CLI converts the command into XML format for processing. After processing the command, Junos OS returns the output in an XML document, which the CLI converts back into a readable format for display. XML encoding enables remote Junos automation apps to handle operations and configurations. The Junos XML API has XML equivalents for all Junos OS configuration statements and most operational mode commands. Each operational mode command with a Junos XML counterpart maps to a request tag element, and if necessary, a response tag element.
	![[Pasted image 20250611231719.png]]![[Pasted image 20250611231736.png]]
- Junos OS CLI commands query Junos OS infrastructure using XML.
	![[Pasted image 20250611231833.png]]
	- Then Junos XML API responds to CLI queries with XML document and converts the XML response to CLI output.
	![[Pasted image 20250611231956.png]]
- Pipe `display XML` to view in XML.
	![[Pasted image 20250611232107.png]]![[Pasted image 20250611232128.png]]
- - Juniper publishes XML schema definition (XSD) documents for every Junos software release. Download archived XSD files from the Junos OS XML API download site
    
    - XML schema for configuration data. Retrievable from a Junos OS device using Network Configuration Protocol (NETCONF) or available as a free download `config-24.2.xsd`
        
    - XML schema for operational data `operational-command-24.2.xsd`
    
- Junos OS CLI output can show which XSD version to use.
	![[Pasted image 20250611232501.png]]
## Navigating XML using XPath

- The Junos on-box scripts, such as commit, op, event, and SNMP, can be written in Extensible Stylesheet Language Transformations (XSLT), which is a standard for processing XML data. On a Junos device, XSLT performs XML-to-XML transformations, turning one XML hierarchy into another. The XSLT engine reads a script and an XML document. It uses the instructions in the script to process the XML document by traversing the document's hierarchy. Usually, the script shows what portion of the XML document tree to be traversed, how it should be inspected, and what XML should be generated at each point. For Junos on-box scripts, the XSLT engine is a function of the Junos OS management process.
	![[Pasted image 20250611232652.png]]
	- XSLT uses the XPath standard to specify and locate elements in the input document's XML hierarchy. XPath enables you to define complex criteria for selecting certain portions of the XML input document.
	
-  [XPath]: Is a standard way to identify and locate elements in an XML document. XPath's expression syntax enables you to define complex matching criteria for elements in an XML document. XPath views different parts of an XML document as nodes. The XPath node types are document nodes, element nodes, text nodes, and attribute nodes. Extensible Stylesheet Language Transformations, Stylesheet Language Alternative Syntax (SLAX), Python, and other automation programming languages that interact with Junos OS using XML use XPath.
	![[Pasted image 20250611232924.png]]
	- Because XML is applied in a wide range of use cases, XML defines a document object model (DOM) to ensure XML documents are parsed consistently. Different parts of an XML document are represented as nodes.
	
- [The XML Path Languages Path]: All elements within the document hierarchy are treated as nodes in XPath. Nodes are considered to be arranged in specific axes.
	![[Pasted image 20250611233142.png]]
	- An ancestor axis points from a node up through its series of parent nodes. A sibling relationship means that two elements have the same parent. A child axis points down the list of an element node's direct child nodes. The descendant axis contains all the descendants of a node. The attribute axis points through the list of an element node's set of attributes.
		
	- Each XPath expression is evaluated from a particular node, which is referred to as the context node (or simply context). A context node is the node at which the language processor is currently focused. Languages like XSLT change context as a document hierarchy is traversed, and XPath expressions are evaluated from that context node.
		
	- XPath supports standard logical operators, comparison operators, and numerical operators.
	
- [Element Node]: An XML element node comprises matching opening and closing tags and any data appearing between those tags. An element node may contain additional nested data including additional elements. Element nodes can be nested multiple levels deep. An XML document can only contain one root element.
	![[Pasted image 20250611233328.png]]
- [XPath Path]: The XPath expression provides two types of syntax—path syntax and predicate syntax. The XPath uses path expressions to select nodes in an XML document and specifies which node to inspect in the document hierarchy. The examples show different XPath expressions used to inspect a node. For example, the configuration is the root element in the document. When you specify `configuration`, it specifies all the nodes with "`configuration`". Similarly, when you specify `configuration/system`, it selects system elements that are children of the configuration element. However, it does not pick system elements under other hierarchies, for example, a system element `under/configuration/groups`. To specify all system elements anywhere in the hierarchy, you can use `//system`.
	![[Pasted image 20250611233626.png]]
	- You can also use XPath expressions path syntax. You can refer the current node by using the `/` notation. You can refer the parent node by using `../` notation. You can refer an attribute by using `@` notation.
	
- [XPath Predicate]: The XPath predicate syntax performs test at each node selected by the path syntax. Predicate syntax is used to match a specific node or node that has a specific value. Only nodes that pass the test are included in the result set. The example shows XPath predicate expressions. A predicate appears inside a square bracket ( [ ] ) after a path node.
	![[Pasted image 20250611233759.png]]
- [Node Preferences]: XPath syntax specifies which nodes to inspect in terms of their path locations on one of the axes in the document's hierarchy. You identify the XML node to access by specifying each level of the nodes' location in the XML hierarchy separating each hierarchy level using a forward slash. The method is similar to the way you specify the path to a specific file system directory on a UNIX host.
	![[Pasted image 20250611234007.png]]
- [Adding Selection Criteria]: The XPath predicate syntax allows you to perform tests for each node selected by the XPath path syntax. Only nodes that pass the test are included in a result set. A predicate appears inside square brackets following a path node.
	![[Pasted image 20250611234129.png]]
- [Elements vs Attributes]: Attribute are key identifiers in elements.
	![[Pasted image 20250611234256.png]]
- There are two important XML attributes that are commonly used in commit scripts to validate configuration changes before they are applied. Commit scripts are processed during a device commit operation. The candidate configuration in the XML format is used by a commit script as input. 
	![[Pasted image 20250611234607.png]]
	- In the XML candidate configuration, the `junos:changed` attribute is attached to element nodes that have changed compared to current active configuration. 
		
	- The `junos:group` attribute is attached to nodes that have inherited configuration settings from a configuration group.

<h2 style="color:#6290C3"><center> XML and NETCONF </center></h2>
## NECONF

- [NETCONF]: A standards-based protocol used for communication with network devices. Communication is usually SSH. With NETCONF you can perform action like locking, reading, modifying, deleting, and unlocking devices.
	![[Pasted image 20250624233626.png]]
- [Message Layer]: Provides a simple, transport-independent framing mechanism for encoding RPCs and notifications.
	![[Pasted image 20250624233737.png]]
	- The `<rpc>` element encapsulates all RPCs sent to a NETCONF server. The `<rpc-reply>` element encapsulates all RPC replies from a NETCONF server including returned data and any OK, error, or warning messages. The `<notification>` element is a one-way message sent asynchronously to NETCONF clients that initiates a `<create-subscription>` RPC to the NETCONF server.
	
- [Operations Layer]: Defines commands used to perform operations on a network device. These Operations layer commands are encapsulated within one of the Messages layer tags
	![[Pasted image 20250624234219.png]]
	- The different Operations layer commands are as follows: `<lock>`, which obtains a lock on a device configuration file before modifying it. `<unlock>`, which unlocks a configuration after modifying it. `<get>`, which retrieves data from the running configuration database or device statistics. `<get-config>`, which retrieves the configuration from a device. `<edit-config>`, which modifies device configuration. `<copy-config>`, which creates or replaces an entire configuration. `<commit>`, which commits a candidate configuration. `<discard-changes>`, which is used to roll back a candidate configuration to the current running configuration. `<delete-config>`, which deletes a device configuration file. `<validate>`, which ensures that the device can load the specified configuration. `<create-subscription>`, which creates a NETCONF subscription for notifications. `<close-session>`, which gracefully closes a NETCONF session. `<kill-session>`, which closes a NETCONF session other than the one you are currently using.
	
- [Content Layer]: Is where specific RPC parameters are encapsulated and sent to a NETCONF server. The XML API provided by the Junos `mgd` process on the server accepts and processes the incoming RPCs and generates an RPC response that is returned to the client.
	
- To enable NETCONF service (to use default port 830) over SSH as the Transport layer protocol on a Junos device, issue the set `system services netconf ssh` configuration mode command.
	
	- You can also configure a specific port number for NETCONF-over-SSH sessions. Use the `set system services netconf ssh port port-number` statement and replace the port-number with a desired port number you want to configure. You may choose any port number ranging from 1 through 65535, however avoid configuring access on a port that is normally assigned for another service. Once you configure the port other than the default port 830, the configured port accepts only NETCONF-over-SSH sessions and rejects regular SSH session requests.
		
	- To enable both NETCONF and SSH sessions, include SSH statement such as `set system services ssh`. The statement enables SSH access to device for all users and applications.
## Junos RPCs

- Type `netconf` to start a session in the Junos CLI.
	![[Pasted image 20250624234913.png]]![[Pasted image 20250624235007.png]]
- To establish a NETCONF session and execute commands, you issue NETCONF RPCs (Remote Procedure Calls) that perform operational mode commands and modify device configurations. All NETCONF RPC requests must be enclosed within XML `<rpc>` tags and terminate with the `]]>]]>` delimiter to mark the end of the message.
	![[Pasted image 20250624235130.png]]
- Pipe `| display xml rpc` Junos CLI command option provides insight into the appropriate Remote Procedure Call (RPC) for a given operation, but it should not be considered the definitive reference. The authoritative sources for RPC specifications are the Junos XML Schema Definition (XSD) files, which are included with each new release of the Junos OS. These XSD files contain the official schema definitions and serve as the primary reference for NETCONF RPCs in Junos.
	![[Pasted image 20250624235311.png]]
## Junos XML API Programming Languages

- [XSLT]: The basic model consists of an XSLT engine or processor that accepts as input a script or stylesheet and an XML document. The XSLT engine uses the instructions in the script to process the XML document’s hierarchy. The script identifies interesting portions of the XML document, how it should be inspected, and what XML output should be generated. Because XSLT was created to support generic XML-to-XML transformations, it is a natural choice for both inspecting Junos configuration syntax and for generating errors and warnings.
	![[Pasted image 20250624235644.png]]![[Pasted image 20250624235709.png]]
- [SLAX]: A programming language developed by Juniper Engineers to simplify the automation of Junos. It is now an open-source language. Unlike XSLT, SLAX is easier to use while maintaining the same capabilities. You can convert between SLAX and XSLT, as SLAX code is ultimately translated into XSLT before being processed by the XSLT engine. Programmers who are unfamiliar with XSLT often prefer SLAX because it allows them to focus on their programming tasks without needing to learn XSLT's complex syntax.
	![[Pasted image 20250624235832.png]]![[Pasted image 20250624235850.png]]

<h2 style="color:#6290C3"><center> Python Fundamentals </center></h2>
## Python Basics

- This flow chart demonstrates the actions that are taken when a Python script or program is executed. When the Python code is executed, the Python interpreter analyzes the program or script. If there are no syntax issues, the interpreter begins to translate the Python code into a byte code. In some scenarios, the Python code is translated and stored as a Python byte code `.pyc` file.
	![[Pasted image 20250625233155.png]]
	- Storing Python modules and packages in this manner speeds up execution because the interpreter doesn’t need to evaluate the Python code every time the module or package is referenced. Finally, the byte code is passed to the Python runtime, known as the Python virtual machine (pvm), that executes the byte code instructions.
	
## Python Modules, Packages, and Libraries

- [Module]: Is the smallest component of the package in the form of a Python script that comprises functions and methods to implement various features of the package. 
	
- [Package]: Consists of modules, resource file and is often developed using other packages to support various features. These supporting packages are called dependencies. 
	
- [Library]: Is a collection of packages. Libraries offer users a ready-to-use feature or a pre-written code so that no additional packages are needed. 
	
	- [Data Serialization Tools]: The Python libraries used for serializing and structuring data are JavaScript Object Notation (JSON), YAML parser and emitter for Python (PyYAML), and xmltodict. For example, you can parse JSON, YAML, or XML and convert it into a Python object.
		
	- [Configuration Management Tools]: Configuration management tool libraries enable you to automate network devices. You can configure, manage, and monitor devices as well as identify and troubleshoot network issues.
		
	- Libraries such as Ansible support multi-vendor devices and can quickly and easily retrieve network information to manage large networks. Network Automation and Programmability Abstraction Layer with Multi-vendor support (NAPALM) provides an API that enables users to write scripts and applications to interact with devices.
		
	- The other libraries useful for automating networks are Scapy for packet manipulation, Pycrypto for encryption algorithms and hash functions, and Requests for sending HTTP requests using Python.
		
	- Python libraries such as Network Configuration Protocol (NETCONF), Paramiko, and Netmiko SSH handling libraries that automate SSH connections to network devices. Juniper recommend these libraries for running remote shell commands or transferring files.
	
- [Framework]: Is the collection of libraries to build an application. An application is a final software product that performs certain tasks using Python codes, functions, and libraries.
	
- [Netmiko Libraries]: Netmiko is one of the most used Python libraries for network automation. The Paramiko library implements SSHv2 protocol. The Netmiko library is built on top of Paramiko. The functionality and implementation of Paramiko is based on OpenSSH. 
	
	- Even though Paramiko provides full implementation, such as connection protocols, user authentication, and secure file transfer protocol (SFTP), it runs as a solid service. But user authentication is provided using different applications running on a separate device or server. In such cases using Paramiko, you can establish an SSH session with the device; however, the device is not authenticated.
		
	- Netmiko provides multivendor support using the `netmiko.ConnectHandler` function. You can provide various parameters, such as device information, device IP address, username, key pair, and algorithm with the `ConnectHandler` function.
		
	- The Netmiko module for Juniper devices is `netmiko.juniper`. The `netmiko.juniper` module has four major classes namely `JuniperBase`, `JuniperFileTransfer`, `JuniperSSH`, and `JuniperTelnet`.
	![[Pasted image 20250626230803.png]]
	- Syntax for connecting via Netmiko:
	![[Pasted image 20250626230857.png]]
	- Syntax for displaying interfaces via Netmiko:
	![[Pasted image 20250626230954.png]]![[Pasted image 20250626231110.png]]
	- Syntax for Configuring Junos via Netmiko:
	![[Pasted image 20250626231240.png]]![[Pasted image 20250626231315.png]]![[Pasted image 20250626231316.png]]
	- Syntax for parsing XML in Netmiko:
	![[Pasted image 20250626231343.png]]![[Pasted image 20250626231400.png]]
- [PyEZ Libraries]: Junos PyEZ is a Python microframework used to manage and automate Junos platforms. A microframework is a package or library providing code that is useful for other larger applications.
	
	- Junos PyEZ is designed and maintained by Juniper to provide the same capabilities as the Junos CLI and to make automating and managing Junos devices using Python easy.
		
	- Common Modules: The `device` module provides the Python code capable of connecting to Junos platforms and printing device facts. The `utils` modules are Python utilities used to manage device configuration, securely copy files, perform file system operations, and install Junos software. The `command` and `op` module provides the predefined tables and views used to extract specific information from the operational mode output returned from devices. The `exception` modules provide Python exception handling capabilities.
	![[Pasted image 20250626231903.png]]
	- Common Submodules: The `config` module performs Junos device configuration operations. The `fs` module manages the Junos filesystem. The `scp` module securely transfers files such as software images and logs. The `ftp` module has capabilities similar to SCP using the FTP protocol. The `start_shell` module accesses the Junos device shell, and the `sw` module performs automated software upgrades.
	![[Pasted image 20250626232128.png]]
	- Syntax for installing `pip3 install junos-eznc`.
	![[Pasted image 20250626232238.png]]
- Python Script Examples:
	![[Pasted image 20250626232325.png]]![[Pasted image 20250626232341.png]]

<h2 style="color:#6290C3"><center> Querying Junos Devices Using Junos PyEZ </center></h2>

## Connecting Junos Devices Using Junos PyEZ

- Junos PyEZ connects to Junos platform using a serial console, Telnet, or NETCONF over SSH. It also supports SSH connections that are initiated by the Junos device.
	![[Pasted image 20250703100000.png]]
- Connecting to Junos devices requires authentication. When a Junos PyEZ script attempts to connect to a device to performs action, it must authenticate using an account with sufficient permission to perform action. Junos operating systems uses login classes to enforce administration privileges and permissions. The Junos built-in `super-user` class provides sufficient permission for PyEZ to performs all supported actions, a custom class is also supported.
	![[Pasted image 20250703100505.png]]
	- Remote management protocol are configured con Junos devices to enable remote PyEZ connections. By default, PyEZ connects using NETCONF over SSH on TCP port 830.
	![[Pasted image 20250703100642.png]]
- Junos device authenticates the user using the Junos PyEZ default method.
	![[Pasted image 20250703100844.png]]
- Connecting with the Python context manager `with/as` syntax open and close the device connection automatically. 
	![[Pasted image 20250703104923.png]]
- The most secure and convenient method to authenticate device connections is by using public keys. To authenticate using publics keys, a public/private key pair is generated on the management workstation. The public key is copied to the managed Junos devices and automatically used during Junos PyEZ device connection process to authenticate the connecting user.
	![[Pasted image 20250703105224.png]]
- Configure the authentication and authorization parameters for the Junos user account on all relevant devices. Make sure to configure `SSH-public-key-based` authentication by specifying the file path of the public key that is copied to the device.
	![[Pasted image 20250703110828.png]]![[Pasted image 20250703110830.png]]
- When using a `non-password-protected` key pairs, the connection automatically uses thee key pair associated with the logged in user for authentication. Since no key pair password is configured, authentication is automatic. 
	![[Pasted image 20250703111237.png]]
	- When using the `password-protected` key pairs, the Python `getpass` module is used to generate a prompt for the user to enter the key passphrase. The prompt is for SSH ky passphrase rather than a user login password. If you did not configure an SSH key passphrase when the SSH keys were generated, you can omit the `passwd` argument.
	
- Storing usernames and passwords in Python scripts is not secure. If public key authentication is not an option, you can configure a Python script that prompts a user for credentials when the Python script is run. Import the built-in Python `getpass` module and define login prompt variables. Reference the login prompt variables in the connection portion of the script. When the script is run, the user is presented with username and password prompts during authentication.
	![[Pasted image 20250703111608.png]]
## Performing Junos PyEZ Device Operations

- Junos PyEZ perform operational tasks: Reboot and power off platforms, secure copy files, upgrade Junos software, access the Unix and Junos device shell, ...
	
	- `jnpr.junos.utils.sw` module `SW` class provides `reboot()` and `poweroff()` methods to manage the device run time. The operation can be performed immediately (default) or scheduled for later. If the script is connected to he device using NETCOND over SSH, you will need to call the device object `open()` method again to reconnect.
	![[Pasted image 20250703145752.png]]![[Pasted image 20250703145812.png]]
		- The `SW` class also provides the methods that enable yo to install or upgrade Junos software through `install()`. This includes standalone devices with a single routing engine, standalone devices equipped with dual routing engines, EX/QFX series Virtual Chassis in mixed-mode and non-mixed-mode configurations, Mixed EX and QFX Virtual Chassis, VM host upgrades on routing engines with VM Host Support, and deployment configurations that have some form of in-service features enabled, such as unified in-service software upgrade (ISSU) or nonstop software upgrade (NSSU).
		![[Pasted image 20250703150610.png]]![[Pasted image 20250703150740.png]]
	- `jnpr.junos.utils.scp` module defines the `SCP` class that is used to establish Secure Copy Protocol (SCP) sessions with Junos platforms. This object class is commonly used during the Junos software image file to target devices. Files, such as device logs, can also be securely copied from the target devices. Junos PyEZ also includes the `jnpr.junos.utils.fpt` module `FTP` class that provides similar capabilities using FTP.
	![[Pasted image 20250703151221.png]]![[Pasted image 20250703151235.png]]![[Pasted image 20250703151309.png]]
	- `jnpr.junos.utils.start_shell` module defines the `StartShell` class. The `StartShell` class enables Python applications to initiate an SSH connection to a Junos device and access the Junos or Unix shell. The `StartShell` object `run()` method enables a Python application to execute Unix shell and Junos CLI commands and retrieve responses.
	![[Pasted image 20250703151637.png]]![[Pasted image 20250703151701.png]]
## Automating Junos Device Operations

- Network Administrator use Junos PyEZ to execute remote procedures calls (RPCs) on Junos devices and perform the same operational tasks traditionally performed using the Junos CLI. PyEZ uses the same XML API used by the CLI to send retrieve data to and from the Junos management daemon `mgd`. You can determine  the RPC corresponding to a particular Junos CLI command by issuing the CLI and including the `| displat xml rpc` command operator.
	![[Pasted image 20250703154036.png]]![[Pasted image 20250703154133.png]]![[Pasted image 20250703154147.png]]

<h2 style="color:#6290C3"><center> Configuring Junos Devices Using Junos PyEZ </center></h2>
## Automating Device Configuration

- `jnpr.junos.utils.config` modules defines the `Config` class. The utility enables you to retrieve, load, rollback, and compare Junos device configuration. PyEZ supports both unstructured and structured configuration changes.
	
	- Unstructured configuration changes consist of static or templated configuration data that is formatted using ASCII text, Junos XML elements , Junos set commands, or JavaScript Object Notation (JSON). Unstructured changes can leverage Python `Jinjia2` templates to deploy configuration containing unique device-specific configuration values. 
		
	- Structured configuration changes use PyEZ tables and view to define the configure specific resources.
	
- Some common Junos PyEZ Config Object method.
	![[Pasted image 20250703155734.png]]
- Simple script that demonstrates how to modify a private copy of the candidate configuration. Note that for networks that uses extensive automation, it is recommended that you perform configuration management using a private configuration database because locking the shared configuration can affect other automation tools. 
	![[Pasted image 20250703155956.png]]
- Retrieve Junos Configuration.
	![[Pasted image 20250703160047.png]]
- The Junos `Config` class provides `pdiff()` and `diff()` methods that can perform the same functions as the Junos CLI `show | compare` command. The `pdiff()` method returns the difference as standard command output. The `diff()` method returns the difference as an object.
	![[Pasted image 20250703160338.png]]![[Pasted image 20250703161304.png]]
	- The `rollback()` method supports an `rb_id` option that is used when performing configuration rollback operations. These operations are equivalent to a Junos CLI configuration mode `rollback` command.
	![[Pasted image 20250703161437.png]]![[Pasted image 20250703161654.png]]![[Pasted image 20250703161755.png]]
	- The `rescue()` method leverages the `save` action to generate a new rescue configuration.
	![[Pasted image 20250703161928.png]]![[Pasted image 20250703162015.png]]
	- The `load()` method to load configuration data from a file. Configuration files can be located on the management workstation, on the Junos device, or at a URL that is reachable from the Junos device. The configuration data can be formatted as ASCII text, Junos XML elements, Junos OS `set` commands, or JSON. Make sure to use `path` and `url` options to specify the location of the configuration file to load, `lock()` and `unlock()` method to lock and unlock candidate configuration.
	![[Pasted image 20250703163137.png]]![[Pasted image 20250703163242.png]]![[Pasted image 20250703163809.png]]
	- The `commit()` method supports commit operations that are equivalent to the options provided by the Junos CLI.
	![[Pasted image 20250716100851.png]]![[Pasted image 20250716100939.png]]
	For Redundant Routing Engines.
	![[Pasted image 20250716101323.png]]
## Exception Handling

- Exceptions are errors that happens in the runtime, causing the operations to fail.
	
- `jnpr.junos.exception` Modules handle PyEZ runtime exceptions. It defines Junos-specific exceptions, including connection errors (ex: auth errors), configuration errors, commit errors, protocol timeout errors, and permission errors.
	![[Pasted image 20250716101846.png]]
## Jinja2 Templates

- Jinja2 templates is utilize to configure device with unique values.
	
	- Identify device configuration that you want to turn into template variable values.
	![[Pasted image 20250716102219.png]]
	- Creating the Jinja2 templates. The variable values are enclosed in curly brackets. 
	![[Pasted image 20250716102609.png]]
	- Creating a YAML file  for each device containing the unique variables. Make sure to match the variable name used in Jinja2 templates.
	![[Pasted image 20250716102804.png]]
	- Creating a script using the Jinja2 Template.
	![[Pasted image 20250716102937.png]]
## Junos XML API Automation

- Example.
	![[Pasted image 20250716103511.png]]
- [XML Parsing]: Used to optimize operation memory and processing speed.
	![[Pasted image 20250716103721.png]]
- Parsing the next hop.
	![[Pasted image 20250716103854.png]]


<h2 style="color:#6290C3"><center> Data Serialization-JSON and YAML </center></h2>
## JSON and YAML: Data Structures

- JSON Dictionary.
	![[Pasted image 20250717094751.png]]
- [JSON]: A lightweight data-interchange format. It is human-readable but is easier for machines to parse than human. It is language-independent but uses conventions like C,C++,JAVA,JAVASCRIPT,PERL, and PYTHON. It first appeared as a lightweight alternative to XML and quickly became popular.
	
	- JSON is simple and universal but sacrifice human readability.
	![[Pasted image 20250717095607.png]]
	- JSON is often used as an alternative for XML. Retrieving operational and configuration data using Junos CLI or NETCONF, uploading content, and REST API.
		
	- JSON is case-sensitive, uses curly braces {} for data structures, ignore white spaces, does not offer a way to add comments, only has two data structures which is objects and arrays which are nesting available.
	![[Pasted image 20250717100237.png]]![[Pasted image 20250717100353.png]]
	- [JSON Objects]: Begin and ends with curly braces and contain at least one key-value pair. The key-value pair are enclosed in quotes and separated by colon. A single object can contain a series of key-value pair that are separated by commas. An empty object is also allowed, but keys in JSON are always a string data types.
	![[Pasted image 20250717100626.png]]
	- [JSON Arrays]: An ordered collection of values. Array structures begin with square brackets and contain zero, one, or more values separated by commas.
	![[Pasted image 20250717100852.png]]
	- Nested Objects and Arrays.
	![[Pasted image 20250717100948.png]]
	- JSON Junos Configuration via `show | display json`.
	![[Pasted image 20250717101309.png]]
	 
- [YAML]: A unicode-based data serialization language designed around common native data types found in agile programming languages. It is very human-readable and is useful for a variety of tasks, including-configuration files, internet messaging, object persistence, and data auditing. It uses indentation to show structures. It was designed as a superset of JSON, offering improved human readability and a more complete information model. Every JSON file is also a valid YAML file but not vice versa.
	
	- YAML is more complex but increase human readability.
	![[Pasted image 20250717095622.png]]
	- YAML is used in Junos Automation to define Junos PyEZ tables and views, which are used to map portions of a remote procedure call (RPC) response into a Python data structure. It is also used in Ansible to create playbooks that automate Juniper devices. 
		
	- YAML is case-sensitive uses indentation for structure, uses spaces instead of tabs, YAML documents start with three dashes, string do not need quotes unless they include special characters, comments begin with #, and has two basic structures which is mappings and sequences.
	![[Pasted image 20250717104508.png]]![[Pasted image 20250717104530.png]]
	- Nested YAML uses indentations to create structures.
	![[Pasted image 20250717104608.png]]
## Junos Automation with JSON and YAML

- Python and Jinja2.
	![[Pasted image 20250717104810.png]]
- Ansible.
	![[Pasted image 20250717104835.png]]
- Junos PyEZ tables and views in YAML.
	![[Pasted image 20250717104922.png]]![[Pasted image 20250717104939.png]]
	- Creating users with custom Tables and Views involves three main files—`ConfigTables.py`, `ConfigTables.yml`, and the `users.py` Python script. You need to follow certain steps to create Tables and Views and import them into Junos PyEZ application.
		![[Pasted image 20250717105404.png]]
	- First, you need to define Tables and Views in the YAML file with the `.yml` extension. Then, create a file that has the same base filename as the Table file but that uses `.py` extension. The ConfigTables.py file uses the Junos PyEZ loadyaml() routine to load the YAML file and then import it into the global namespace of the module.
		![[Pasted image 20250717105525.png]]
	- Now add `ConfigTables.yml` and `ConfigTables.py` files in a folder. Include an `__init__.py` file if the files are in the sub-directory.
		
	- Create a Python script `users.py`. The Python script imports `UserConfigTable` and configures values for the username, `userclass`, and password fields. You use the `append()` method to build the corresponding Junos XML configuration and add it to the `lxml` object that stores the primary set of configuration changes. You can load the configuration into the shared configuration database on the device. Using the set() method, you can automatically call the lock(), load(), commit(), and unlock() methods.
		![[Pasted image 20250717105754.png]]![[Pasted image 20250717105849.png]]

<h2 style="color:#6290C3"><center> Automating Junos Device Using REST API </center></h2>
## Junos REST API Functionality

- Benefits: 
	
	- Securely execute configuration.
		
	- Simple configuration.
		
	- Network Configuration Protocol and SSH are not required.
		
	- Juniper provides a GUI REST API Explorer.
		
	- Supports data in ASCII text, JSON, and XML formats.
	
- Junos REST API Architecture:
	
	- After the REST service is enabled, a `lighttpd` server launches and begins listening to incoming connections.
		
	- A REST client makes HTTPS Junos RPC requests.
		
	- The `lighttpd` server receive and processes the HTTP GET or POST request and forwards the client RPC request to the `mod_juise` plug-in.
		
	- The `mod_juise` plug-in invokes the Junos User Interface Scripting Environment (JUISE) to process the Junos RPC and authentication.
		
	- The RPC request is passed to the Junos management process (mgd).
		
	- The `mgd` returns the data back to the JUISE, which formats the data for the `lighttpd` web server, which the passes the response back to the REST Client.
		
	- #Note: `lighttpd`, `mod_juise`, and JUISE run inside a `chroot` environment for increased security. A environment that processes cannot access files outside of a designated directory structure.
	
- [Enabling Junos REST API over HTTP]: `set system services rest http port 3000`, 3000 is the default HTTP port. Or `http addresses [x.x.x.x y.y.y.y]`. Junos REST API supports IPv4 only.
