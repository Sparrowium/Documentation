
<h2><center> Basic </center></h2>

<h1 style="color:#6290C3"><center> The Baseline </center></h1>
## Computer Subsystems

- Computer hardware consist of three separated subsystems: [Central Processing Unit], [Memory], and [Input/Output(I/O)]. These are connected with buses.
	![[Pasted image 20250112222509.png]]
- [Central Processing Unit (CPU)]: Controls the flow of data to and from memory and I/O devices. The CPU performs arithmetic and logical operations on the data. The CPU can decide the order of operations based on the results of arithmetic and logic operations. It contains a small amount of very fast memory.
	
- [Memory]: Provides storage that is readily accessible to the CPU and I/O devices for executing instruction and data manipulation.
	
- [Input/Output (I/O)]: Communicates with the problem exist between the chair and the table, and with mass storage devices.
	
- [Buses]: 
	
	- A physical communication pathway with a protocol specifying exactly how the pathway is used.
		
	- [Address Bus]: Used to specify a specific memory location or an I/O device.
		
	- [Data Bus]: Indicates the flow of program data and program instruction.
		
	- [Control Bus]: Carries signals that specify how each of the subsystems should be using the signals on other buses.

## Program Execution

- [Program]: Consists of a sequence of instructions stored in memory. When you create a new program, you can use an *editor* to write the *source code* for your new program and it will be stored as a file on the disk. The you use a *compiler* to translate the *high-level language* statements into machine code instruction that are stored in a disk file.
	
- When it comes time to execute the program, the CPU executes the program by reading-often called **fetching**-each instruction from memory and executing it.
	
- When the CPU is ready to execute the next instruction in the program, the location of that instruction in memory is placed on the address bus. The CPU also places a **read** signal on the control bus. The memory subsystem responds by placing the instruction on the data bus, where the CPU can then copy it.
	
- If the CPU is instructed to store data in memory, it places the data on the data bus, places the location in memory where the data is to be stored on the address bus, and places a **write** signal on the control bus. The memory subsystem responds by copying the data on the data bus into the specified memory location.

<h1 style="color:#6290C3"><center> Data Storage Formats </center></h1>
## Describing Switches and Groups of Switches

- [Representing Switches with Bits]: 
	
	- [Decimal Systems]: Uses 10 digits, 0-9, to write numbers.
		
	- [Binary Systems]: A two-digit system that uses 0 (off state) and 1 (on state) that is commonly called *binary digit* and shorted to *bit* and used to represent the state of the switch.
	
- [Representing Groups of Bits]: 
	
	- [Hexadecimal]: A 16 digits systems with each of the digit can represent one group of 4 bits.
		
	- [Octal Systems]: A 8 digit systems, from 0-7, with each digit resembling a group of 3 bits. 
	
- [Using Hexadecimal Digits]: 
	
	- Hexadecimal digits are especially convenient when we need to specify the state of a group. 




