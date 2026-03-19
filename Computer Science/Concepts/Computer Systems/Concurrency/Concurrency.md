Multiple computations running simultaneously.

<h1 style="color:#6290C3"><center> Introduction </center></h1>

##  What is Concurrency? 
- [Concurrency]: Multiple computations are happening at the same time. It is everywhere in modern programming. 
	
	- Multiple computers in a network.
		
	- Multiple applications running on one computer.
		
	- Multiple processors in a computer.
	
- It is essential in modern programming.
	
	- Websites must handle multiple simultaneous users.
		
	- Mobile apps need to do some of their processing on servers.
		
	- Graphical user interfaces almost always require background work that does not interrupt the user.

##  Two Models for Concurrent Programming 
- There are two common models for Concurrent programming: Shared Memory and Message Passing.
	
- [Shared Memory]: In the shared memory model of concurrency, concurrent modules interact by reading and writing shared objects in memory.
	![[Screenshot_20260223-141622.png]]
	
- [Message Passing]: In this model, concurrent modules interact by sending messages to each other through a communication channel. Modules send off messages, and incoming messages to each module are queued up for handling.
	![[Screenshot_20260223-141946.png]]

##  Processes, Threads, Time-slicing 
- The message-passing and shared-memory models are about two concurrent modules communicate. The concurrent modules themselves come in two different kinds: Processes and Threads.
	
- [Process]: A process is an instance a running program that is isolated from other processes on the same machine. In particular, it has its own private section of the machine's memory.
	
	- The process abstraction is virtual computer. It makes the program feel like it has the entire machine to itself. 
		
	- Just like computers connected across a network, processes normally share no memory between them. A process can't access other process's memory or objects at all. Sharing memory between processes is possible on most operating system, but it needs special effort. By contrast, a new process is automatically ready for message passing, because it is created with standard input & output streams, which are the `system.out` and `system.in` stream in Java.
	
- [Thread]: A locus of control inside a running program. A place in the program that is being run, plus the stack of method calls that led to that place to which it will be necessary to return through. 
	
	- Jus as a process represents a virtual computer, the thread abstraction represents a virtual processor. Making a new thread simulates making a fresh processor inside the virtual computer represented by the process. This new virtual processor runs the same program a shares the same memory as the other threads in process.
		
	- Threads are automatically ready for shared memory, because threads share all the memory in the process. It needs special effort to get "thread-local" memory that's private to a single thread. It's also necessary to set up message-passing explicitly, by creating and using queue data structures.

##  Interleaving  
- A process where multiple process/thread happens at once, this might happen at the same time or not the same time. Interleaving in concurrency are one of the best method to determine a case where a concurrent actions should be delayed by an fraction or a common middle partner should be establish to best produce or satisfy a postconditions and invariants. 

##  Race Condition 
- Race condition means that the correctness of the program (the satisfactions of postconditions and invariants) depends on the relative timing of events in concurrent computations A and B. When this happens, we say "A is in a race with B."
	
- Some interleavings of events may OK, in the sense that they are consistent with what a single, nonconcurrent process would produce, but other interleavings produce wrong answers - violating postconditions or invariants.

##  Reordering 
- A common problem that usually happens when a process reads the other output rather than the expected 1st order output. This phenomenon happen because moderns compilers do a lot of things to make the code fast. One of those things is to store temporary copies of variables in a faster storage and working with them temporarily before storing them back into their official location in the memory. The storeback may occur in a different order than the variables were manipulated in your code, which causes reordering.
	
- This usually makes the program hard to debug as the speed of the process are within a mili-of-a-seconds. Even if async or wait/sleep is implement there are no certainty that this wont happen in a program as the storing mechanisms and optimization might bypass.

## Concurrency Is Hard To Test And Debug
- It’s very hard to discover race conditions using testing. And even once a test has found a bug, it may be very hard to localize it to the part of the program causing it.
	
- Concurrency bugs exhibit very poor reproducibility. It's hard to make them happen again the same way twice. Interleaving of instructions or messages depends on the relative timing of events that are strongly influenced by the environment. Delays ca be caused by other running programs, other network traffic, operating system scheduling decisions, variations in processors clock speed, etc. Each time you run a program containing a race condition, you may get a different behavior.
	
- These kinds of bugs are [heisenbugs], which are nondeterministic and hard to reproduce, as opposed to [bohrbug], which shows up repeatedly whenever you looked at it. Almost all bugs in sequential programming are bohrbugs. 
	
- A heisenbug may even disappear when you try to look at it with `println` or `debugger`. The reason is that printing and debugging are so much slower than other operations, often 100-1000x slower, that they dramatically change the timing of operations, and the interleaving. 
