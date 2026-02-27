Multiple computations running simultaneously.

<h1 style="color:#6290C3"><center> Introduction </center></h1>

<h2> What is Concurrency? </h2>
- [Concurrency]: Multiple computations are happening at the same time. It is everywhere in modern programming. 
	
	- Multiple computers in a network.
		
	- Multiple applications running on one computer.
		
	- Multiple processors in a computer.
	
- It is essential in modern programming.
	
	- Websites must handle multiple simultaneous users.
		
	- Mobile apps need to do some of their processing on servers.
		
	- Graphical user interfaces almost always require background work that does not interrupt the user.

<h2> Two Models for Concurrent Programming </h2>
- There are two common models for Concurrent programming: Shared Memory and Message Passing.
	
- [Shared Memory]: In the shared memory model of concurrency, concurrent modules interact by reading and writing shared objects in memory.
	![[Screenshot_20260223-141622.png]]
	
- [Message Passing]: In this model, concurrent modules interact by sending messages to each other through a communication channel. Modules send off messages, and incoming messages to each module are queued up for handling.
	![[Screenshot_20260223-141946.png]]

<H2> Processes, Threads, Time-slicing </h2>
- The message-passing and shared-memory models are about two concurrent modules communicate. The concurrent modules themselves come in two different kinds: Processes and Threads.
	
- [Process]: A process is an instance a running program that is isolated from other processes on the same machine. In particular, it has its own private section of the machine's memory.
	
	- The process abstraction is virtual computer. It makes the program feel like it has the entire machine to itself. 
		
	- Just like computers connected across a network, processes normally share no memory between them. A process can't access other process's memory or objects at all. Sharing memory between processes is possible on most operating system, but it needs special effort. By contrast, a new process is automatically ready for message passing, because it is created with standard input & output streams, which are the `system.out` and `system.in` stream in Java.
	
- [Thread]: A locus of control inside a running program. A place in the program that is being run, plus the stack of method calls that led to that place to which it will be necessary to return through. 
	
	- Jus as a process represents a virtual computer, the thread abstraction represents a virtual processor. Making a new thread simulates making a fresh processor inside the virtual computer represented by the process. This new virtual processor runs the same program a shares the same memory as the other threads in process.
		
	- Threads are automatically ready for shared memory, because threads share all the memory in the process. It needs special effort to get "thread-local" memory that's private to a single thread. It's also necessary to set up message-passing explicitly, by creating and using queue data structures.

<h2> Interleaving </h2> 
- A process where multiple process/thread happens at once, this might happen at the same time or not the same time. Interleaving in concurrency are one of the best method to determine a case where a concurrent actions should be delayed by an fraction or a common middle partner should be establish to best produce or satisfy a postconditions and invariants. 

<h2> Race Condition </h2>
- Race condition means that the correctness of the program (the satisfactions of postconditions and invariants) depends on the relative timing of events in concurrent computations A and B. When this happens, we say "A is in a race with B."
	
- Some interleavings of events may OK, in the sense that they are consistent with what a single, nonconcurrent process would produce, but other interleavings produce wrong answers - violating postconditions or invariants.

<h2> Reordering </h2>
- 
