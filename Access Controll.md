- Nature of access
<center><h2> Basic </h2></center>

## Resources and Ownership

- Users:
	Launch processes and own files. A process is a program (executable file) that the kernel has loaded into main memory and runs.
- Files:
	Have owners; by default, the user who creates the files own it.
- Processes:
	Use files for communication and persistency. Of course, users indirectly also use files, but they need to do so via processes.

## Sandboxing

- A security practice that involves running code in an isolated environment, or "sandbox", to test for potential threats.

## Types of Access Control

- Discretionary access control:
	 With discretionary access control (DAC), the idea is to restrict access to resources based on the identity of the user. It's discretionary in the sense that a user with certain permissions can pass them on to other users.
- Mandatory access control:
	 Mandatory access control is based on  a hierarchical model representing security levels. User are assigned a clearance level, and resources are assigned a security label. Users can only access resources corresponding to a clearance level equal to (or lower than) their own. In a mandatory access control model, an admin strictly and exclusively control access, setting all permissions. In other words, users cannot set permissions themselves, even when they own the resources. 

## Users

- System-user/accounts:
	Typically, programs (sometimes called daemons) use these types of accounts to run background processes. The services provided by these programs can be part of the operating system, such as networking (sshd, for example), or on the application layer (for example, mysql, in the case of a popular relational database).
- Regular Users:
	For example, a human user that interactively uses Linux via the shell. 

- UID: User identification.
	- UID 0: aka root user/superuser.
	- UID 1-999: reversed for system users.
	- UID: 65534: User nobody-used.
	- UID 1000 to 65533 and 65536 to 4294967294: Regular user.

