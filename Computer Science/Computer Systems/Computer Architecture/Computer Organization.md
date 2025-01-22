
<h2 style="color:#6290C3"><center> The Baseline </center></h2>
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

<h2 style="color:#6290C3"><center> Data Storage Formats </center></h2>
## Describing Switches and Groups of Switches

- [Representing Switches with Bits]: 
	
	- [Decimal Systems]: Uses 10 digits, 0-9, to write numbers.
		
	- [Binary Systems]: A two-digit system that uses 0 (off state) and 1 (on state) that is commonly called *binary digit* and shorted to *bit* and used to represent the state of the switch.
	
- [Representing Groups of Bits]: 
	
	- [Hexadecimal]: A 16 digits systems with each of the digit can represent one group of 4 bits.
		![[Pasted image 20250114135814.png]]![[Pasted image 20250114135835.png]]
		
	- [Octal Systems]: A 8 digit systems, from 0-7, with each digit resembling a group of 3 bits. 
		![[Pasted image 20250114140110.png]]
	
- [Using Hexadecimal Digits]: 
	
	- Hexadecimal digits are especially convenient when we need to specify the state of a group. But a single bit isn't usually useful for storing data, we uses Byte instead.
		
	- [Byte]: The smallest number of bits that can be accessed at a time in a computer.

## Mathematical Equivalency of Binary and Decimal

- [Positional Notation]: The value of a symbol depends on its position within a group of symbols.
	`123 = 1 * 10^2 + 2 * 10^1 + 3 * 10^0`
	
	- [Least significant digit]: A digit where its values contributed the least to the number's total value.
		`3 in 123`
		
	- [Most significant digit]: A digit where its values contributed the most to the number's total value.
		`1 in 123`
		
	- [Base / Radix]: The number of unique digit. 10 for Decimal Number System.
		
	- [Signed / Unsigned Number]: Signed number can either be negative or positive, Unsigned number have no sign.
		
	- #HonorableMention: Roman Numbering System.
	
- [Converting Binary to Unsigned Decimal]:
	
	- Binary to Decimal can be converted by computing the value of 2 raised to the power of its position it is in then multiplying that be the value of the bit in that position.
		![[Pasted image 20250114142930.png]]
	- The following algorithm summarizes the procedure for converting binary to decimal:
		![[Pasted image 20250114143133.png]]
	
- [Converting Unsigned Decimal to Binary]: We can produce the binary representation of a number by working from right to left, repeatedly dividing by, and using the remainder as the value of the respective bit. 
	![[Pasted image 20250114154739.png]]

## Storing Data in Memory 

- There are two generals kinds of memory used for storing program instructions and data in a computer: **RAM (Random Access Memory)** which is volatile and it takes the same amount of time to access any byte in memory, **ROM (Read-only Memory)** which is non-volatile memory (NVM). **SAM (Sequential Access Memory)** means that the amount it takes to access a byte depends on its position.
	
- [Express Memory Address]:
	
	- Each byte in memory has a location, or address, much like the room number in an office building. The address of specific byte never changes but their state will which can either be 0 or 1. Computer Scientist typically express the address of each byte in memory in hexadecimal. This means that the first 16 bytes in memory have the addresses: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, a, b, c, d, e, f. Using the notation: 
		`<address>:<content`
		![[Pasted image 20250114162322.png]]
	- The content of each byte is represented by two hexadecimals digits, which specify the exact state of byte's eight bits.
	
- [Characters]: Text Strings
	
	- [Character Encoding]: 
		
		- The most common standard for encoding characters for computer storage is `UNICODE UTF-8` (Unicode Transformation Format). It uses  from one to four bytes for storing a number called a **code point**, which represent a character. 
			UTF-8 for the Hexadecimal Characters![[Pasted image 20250114182100.png]]
		- A Unicode code point is written as `U+h`, where h is four to six hexadecimal digits.
			
		- The operating systems and display hardware associate one or more code points with a **glyph**, which is what we see on the screen or on paper.
			
		- American Standard Code for Information Interchange (`ASCII`) uses seven bits to specify each code point in a 128-character set, which contains the English alphabet, numerals, special characters, and control characters.
			
		- UTF-8 uses one byte per character to store code points U+0000 to U+007F. Bits 6 and 5 in the byte (numbered from right to left) specify the four group of characters, these special characters are mostly punctuation.
			![[Pasted image 20250114182434.png]]
		- To generate a table of code points that coincide with ASCII characters, type `man ascii` in Linux Terminal
		
	- [Storing a Text String]: Text string are stored by the **compiler** as a constant array of characters. To specify the extent of this array, a C-style string uses the code point U+0000 (ASCII NUL) at the end of the string as a **sentinel value**, a unique value that indicates the end of a sequence of characters.
	
- [Unsigned Integers]: 
	
	- Unsigned Integer can be expressed in any radix/base, the most obvious way is to store it in Binary Number System. If we number the bits in a byte from right to left, then the lowest-order bit would be stored in bit 0, the next in bit 1, and so forth.
		
	- The default size for an unsigned integer in most programming environment is 4 bytes = 4,294,967,295 base 10.
		
	- One limitation of binary number systems is that you need to convert a decimal number from a character string to the binary number system before performing arithmetic operations on it.
		
	- **Binary COded Decimal (BCD)** is another code for storing integer, it uses four bits for each decimal digits.
		![[Pasted image 20250114184401.png]]
	- BCD is useful when it comes to printing a lot of numbers.
	
- [Understanding Byte Storage Order in Memory]:
	
	- [Little Endian]: Data is stored in memory with the *least* significant byte in a multiple-byte value in the lowest-numbered address. That is, the "littlest" byte comes first in memory.
		
	- [Big Endian]: Data is stored in memory with the *most* significant byte in a multiple-byte value in the lowest-numbered address. That is, the "biggest" byte comes first in memory.

<h2 style="color:#6290C3"><center> Computer Arithmetic </center></h2>
## Adding and Subtracting Unsigned Integers

- [Adding in the Decimal Number System]: 
	![[Pasted image 20250117220727.png]]
- [Subtracting the Decimal Number Systems]:
	
	





