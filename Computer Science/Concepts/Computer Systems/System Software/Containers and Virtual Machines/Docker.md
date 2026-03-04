Large shipping BO-AT but software style.

<h1 style="color:#6290C3"><center> Introduction </center></h1>
<h2> What is Docker? </h2>
- [Docker]: An open source platform for developing, shipping, and running applications. 
	
- It enables you to separate your applications from your infrastructure so you can deliver software quickly, and manage the infrastructure the way you manage your applications. 
	
- It significantly reduce the delay between writing code and running it in production.

<h2> The Platform </h2>
- Provides the ability to package and run an application in a loosely isolated environment called a container. The isolation and security let you run many containers simultaneously on a given host. Containers are lightweight and contain everything needed to run the application, so you don't need you rely what's installed on the host. 
	
- Docker provides tooling and a platform to manage the lifecycle of your containers:
	
	- Develop your application and its supporting components using containers.
		
	- The container becomes the unit for distributing and testing your application. 
		
	- When you're ready, deploy your application into your production environment, as a container or an orchestrated service. This works the same whether your production environment is a local data center, a cloud provider, or a hybrid of the two.

<h2> The use case of Docker </h2>
- Fast, consistent delivery of your applications. 
	
	- By allowing developers to work in standardized environment using local containers, Docker streamlined the development lifecycle, which provide your applications and services. Containers are great for continuous integration and continuous delivery (CICD) workflow.
	
- Responsive Deployment and Scaling.
	
	- Docker's container-based platform allows for highly portable workloads. Docker containers can run on a developer's local laptop, on a physical or virtual machine in a data center, on cloud providers, or in a mixture of environments.
		
	- Docker's portability and lightweight nature also make it easy to dynamically manage workloads, scaling up or tearing down application and services as business needs dictate, in near real time.
	
- Running More Workload On The Same Hardware.
	
	- Docker is lightweight and fast. It provides a viable, cost-effective alternative to hypervisor-based virtual machines, so you can use more of your server capacity to achieve your business goals. Docker is perfect for high density environments and for small and medium deployments where you need to do more with fewer resources.

<h2> Docker Architecture </h2>
- Docker uses a client-server architecture. The Docker client talks to the Docker daemon, which does the heavy lifting of building, running, and distributing your Docker containers. The Docker client and daemon can run on the same system, or you can connect a Docker client to a remote Docker daemon. The Docker client and daemon communicate using a REST API, over UNIX sockets or a network interface. Another Docker client is Docker compose, that lets you work with application consisting of a set of containers.
	![[Pasted image 20260227192455.png]]
	
- [Docker Daemon (dockerd)]: Listens for Docker API requests and manages Docker objects such as images, containers, networks, and volumes. A daemon can also communicate with other daemons to manage Docker services.
	
- [Docker Client (docker)]: Is the primary way that many Docker users interact with Docker. When you use commands such as `docker run`, the client sends these commands to `dockerd`, which carries them out. The `docker` command uses Docker API. The Docker client can communicate with more than one daemon.
	
- [Docker Desktop]: Docker engine but visualized.
	
- [Docker Registries]: Store Docker images. **Docker Hub** is a public registry that anyone can use, and Docker looks for images on Docker Hub by default. You can even run your own private registry. 
	
	- When you use the `docker pull` or `docker run` commands, Docker pulls the required images from your configured registry. When you use the `docker push` command, Docker pushes your image to your configured registry.
	
- [Docker Objects]: When you use Docker, you are creating and using images, containers, networks, volumes, plugins, and other objects. This section is a brief overview of some of those objects.
	
	- [Images]: An image is a read-only template with instruction for creating a Docker container. Often, an image is based on another image with some additional customization. For example, you may build an image that is based on the Ubuntu image but includes the Apache web server and your application, as well as the configuration details needed to make your application run.
		
		- You might create your own images or you might only use those created by others and published in a registry. To build your own image, you create a Dockerfile with a simple syntax for defining the steps needed to create the image and run it. Each instruction in a Dockerfile creates a layer in the image. When you change the Dockerfile and rebuild the image, only those layers will have changed are rebuilt. This is part of what makes images so lightweight and small, and fast, when compared to other virtualization technologies.
		
	- [Containers]: A runnable instance of an image. You can create, start, stop, move, or delete a container using the Docker API or CLI. You can connect a container to one or more networks, attach storage to it, or even create a new image based on its current state.
		
		- By default, a container is relatively well isolated from other containers and its host machine. You can control how isolated a container's network, storage, or other underlying subsystems are from other containers or from the host machine.
			
		- A container is defined by its image as well as any configuration options you provide to it when you create or start it. When a container is removed, any changes to its state that aren't stored in persistent storage disappear.
		
	
	`docker run -i -t ubuntu /bin/bash`
	- If you don't have the `ubuntu` image locally, Docker pulls it from your configured registry, as though you had run `docker pull ubuntu` manually.
		
	- Docker creates a new container, as though you had run a `docker container create` command manually.
		
	- Docker allocates a read-write filesystem to the container, as its final layer. This allows a running container to create or modify files and directories in its local filesystem.
		
	- Docker creates a network interface to connect the container to the default network, since you didn't specify any networking options. This includes assigning an IP address to the container. By default, containers can connect to external networks using the host machine's network connection.
		
	- Docker starts the container and executes `/bin/bash`. Because the container is running interactively `-i` and attached to your terminal `-t`, you can provide input using your keyboard while Docker logs the output to your terminal.
		
	- When you run `exit` to terminate the `/bin/bash` command, the container stops but isn't removed. You can start it again or remove it.

<h2> Underlying Technology </h2>
- Docker is written in [[Go]] programming language and takes advantage of several features of the Linux Kernel to deliver its functionality. Docker uses a technology called `namespaces` to provide the isolated workspace called the container. When you run a container, Docker creates a namespaces for that container.
	
- These namespaces provide a layer of isolation. Each aspect of a container runs in a separate namespace and its access is limited to that namespace. 

<h1 style="color:#6290C3"><center> Docker Concept </center></h1>
<h2> What Is A Container? </h2>
- Containers are isolated processes for each of your app's components. Each component run in its own isolated environment, completely isolated from everything else on your machine. 
	
	- Each container has everything it needs to function with no reliance on any pre-installed dependencies on the host machines.
		
	- They have minimal influence on the host and other containers, increasing the security of your applications.
		
	- Each container is independently managed. Deleting one container won't affect any others.
		
	- Containers can run anywhere, one that runs on your development machine will work the same way in a data center or else where.

<h2> Containers Versus Virtual Machine </h2>
- VM is an entire operating system with its own kernel, hardware drivers, programs, and applications. Spinning up a VM only to isolate a single application is a lot of overhead.
	
- A container is simply an isolated process with all the files it needs to run. If you run multiple containers, they all share the same kernel, allowing you to run more application on less infrastructure.
	
- Quite often, you will see containers and VMs used together. As an example, in a cloud environment, the provisioned machines are typically VMs. However, instead of provisioning one machine to run one application, a VM with a container runtime can run multiple containerized applications, increasing resource utilization and reducing costs.

<
- 