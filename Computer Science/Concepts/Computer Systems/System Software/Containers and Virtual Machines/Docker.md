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
	
	- [Images]: An image is a read-only template with instruction for creating a Docker container.