An Operating System based on UNIX, it is also known as GNU/Linux

<h2 style="color:#6290C3"><center> Introduction </center></h2>
## What is Linux?

- An operating system takes on all this undifferentiated heavy lifting, abstracting away the different hardware components and providing you with a (usually) clean and nicely designed Application Programming Interface (API).
	
- Linux have a lot of distributions, often called as **distros**, which includes a concrete bundling of kernel and related components, including package management, file systems layouts, init systems, and a shell, preselected for you.
	
- Everything in Linux is a file.
	
- Linux was built to be POSIX(Portable Operating System Interface)-compliant as well as to be compliant with the UNIX System V Interface Definition (SVID), which gave it the flavor of old-time AT&T UNIX systems, as opposed to Berkeley Software Distribution (BSD)-style systems.

<h2 style="color:#6290C3"><center> Linux Kernel </center></h2>
- Provides the core functionality, on its own it is not the operating system, but a central part of it.

## Linux Architecture

![[Pasted image 20250304193433.png]]

- There are three distinct layers:
	
	- [Hardware]: From CPUs and mainboard to disk drives, network interfaces, and peripheral devices such as keyboards and monitors.
		
	- [The Kernel]: Known as the "bridge", the layer of abstraction that allows the user connect to the hardware through user spaces.
		
	- [User Land]: Where majority of the apps are running, including the operating systems components such as shells, utilities like ps or ssh, and graphical user interfaces such as X Window System-based desktops.
	
- The interfaces between he different layers are well defines and part of the Linux Operating Systems package. Between the kernel and the user land/space is the interface called *system calls (syscalls for short)*.
	
- The interfaces between the hard and the kernel consists of a collection of individual interfaces, usually grouped by hardware:
	
	- The CPU interface.
		
	- The interface with the main memory.
		
	- Network interfaces and drivers.
		
	- Filesystem and block devices driver interfaces.
		
	- Character devices, hardware interrupts, and device drivers, for input devices like keyboards, terminals, and other I/O devices.
	
- In the user land consists of grep, find, ping, shells, which are very much like an app you download.
	
- There are two main modes, Kernel Mode and User Mode. These mode refers to how privileged the access to hardware is and how restricted the abstractions available are. 
	
- [Kernel Mode]: Means fast execution with limited abstractions.
	
- [User Mode]: Means comparatively slower but safer and more convenient abstractions. 

### CPU Architectures

- Linux runs on a large number of different CPU architectures. For each architecture, it contains a architecture specific code, which allows it to port Linux and make it available on new hardware quickly.
	
- [BIOS and EUFI]: 
	
	- [BIOS]: known as Basic I/O System are used to bootstrapping Linux. When the device is first powered, it is entirely hardware-controlled. First off, the hardware is wired to run the Power On Self Test (POST), part of the BIOS. POST makes sure that the hardware (RAM, etc.) function as specified.
		
	- [EUFI]: Unified Extensible Firmware Interface, a public specification that defines a software interface between an operating system and platform firmware. Replaced the traditions BIOS functions.
	
- There are many ways to check your CPU architecture information.
	`lscpu`
	`cat /proc/cpuinfo`
	`uname -m`
	
- [x86 Architecture]: An instruction set family originally developed by Intel and later licensed to AMD. Within the kernel, x64 refers to Intel 64bit, x86 stands for Intel 32bit, and amd64 refers to AMD 64bit. Specifically, x86 forms the basis of the public cloud. It is a powerful and widely available architecture but isn’t very energy efficient. Partially due to its heavy reliance on out-of-order execution.
	
- [ARM Architecture]: A family of Reduced Instruction Set Computing (RISC) Architecture. Usually consists of many generic CPU registers along with a small set of instructions that can be executed faster. Very power efficient, mostly on mobile platform.
	
- [RISC-V Architecture]: An open RISC standard.

### Kernel Components

- Linux Kernel is a monolithic one--that is, all the components discussed are part of a single library--there are functional areas in the code base that we can identify and ascribe dedicated responsibility.
	
- Main functional blocks in kernel code base:
	
	- [Process Management]: Such as starting a process based on an executable file.
		
	- [Memory Management]: Such as allocating memory for a process or map a file into memory.
		
	- [Networking]: Like managing network interfaces or providing network stack.
		
	- [Filesystem]: Provides file management and supporting the creation and deletion of files.
		
	- Management of character devices and devices drivers.
	
- [Process Management]: The managing of processes with are related to CPU and launching and scheduling of programs.
	`ps -j`
	
	- [Sessions]: Contain one or more process groups and represent a high-level user-facing unit with optional tty attachments. The kernel identifies a sessions via a number called session ID (SID).
		
	- [Process Groups]: Contain one or more processes, with at most one process group in a session as the foreground process group. The kernel identifies a process group via a number called process group id (PGID).
		
	- [Processes]: Abstractions that group multiple resources, which the kernel exposes to you via /proc/self for the current process. The kernel identifies a process via a number called process ID (PID).
		
	- [Threads]: Implemented by the kernel as processes. That is, there are no dedicated data structures representing threads. Rather, a thread is a process that shares certain resources with other processes. The kernel identifies a thread via thread is (TID) and thread group id (TGID), with the semantics that a shared TGID value means a multi-threaded process.
		
	- [Tasks]: A data structures called `task_struct` forms the basis of implementing processes and threads alike. This data structures captures scheduling-related information, identifiers, and signal handlers, as well as other information, such as that related to performance and security.
	![[Pasted image 20250304205230.png]]
- [Memory Management]: How to effectively provide each process with the illusion that its page actually exists in RAM while using the existing space optimally. 
	
	- Virtual memory makes your system appear as if it has more memory than it physically has. In fact, every process gets a lot of (virtual) memory. This is how it works: both physical memory and virtual memory are divided into fixed-length chunks we call pages.
		
	- Tools to figure out memory-related information:
		`grep MemTotal /proc/meminfo`
		`grep VmallocTotal /proc/meminfo`
		`grep Huge /proc/meminfo`
	![[Pasted image 20250304205727.png]]
- [Networking]: 
	`ip link`: Show linking information.
	`ip route`: Show routing information.
	
	- [Sockets]: For abstracting communication.
		
	- [Transmissions Control Protocol (TCP), User Datagram Protocol (UDP)]: For connection-oriented communication and connection-less communication respectively.
		
	- [Internet Protocol (IP)]: For addressing machines.
	
- [Filesystem]: To organize files and directories on storage devices. 
	
	- [VFS]: Virtual File System, support multiple filesystem types and instances. The higher layer in VFS provides a common API abstraction of functions. The bottom layer are filesystem abstraction called plug-ins for the given filesystem.
	
- [Device Drivers]:
	
	- [Driver]: A bit of code that runs in the kernel. Its job is to manage a device, which can be actual hardware or it can be pseudo-device such as pseudo-terminal under /dev/pts/.
		
	- [GPUs Driver]: Are special driver for graphical purpose.
		
	- The Driver may be built into the kernel, or it can be built as a kernel module so that it can be dynamically loaded when needed.
		
	- Tools to check devices:
		`ls -al /sys/devices/`
		`mount`
	
- [syscalls]: The service interface the kernel exposes and that user land entities call.
	
	- Linux has hundreds of syscalls: around three hundred or more, depending on the CPU family. However, the programs don’t usually invoke these syscalls directly but via what we call the C standard library. The standard library provides wrapper functions and is available in various implementations, such as glibc or musl. These wrapper libraries perform an important task. They take care of the repetitive low-level handling of the execution of a syscall. System calls are implemented as software interrupts, causing an exception that transfers the control to an exception handler.
		
	- Use `strace ls`, `strace -c\` to troubleshoot or looking at the history log of syscalls.
	![[Pasted image 20250304212544.png]]![[Pasted image 20250304213022.png]]

### Kernel Extensions

- [Module]: A program that you can load into a kernel on demand. That is, you do not necessarily have to recompile the kernel and/or reboot the machine. 
	
	- Modern Linux loads modules automatically.
		
	- To list available modules type: 
		`find /lib/modules/$(uname -r) -type f -name '*.ko*'`
		`lsmod`
		`modprobe --show-depends async_memcpy`