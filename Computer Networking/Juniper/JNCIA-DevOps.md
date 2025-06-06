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

