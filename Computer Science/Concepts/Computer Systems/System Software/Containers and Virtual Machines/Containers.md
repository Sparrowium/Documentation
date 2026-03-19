<h1 style="color:#6290C3"><center> Introduction </center></h1>
##  What are Containers? 
- [Containers]: Are a technology that allow applications to be packaged and isolated with their entire runtime environment. This makes it easier to maintain consistent behavior and functionality while moving the contained application between environments (dev, test, production) and across public, private, hybrid cloud, and on-premise. Because they are lightweight and portable, containers provide opportunities for faster development pipelines that rely on replicating traditional testing environments..
	![[Pasted image 20260222223920.png]]
	
- Containers are an abstraction at the app layer that packages code and dependencies together. Multiple containers can run on the same machine and share the OS kernel with other containers, each running as isolated processes in user space. Containers take up less space than VMs (containers images are typically tens of MBs in size), can handle more application and require fewer VMs and Operating Systems.

##  What is Containerization (computing) 
- [Containerization]: Is a operating-system-level virtualization or application-level virtualization over multiple resources so that software applications can run in isolated user spaces called containers in any cloud or non-cloud environment, regardless of type or vendor.

##  Usage 
- Each container is basically a fully functional and portable cloud or non-cloud computing environment surrounding the application and keeping it independent of other environments running in parallel. Individually, each containers simulates a different software application and runs isolated processes by bundling related configuration files, libraries, and dependencies. But, collectively, multiple containers share a common operating system kernel (OS).
	
- [Cloud Migration]: Is the software strategy that involves encapsulating legacy applications in containers and deploying them in a cloud computing environment. Organization can modernize their applications without rewriting the entire software code.
	
- [Adoption of Microservice Architecture]: A software development approach that uses multiple, interdependent software components to deliver a functional application. Each microservice has a unique and specific function. 
	
- [IoT Devices]: Contain limited computing resources, making manual software updating a complex process. Containerization allows developers to deploy and update application across IoT devices easily.

##  How does containerization work? 
- Containerization involves building self-sufficient software packages that perform consistently, regardless of the machines they run on. Software developers create and deploy container images-that is, files that contain the necessary information to run a containerized application. Developers use containerization tools to build container images based on the Open Container Initiative (OCI) image specification. OCI is an open-source group that provides a standardized format for creating container images. Container images are read-only and cannot be altered by the computer system.
	
- [Infrastructure]: Is the hardware layer of the container model. It refers to the physical computer or the bare-metal server that runs the containerized application. 
	
- [Operating System]: The second layer of containerization architecture is the operating system. 
	
- [Container Engine]: Or container runtime, is a software program that creates containers based on the container images. It acts as an intermediary agent between the containers and the operating system, providing and managing resources that eh application needs.
	
- [Application and Dependencies]: The topmost layer of the containerization architecture is the application code and the other files it needs to run, such as library dependencies and related configuration files. This layer might also contain a light guest operating system that gets installed over the host operating system.

##  What is Container Orchestration? 
- [Container Orchestration]: A software technology that allows the automatics management of containers. This is necessary for the modern cloud application development because an application might contain thousands of microservices in their respective containers. The large number of containerized microservices makes it impossible for software developers to manage them manually.
	
- Developers use container orchestration tools to automatically start, stop, and manage containers. Container Orchestrators allow developers to scale cloud applications precisely and avoid humans errors. 

##  Types of container technology 
- [[Docker]]: A popular open-source container runtime that allows software developer to build, deploy, and test containerized application on various platforms. Docker containers are self-contained packages of application and related files that are created with the Docker framework.
	
- [[Linux]]: An open-source operating system with built-in container technology. Linux container ([LXC]) are self-contained environments that allow multiple Linux-based applications to run on  a single host machine. Software developers uses Linux containers to deploy applications that write or read large amounts of data. Linux container do not copy the entire operating system to their virtualized environment. Instead, the containers consist of necessary functionalities allocated in the Linux namespace.
	
- [Kubernetes]: An open-source container orchestrator that software developer use to deploy, scale, and manage a vast number of micro services. It has a declarative model that makes automating easier. The declarative model ensures that Kubernetes takes the appropriate action to fulfil the requirements based on the configuration files.