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
<h2> The Basics </h2>
<h3> What Is A Container? </h3>
- Containers are isolated processes for each of your app's components. Each component run in its own isolated environment, completely isolated from everything else on your machine. 
	
	- Each container has everything it needs to function with no reliance on any pre-installed dependencies on the host machines.
		
	- They have minimal influence on the host and other containers, increasing the security of your applications.
		
	- Each container is independently managed. Deleting one container won't affect any others.
		
	- Containers can run anywhere, one that runs on your development machine will work the same way in a data center or else where.

<h3> Containers Versus Virtual Machine </h3>
- VM is an entire operating system with its own kernel, hardware drivers, programs, and applications. Spinning up a VM only to isolate a single application is a lot of overhead.
	
- A container is simply an isolated process with all the files it needs to run. If you run multiple containers, they all share the same kernel, allowing you to run more application on less infrastructure.
	
- Quite often, you will see containers and VMs used together. As an example, in a cloud environment, the provisioned machines are typically VMs. However, instead of provisioning one machine to run one application, a VM with a container runtime can run multiple containerized applications, increasing resource utilization and reducing costs.

<h3> What Is An Image? </h3>
- A container image is a standardized package that includes all of the files, binaries, libraries, and configurations to run a container.
	
- Two important principles of images:
	
	- Images are immutable. Once an image is created, it can't be modified. You can only make a new image or add changes on top of it.
		
	- Container images are composed of layers. Each layer represents a set of file system changes that add, remove, or modify files.
	
- These two principles let you to extend or add to existing images. Starting from the foundation (python, go, c, ...) and add additional layers to install your app's dependencies and add your code.

<h3> Finding Images </h3>
- [Docker Hub]: The default global marketplace for storing and distributing images. It has over 100000 images created by developers that you can run locally. You can search for Docker Hub images and run them directly form Docker Desktop.
	
- Docker Hub provides a variety of Docker-supported and endorsed images known as Docker Trusted Content. These provide fully managed services or great starters for your own images. These include:
	
	- [Docker Official Images]: A curated set of Docker repo, serve as the starting point for the majority of users, and are some of the most secure on Docker Hub.
		
	- [Docker Hardened Images]: Minimal, secure, production-ready images with near-zero CVEs, designed to reduce attack surface and simplify compliance. Free and open source under Apache 2.0.
		
	- [Docker Verified Publishers]: High quality images from commercial publishers verified by Docker. 
		
	- [Docker-Sponsored Open Source]: Images published and maintained by open-source projects sponsored by Docker through Docker's open source program.

<h3> What Is A Registry? </h3>
- An image registry is a centralized location for string and sharing your container images. It can be either public or private. Docker Hub is a public registry that anyone can use and is the default registry.

<h3> Registry VS Repositories </h3>
- A _registry_ is a centralized location that stores and manages container images, whereas a _repository_ is a collection of related container images within a registry.
	![[Pasted image 20260308174922.png]]

<h3> What Is Docker Compose? </h3>
- [Docker Compose]: A declarative tool used to define all of the containers and their configurations from networks, flags, in a single YAML file. If you include this file in your code repository, anyone that clones your repo can get up and running with a single command. 
	
- Compose is a declarative tools, you define it and go. No need for recreate everything from scratch, for changes run `docker compose up` again and Compose will reconcile the changes in your file and apply them intelligently.

<h2> Building Images </h2>
<h3> The Image Layer </h3>
- Each layer in an image contains a set of filesystem changes - additions, deletions, or modifications.
	
	- The first layer adds basics commands and a package manager, such as apt.
		
	- The second layer installs a Programming Languages and Language Dependencies Manager for dependency management.
		
	- The third layer copies in an application's specific requirements.txt file.
		
	- The fourth layer installs that application's specific dependencies.
		
	- The fifth layer copies in the actual source code of the application.
	![[Pasted image 20260308183344.png]]
	
- This the beneficial because it allows layers to be reused between images. Thanks to layering you can leverage the same base. This will make builds faster and reduce the amount of storage and bandwidth required to distribute the images.
	![[Pasted image 20260308184304.png]]
	
- Layers let you extend images of others by reusing their base layers allowing you to add only the data that your application needs.

<h3> Stacking The Layer </h3>
- Layering is made possible by content-addressable storage and union filesystems.
	
	- After each layer is downloaded, it is extracted into its own directory on the host filesystem.
		
	- When you run a container from an image, a union filesystem is created where layers are stacked on top of each other, creating a new and unified view.
		
	- When the container starts, its root directory is set to the location of this unified directory, using `chroot`.
	
- When the union filesystem is created, in addition to the image layers, a directory is created specifically for the running container. This allows the container to make filesystem changes while allowing the original image layers to remain untouched. This enables you to run multiple containers form the same underlying image.