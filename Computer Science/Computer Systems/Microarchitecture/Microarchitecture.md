Also Called **Computer Organization**
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
	![[Pasted image 20250128124322.png]]
- [Adding and Subtracting Unsigned Integers in Binary]: Can be tedious if another bytes needs to be borrowed when performing calculation.

## Adding and Subtracting Signed Integer

- Calculation in signed integer tends to be incorrect due to the "sign magnitude code" which result in arithmetically incorrect.
	
- [Two Complement]: The complement of a quantity is the amount that must be added to make it "whole". When it comes to computers, it based on the radix (base) and the number of digits that allow you to represent the numbers.
	`-2^(n-1) =< x <= +(2^(n-1) - 1)`
	
- [Computing Two's Complement]: Starting with the binary representation of the number, invert the bits following the one's complement and add one to the result.
	
- [Circular Nature of Integer Codes]: For a given number of bits, each code "wraps around".
	![[Pasted image 20250128132808.png]]
	- Steps:
		
		- Pick the ring corresponding to the type of integer you're using.
			
		- Move the location on that ring corresponding to the first integer.
			
		- Move along the ring, moving the number of "spokes" equal to the second integer. Move clockwise to add, and move counterclockwise to subtract.
	
- [Binary arithmetic]: Computers perform addition and subtraction in the binary number system. Addition of two numbers may yield a result that is one bit wider than each of the two numbers. Subtraction of one number from another may require borrowing from one bit beyond the width of the two numbers.
	
- [Representing signed/unsigned]: Bit patterns can be treated as representing either signed or unsigned integers. Two’s complement notation is commonly used to represent signed integers.
	
- [Carry Flag]: The CPU includes a one-bit carry flag that shows whether the result of addition or subtraction exceeds the number of bits allowed for an unsigned integer.
	
- [Overflow flag]: The CPU includes a one-bit overflow flag that shows whether the result of addition or subtraction exceeds the number of bits allowed for a signed integer using the two’s complement notation.

<h2 style="color:#6290C3"><center> Boolean Algebra </center></h2>
## Basic Boolean Operators

- A Boolean operator acts on a value, or pair of values, called the operands
	
- [Truth Table]: A table that shows the results for all possible combinations of the operands.
	![[Pasted image 20250130165103.png]]
- [Gates]: Electronic devices that implement the Boolean operators.
	
	- [AND]: A *binary operator* that result in 1 if and only if both operands are one; otherwise, the result is 0. Some times also called a *Conjunction*.
		![[Pasted image 20250130165512.png]]
		
	- [OR]: A *binary operator* that results in 1 if at least one of the operands is 1; otherwise the result is 0. Some times also called a *Disjunction*.
		![[Pasted image 20250130165744.png]]
		
	- [NOT]: A *unary operator*, which acts on only one operand. The result of NOT is 1 if the operand is 0, vice versa. Other name for NOT is *complement* and *invert*.
		![[Pasted image 20250130170014.png]]	

## Boolean Algebra Rules

### Boolean Algebra Rules That Are the Same as Elementary Algebra

- [AND and OR are associative]: Means that there are two or more occurrences of the operator in an expression, the order of applying the operator does not change the value of the expression. Mathematically: 		
	![[Pasted image 20250130170511.png]]![[Pasted image 20250130170607.png]]![[Pasted image 20250130170630.png]]
	
- [AND and OR have identity values]: Means that their identity value is a value specific to an operation such that using that operation on a quantity with the identity value yields the value of the original quantity. 
	![[Pasted image 20250130171016.png]]
	
- [AND and OR are commutative]: The order of its operands are reversible.
	![[Pasted image 20250130171130.png]]
	
- [AND is distributive over OR]: The AND operator applied to quantities OR-ed together can be *distributed* to apply to each of the OR-ed quantities.
	![[Pasted image 20250130171519.png]]
	
- [AND has an annulment (annihilation) value]: Operating on a value with the operator's annulment value yields the annulment value.
	![[Pasted image 20250130184745.png]]
	
- [NOT shows involution]: An operator show *involution* if applying it to a quantity twice yields the original quantity.

### Boolean Algebra Rules That Differ from Elementary Algebra

- [OR is distributive over AND]: The OR operator applied to quantities AND-ed together can be distributed to apply to each of the AND-ed quantities.
	![[Pasted image 20250130185327.png]]![[Pasted image 20250130185622.png]]
	
- [OR has an annulment value]: An *annulment value* is a value such that operating on a quantity with the annulment value yields the annulment value. For OR it is 1.
	![[Pasted image 20250130185805.png]]
	
- [AND and OR both have complement value]: The *complement value* is the diminished radix complement of the variable. In boolean algebra the complement of 1 is 0 and vice versa.
	![[Pasted image 20250130185936.png]]
	
- [AND and OR are idempotent]: If an operator is *idempotent*, applying it to two of the same operands results in that operands.
	![[Pasted image 20250130190223.png]]
	
- [De Morgan's law applies]: Boolean algebra states that if you replace every 0 with 1, every 1 with a 0, every AND with an OR, and every OR with an AND, the equation will still be true.
	![[Pasted image 20250130190427.png]]

## Boolean Functions

- A Boolean Functions looks somewhat like an elementary algebra function, but the variables can appear in either uncomplemented or complemented form. The variables and constants are connected by Boolean operators. A Boolean function evaluates to either 1 or 0.
	
- [Canonical Sum or Sum of Minterms]: 
	
	- [Canonical Form]: A canonical form of a Boolean function explicitly shows whether each variable in the problem is complemented or nor in each term that defines the function.
		
	- [Product terms]: Terms where all the literals are operated on only by AND.
		
	- An equation that has n variable has 2^n permutations of the values for the variable.
		
	- [minterm]: A product term that specifies exactly one of the permutations
		
	- A Boolean function that is defined by summing (OR-ing) all the minterms that evaluate to 1 is said to be a canonical sum, a sum of minterms, or in full disjunctive normal form. A function defined by a sum of minterms evaluates to 1 when at least one of the minterms evaluate to 1.
	
- [Canonical Product or Product of Maxterms]: 
	
	- [sum terms]: Terms where all the literals are operated on only by OR.
		
	- [conjunctive normal form]: A product of sums.
		
	- [maxterm]: A sum term specifying exactly one of those permutations.
		
	- A Boolean function that is defined by multiplying (AND-ing) all the maxterms that evaluate to 0 is said to be a canonical product, a product of maxterms, or in full conjunctive normal form.
	
- [Comparison of Canonical Boolean Forms]:
	![[Pasted image 20250206154234.png]]

## Boolean Expression Minimization

### Minimal Expressions

- When simplifying a Boolean function, start with one of the canonical forms to ensure you have taken all of the possible cases into account. Create a truth table that list all possible combinations of the variables in the problem. List the minterms and maxterms.
	
- [Minimal Expression]: an expression that does the same thing as the canonical one, but with a minimum number of literals and Boolean operators.
	
- Too minimize an expression, we apply the rules of Boolean algebra to reduce the number of terms and the number of literals in each term.
	
- [Minimal Sum of Products]: A sum of products expression where all other mathematically equivalent sum of products expression have at least as many product terms, and those with the same number of product terms have at least as many literals.
	
- [Minimal Product of Sums]: A product of sums expression where all other mathematically equivalent product of sums expressions have at least as many sum terms, and those with the same number of sum terms have at least as many literals.

### Minimization Using Algebraic Manipulations

- By using idempotency rule, distribution, the complement properties, substitutions. 

### Minimization using Karnaugh Maps

- [Karnaugh Maps]: A rectangular grid with a cell for each minterm. There are 2 ^ n cells for n variables.
	
- [Simplifying Sums of Products using Karnaugh Maps]: You group two adjacent cells in a sum of products karnaugh map that have 1s in them. Then you eliminate the variable that differs between them and coalesce the two product terms. Repeating this process allows you to simplify the equation. Each grouping eliminates a product term in the final sum of products. This can be extended to no equations with more than two variables, but the number of cells that are grouped together must be a multiple of 2, and you can group only adjacent cells. The adjacency wraps around from side to side and from top to bottom.
	
- [Karnaugh Map Cell Order]: Follows the Gray Code.
	![[Pasted image 20250206184048.png]]![[Pasted image 20250206184109.png]]
- [Karnaugh Map for Three Variable]: Adding another variable means that we need to double the number of cells to hold the minterms. To keep the map two-dimensional, we add the new variable to an existing variable on one side of the map. We need a total of eight cells (23), so we’ll draw it four cells wide and two high. We’ll add z to the y-axis and draw our Karnaugh map with y and z on the horizontal axis, and x on the vertical.
	
- [Simplifying Products of Sums using Karnaugh Maps]: Using maxterms, complement, and comparison.
	
- [Larger Groupings on a Karnaugh Map]
	
- [Adding More Variables to a Karnaugh Map]: Each time you add another variable to Karnaugh Map, you need to double the number of cells. The only requirement for the Karnaugh map to work is that you arrange the minterms or maxterms, according to the adjacency rule.
	
- [Don't Care Cells]: Are cells that no matter the combination the value never occur, or known as irrelevant.

## Combining Basic Boolean Operators

- [XOR]: The XOR is a binary operator. The result is 1 if one, and only one, of the two operands is 1; otherwise, the result is 0.

<h2 style="color:#6290C3"><center> Logic Gates </center></h2>
## Crash Course

- [Current]: The movement of electrical charge, measured in *Coulombs*. A flow of one coulomb is *ampere*, often abbreviated as *amp*. Current flow through an electrical circuit only if there is a completely connected path from one side of the power source to the other side.
	
- [Voltage]: The difference in electrical energy per unit charge, *potential difference*, between two points in an electrical circuit. One *volt* is defined as the electrical difference between two points on a *conductor* when one ampere of current flowing through the conductor dissipates one watt of power.
	
- A computer consist of: 
	
	- Power source that provide electrical power.
		
	- Passive components that affect current flow and voltage levels, but whose characteristics cannot be altered by another electronic component.
		
	- Active components that switch between various combinations of the power source, passive components, and other active components under the control of one or more other electronic components.
		
	- Conductors that connect the other components together.
	
- [Power Supplies and Battery]: Electrical power comes in the form of alternating current (AC), have a sinusoidal plot, most computer circuits use direct current (DC) power. A power supply is used to convert AC to DC. A battery provides DC power.
	
- [Passive Components]: 
	
	- [Resistance]: Impedes current flow, thus dissipating energy. The electrical energy is transformed into heat.
		
	- [Capacitance]: Stores energy in an electrical field. Voltage across a capacitance cannot change instantaneously.
		
	- [Inductance]: Stores energy in a magnetic field. Current through an inductance cannot change instantaneously.
		 
	- [Switches]: Act as a bridge, has two form, open or closed.
		
	- [Resistors]: Used to limit the amount of current in a specific location in a circuit. By limiting the current flow into a capacitor or inductor, a resistor affects the time it takes for these other devices to build up their energy storage.
		
	- [Capacitors]: Stores energy in a form of an electric field, which is essentially the electric charge at rest.
		
	- [Inductors]: Stores energy in the form of a magnetic field, which is created by electric charge in motion.
		
	- [Power Consumption]: Energy is the ability to cause change, and power is a measure of how fast energy can be used to make the change. The basic unit of energy is a joule. The basic unit of power is a watt, which is defined as expending one joule per second. Resistance is the primary consumer of power. 

## Transistors

- [Transistors]: A device whose resistance can be controlled electronically. 
	
- [MOSFET Switch]: The most commonly used switching transistor in today’s computer logic circuits is the metal-oxide-semiconductor field-effect transistor (MOSFET).
	
	- The basic material in a MOSFET is typically silicon, which is a semiconductor, meaning it conducts electricity, but not very well. Its conductivity is improved by adding an impurity, a process called doping. Depending on the type of impurity, the electrical conductivity can be either the flow of electrons or the flow of lack of electrons (called holes). Since electrons have a negative electrical charge, the type that conducts electrons is called N-type, and the type that conducts holes is called P-type. The main conduction path through a MOSFET is the channel, which is connected between the source and the drain terminals on the MOSFET. The gate is made from the opposite type of semi-conductor. The gate controls the conductivity through the channel.
		
	- Each MOSFET has three connection points, or terminals. The gate is used as the input terminal. Voltage applied to the gate, relative to the volt- age applied to the source, controls current flow through the MOSFET. The drain is used as the output. The source of an N-channel MOSFET is connected to the lower voltage of the power supply, and the source of a P-channel is connected to the higher voltage.
		![[Pasted image 20250206205928.png]]
	
- [N-Channel MOSFET]: When the voltage applied to the gate is positive with respect to the source, the resistance between the drain and the source of the N-channel MOSFET decreases. When this voltage reaches a threshold value, typically in the range of 1 volt, the resistance becomes very low, thus providing a good conduction path for current between the drain and the source.If the voltage applied to the gate is switched to be nearly the same as the voltage applied to the source, 0 volts, the MOSFET turns off.
	
-  [P-Channel MOSFET]: When the voltage applied to the gate is switched to be nearly the same as the voltage applied to the source, the MOSFET turns off. In this case, the resistor, R, acts as a pull-down device, to pull the voltage on the drain down to 0 volts. When the voltage applied to the gate is negative with respect to the source, the resistance between the drain and source of the P-channel MOSFET decreases. When this voltage reaches a threshold value, typically in the range of –1 volt, the resistance becomes very low, thus providing a good conduction path for current between the drain and the source.
	
- [CMOS Switch]: The P-channel will replace the pull-up resistor in the N-channel circuit, and the N-channel will replace the pull-down resistor in the P-channel circuit.
	![[Pasted image 20250206205951.png]]
	- The two main advantages of using CMOS circuits are:
		
		- They consume very little power. Because of the switching speed difference between N-channel and P-channel MOSFETs, only a small amount of current flows during the switching period. Less current means less heat, which is often the limiting factor in chip design.
			
		-  The circuit responds much faster. A MOSFET can supply the current at its output faster than a resistor, charging the gate of the following MOSFET. This allows us to build faster computers.

## NAND and NOR Gates

- [NAND]: A binary operator that gives a result of 0 if and only if both operands are 1 and gives 1 otherwise.
	![[Pasted image 20250206210159.png]]
- [NOR]: A binary operator that gives a result of 0 if at least one of the two operands is 1 and gives 1 otherwise.
	![[Pasted image 20250206210308.png]]

## NAND as a Universal Gate

- One of the interesting properties about NAND gates is that they can be used to build AND, OR, and NOT gates. This means the NAND gate can be used to implement any Boolean function. In this sense, you can think of the NAND gate as a universal gate.
	![[Pasted image 20250206210404.png]]![[Pasted image 20250206210421.png]]![[Pasted image 20250206210428.png]]
- The conversion from an AND/OR/NOT gate design to one that uses
	only NAND gates is straightforward:
	
	- Express the function as a minimal sum of products.
		
	- Convert the products (AND terms) and the final sum (OR) to NANDs.
		
	- Add a NAND gate for any product with only a single literal.

<h2 style="color:#6290C3"><center> Combinational Logic Circuits </center></h2>
## The Two Classes of Logic Circuits

- [Combinational]: A combinational logic circuits has output that depends only on the inputs given at any specific time and not on any previous inputs.
	
- [Sequential]: A sequential logic circuit has outputs that depend both on previous and current inputs.

## Adders

- [Half Adders]: Simply adds the two bits in the current bit position of a number (expressed in binary). Only work with two inputs bits and does not take into account of a possible carry.
	![[Pasted image 20250213142257.png]]
- [Full Adder]: Has three one-bit inputs, Carry, xi, and yi. Carry is the carry that resulted when you added two bits in in the previous bit position.
	![[Pasted image 20250213142453.png]]![[Pasted image 20250213142535.png]]![[Pasted image 20250213142543.png]]![[Pasted image 20250213142743.png]]
- [Full Adder from Two Half Adder]:
	![[Pasted image 20250213142937.png]]
- [Ripple-Carry Addition and Subtraction Circuits]:
	![[Pasted image 20250213143313.png]]![[Pasted image 20250213143325.png]]

## Decoders

- [Decoder]: Process the 4 bits of the the register, and the output is one of n possible connections to the specified register.
	
- The decoder has n binary inputs that can produce up to 2^n binary outputs.
	
- [Line Decoder]: Selects only one of the output lines to set to 1 for each input bit pattern.
	![[Pasted image 20250213143812.png]]![[Pasted image 20250213143828.png]]
- Decoders are more versatile because each input can be seen as a minterm.
	![[Pasted image 20250213144049.png]]

## Multiplexers

- [Multiplexers]: A device that can switch between 2^n input lines by using n selection lines.
	![[Pasted image 20250213144506.png]]
- [Tristate Buffers]: A buffer that has 3 states: 0, 1, and "no connection".The “no connection” output is actually a high impedance connection, also called high Z or open. The “no connection” output lets us physically connect the outputs of many tristate buffers together but select only one to pass its input to the common output line. A tristate buffer has both a data input and an enabling feature. 
	![[Pasted image 20250213145748.png]]![[Pasted image 20250213145803.png]]![[Pasted image 20250213145841.png]]![[Pasted image 20250213150006.png]]

## Programmable Logic Devices

- PLDs, Programmable Logic Devices, contains many AND and OR gates which can be programmed to implement Boolean Functions. The inputs, and their complemented value, are connected to the AND gates. The AND gates, taken together, are referred to as the AND plane, or AND array. The outputs of from the AND gates are connected to OR gates, which taken together are referred to as the OR plane, or OR array. Depending on the type, one or both planes can be programmed to implement combinational logic. When using a PLD, a design change means only changing how the device is programmed, not buying different devices, meaning the circuit board does not need to be redesigned.
	
- [Programmable Logic Array]: Both AND and OR planes are programmable. PLAs are used to implement logic functions.
	![[Pasted image 20250213150904.png]]
	- Each input variable, in both its uncomplemented and complemented form, is an input to the AND gates through fuses. A fuse is a thin piece of conductor used to protect an electrical circuit. If the current flowing through it is high enough, the conductor melts, thus opening the circuit and stop- ping current flow. PLDs can be programmed by breaking (or blowing) the appropriate fuses, thus removing the input to the logic gate. Some devices use antifuses instead of fuses. These are normally open, and programming them consists of completing the connection instead of removing it. Devices that can be reprogrammed have fuses that can be broken and then remade.
	![[Pasted image 20250213151354.png]]
- [Read-Only Memory]: Used to store bit patterns that can represent data or program instructions. A program can only read the data or program stored in ROM, but the contents of the ROM cannot be changed by writing new data or program instructions to it.
	
	- ROM can be implemented as a programmable logic device where only the OR gate plane can be programmed. The AND gate plane remains wired to provide all the minterms. We can think of the inputs to the ROM as addresses. Then the OR gate plane is programmed to provide the bit pattern at each address.
	![[Pasted image 20250213151803.png]]
	- The “×” connections in Figure 6-17 represent permanent connections, showing that the AND gate plane is fixed. Each AND gate produces a minterm at each address in this ROM. The OR gate plane produces up to 2n eight-bit bytes, where n is the width, in number of bits, of the address input to the AND gate plane. The connections (dots) to the OR gates represent the bit pattern stored at the corresponding address.
	
- [Programmable Array Logic]: In a programmable array logic (PAL) device, each OR gate is permanently wired to a group of AND gates. Only the AND gate plane is programmable.
	![[Pasted image 20250213152114.png]]

<h2 style="color:#6290C3"><center> Sequential Logic Circuits </center></h2>
- [System State]: A description of the system such that knowing the state at time t0 and the inputs from time t0 through time t1, uniquely determines the state at time t and the outputs from time t0 through time t1. 
	
- [Finite State Machine]: A mathematical model of computation that can exist in any one of a finite number of states. If a sequential logic circuit is designed such that its output depends only on the state it’s in, it’s called a Moore state machine. If the output also depends on the input causing a transition to a state, it’s called a Mealy state machine.
## Latches

- A one-bit storage device that can be in one of two states, depending on its input. A latch can be constructed by connecting two or more logic gates such that the output from one gate is fed back into the input of another gate; this keeps the out- put of both gates in the same state as long as power is applied.
	
- [SR Latch using NOR gates]: The most basic latch is the Set-Reset (SR). It has two inputs (S and R) and two states, called Set and Reset. The state is used as the primary output, Q. It’s common to also provide the complemented output, ¬Q. The SR latch is said to be in the Set state when the outputs Q = 1 and ¬Q = 0. It’s in a Reset state when Q = 0 and ¬Q = 1.
	![[Pasted image 20250227155501.png]]
	- This result in 4 different state:
		`S = 0, R = 0. Keep current state.`
		`S = 1, R = 0. Set (Q = 1).`
		`S = 0, R = 1. Reset (Q = 0).`
		`S = 1, R = 1. Not allowed.`
	![[Pasted image 20250227155742.png]]![[Pasted image 20250227155803.png]]
	
- [SR Latch using NAND Gates]: 
	![[Pasted image 20250227160332.png]]
	- There are 4 different state:
		`¬S = 1, ¬R = 1: Keep current state`
		`¬S = 0, ¬R = 1: Set (Q = 1)`
		`¬S = 1, ¬R = 0: Reset (Q = 0)`
		`¬S = 0, ¬R = 0: Not allowed`
	![[Pasted image 20250227160459.png]]![[Pasted image 20250227160509.png]]
- [SR Latch with Enable]: We can get better control over the SR latch by adding two NAND gates to provide an Enable input. Connecting the outputs of these two NAND gates to the inputs of an ¬S¬R latch gives us a gated SR latch.
	![[Pasted image 20250227161656.png]]![[Pasted image 20250227161851.png]]
- [The D Latch]: A D latch allows us to store the value of one bit.
	![[Pasted image 20250227163106.png]]![[Pasted image 20250227163115.png]]

## Flip-Flops

- A one bit storage device designed to accept an input during one portion of the clock signal and then lock the output to a single value throughout the duration of the other portion if the clock signal.
	
- [Clocks]: A device that provides an electronic clock signal, typically a square wave that alternates between the 0 and 1 levels. This signal is used as the enabling/disabling input to devices that needs to be synchronized. 
	![[Pasted image 20250227164430.png]]
- [D Flip-Flop]: The uncomplemented output of the Primary D latch is fed to the S input, and its complemented output is fed to the R input of the Secondary SR latch, effectively making the Secondary a D latch without requiring a NOT gate at the R input.
	![[Pasted image 20250227165336.png]]![[Pasted image 20250227165820.png]]![[Pasted image 20250227165835.png]]
- [T Flip-Flop]: Toggleable switches using a flip-flop that simply complements its state. To construct a T flip-flop from a D flip-flop, we need to feed the output back and combine it with the input to the D flip-flop.
	![[Pasted image 20250227165937.png]]![[Pasted image 20250227170208.png]]
- [JK Flip Flop]: Implementing all four possible actions—set, reset, keep, toggle—requires two inputs, J and K, giving us the JK flip-flop.
	![[Pasted image 20250227170244.png]]![[Pasted image 20250227170301.png]]![[Pasted image 20250227170322.png]]![[Pasted image 20250227170333.png]]![[Pasted image 20250227170343.png]]

<h2 style="color:#6290C3"><center> Memory </center></h2>
## The Memory Hierarchy

- The closer the memory is to the CPU the fast and more expensive it will be. 
	![[Pasted image 20250306131728.png]]
	- The top three layers is typically included int the CPU.
		
	- There are maybe one or two more levels of cache before getting into the main memory.
		
	- The main memory and disk are usually in the same enclosure with the CPU, which may include more than one disk.
		
	- Next layer represent offline storage devices.
		
	- The final line is online storage. 
	
- [Mass Storage]: Used for keeping programs and large amounts of data in a machine-readable format. This includes hard disks, solid state drives, memory sticks, optical disks, etc. Their content is *nonvolatile*, meaning that if the computer is turn off, the content remain. They also are slow compared to the CPU. Accessing their contents requires explicit programming.
	![[Pasted image 20250306132333.png]]
- [Main Memory]: Often called RAM, volatile, meaning the content is erased when the computer is turned off. The main memory communicates with the CPU using data, address, and control buses. It as synchronized in the hardware with the CPU, this means that the programmer can access items in the memory via specifying the address.
	
	- Only a portion of the data is loaded when the computer is turned on, and only a portion currently being worked on is loaded from mass storage to main memory. And since they are loaded into memory, loading from mass storage is not needed therefore increasing execution speed.
		
	- Most organization of main memory store both program instructions and data. Which introduce the *von Neumann bottleneck*, that is if an instructions calls for reading from, or writing data to, memory, the next instruction in the program sequence cannot be read from memory over the same bus until the current execution has completed the data transfer. This was partially resolve by *Harvard Architecture* which store data in different memories, allows for simultaneous access. 
	
- [Cache Memory]: Provides a much faster location for the instructions and variables currently being processed by the program. 
	
	- Cache memory is organized in levels, as the level increase the cache gets bigger and further away from the CPU. 
		
	- Cache is checked first. If data exist in higher level cache, it is copied to the lower level then into the CPU.
		
	- [Line]: The amount of memory copied into a cache at a time.
		
	- When data is written into main memory, it starts with the lowest cache (Level 1), then to the next level (Level 2), and so on. 
		
	- The time decrease as a exponential of 10^n as the cache level increases. 
		
	- [Locality of Reference]: The tendency of a program to reference nearby memory addresses in a short period of time. Simply, shows the effectiveness of cache based on the location.
	
- [Registers]: The fastest memory. They’re mainly used for numerical computations, logical operations, temporary data storage, and similar short-term operations. They are also very specific to the particular architecture and usage.

## Implementing Memory in Hardware

- [Four Bit Register]:
	![[Pasted image 20250306134711.png]]![[Pasted image 20250306134751.png]]
- [Shift Register]: We can use a shift register as a serial-in parallel-out (SIPO) device. A shift register uses a sequence of D flip-flops, like the simple storage register, but the output of each flip-flop is connected to the input of the next flip-flop in the sequence.
	![[Pasted image 20250306135414.png]]
- [Register File]: Grouped register that are used for similar operations.
	![[Pasted image 20250306141819.png]]
- [Read Write Memory]:
	![[Pasted image 20250306141912.png]]
- [Static Random Access Memory]: Uses flip-flops to store bits. SRAM is fast, but expensive. It is called static because it maintains its values so long as power is maintained, it is called random because it takes the same amount of time to access any random byte in the memory. SRAM is used for cache memory. 
	![[Pasted image 20250306142138.png]]![[Pasted image 20250306142152.png]]
- [Dynamic Random-Access Memory]: Uses capacitors to store bits. DRAM is slow, but has a much lower cost. A bit in DRAM is commonly implemented by a charging a capacitor to one of two voltages.
	![[Pasted image 20250306142317.png]]
	- When the Row Select line is set to 1, all the transistors in that row are turned on, thus connecting the respective capacitor to the Sense Amplifier/Latch. The value stored in the capacitor, high voltage or low voltage, is amplified and stored in the latch. There, it’s available to be read. Since this action tends to discharge the capacitors, they must be refreshed from the values stored in the latch. Separate circuitry is provided to do the refresh. 
		
	- When data is to be stored in DRAM, the new bit value, 0 or 1, is first stored in the latch. Then Row Select is set to 1, and the Sense Amplifier/Latch circuitry applies the voltage corresponding to the logical 0 or 1 to the capacitor. The capacitor is either charged or discharged appropriately.

<h2 style="color:#6290C3"><center> Central Processing Unit </center></h2>
## CPU Overview

- [CPU Subsystems]: The subsystems are connected through internal buses, which include the hardware pathways and the software protocols that control the communication.
	![[Pasted image 20250313142223.png]]
	- [Instruction Pointer]: This register always contains the memory address of the next instruction to be executed.
		
	- [Cache Memory]: Although it could be argued that this is not part of the CPU, most modern CPUs include very fast cache memory on the CPU chip. The CPU can execute instructions much faster than it can fetch them from main memory through the bus interface. The interface with main memory makes it more efficient to fetch several instructions at one time, storing them in cache memory where the CPU has fast access to them.
		
	- [Instruction Register]: This register contains the instruction currently being executed. Its bit pattern determines what the control unit is causing the CPU to do. Once that action is completed, the bit pattern in the instruction register will be changed to that of the next instruction, and the CPU will perform the operation specified by this new bit pattern.
		
	- [Register File]: A register file is a group of registers used in a similar ways. Most CPUs have several register files. Compilers and assemblers have names for each register. Almost all arithmetic and logic operations and data movement operations involve at least one register in a register file.
		
	- [Control Unit]: The bits in the instruction register are decoded in the control unit. To carry out the action specified by the instruction, the control unit generates the signals that control the other subsystems in the CPU. It's typically implemented as a finite-state machine and contains decoders, multiplexers, and other logic components.
		
	- [Arithmetic Logic Unit (ALU)]: Used to perform the arithmetic and logic operations you specify in your program. It is also used by the CPU when it needs to do its own arithmetic.
		
	- [Status Register]: Each operation performed by the ALU results in various conditions that must be recorded for possible use by the program.
		
	- [Bus Interface]: This is how CPU communicates with the other computer subsystems. It contains circuitry to place addresses on the address bus, read and write data on the data bus, and read and write signals on the control bus. The bus interface on many CPUs interfaces with external bus control units that in turn interface with memory and with different types of I/O buses.
	
- [Instruction Execution Cycle]: It does this by fetching the instructions form main memory using the three buses-address, data, and control-through the bus interface.
	
	- The address in the instruction pointer register, rip, always points to (has the memory address of) the next instruction in a program to be executed. The CPU works its way through a program by fetching the instruction from the memory address in the instruction pointer. When an instruction is fetched, the CPU starts to decode it. The first byte or two, depending on the instruction, tell the CPU the number of bytes in the instruction. The CPU then increments the rip register by this number, causing the rip to contain the address of the next instruction in the program. Thus, the rip marks the current location in a program.
		
	- There are instructions that change the address in the rip, thus causing a jump from one place in the program to another. In this case, the address of the next instruction is not known until the instruction that causes the jump is actually executed.
		
	- The steps to fetch each instruction from memory, and thus to execute a programs:
		1. A sequence of instructions is stored in memory.
		2. The memory address where the first instruction is located is copied to the instruction pointer.
		3. The CPU sends the address in the instruction pointer to memory on the address bus.
		4. The CPU sends a "read" signal on the control bus.
		5. The memory responds by sending a copy of the state of the bits at that memory location on the data bus, which the CPU then copies into its instructions register.
		6. The instruction pointer is automatically incremented to contain the address of the next instruction in memory.
		7. The CPU executes the instruction in the instruction register.
		8. Go back to step 3.
		![[Pasted image 20250313144352.png]]
	- Most instructions in a program use at least on register in at least one of the register files. A program typically loads data from memory into a register, operates on the data, and stores the result in memory. Registers are also used to hold addresses of items that are stored in memory, thus serving as pointers to data or other addresses.

## x86_64 Register

![[Pasted image 20250313144722.png]]![[Pasted image 20250313144733.png]]
- [General Purpose Register]: Deal with the integral data types and memory addresses. Each bit in the register is numbered from right to left, beginning with 0. So, the rightmost bit is number 0, the next one to the left is 1, and so on. Since there are 64 bits in each general purpose register, the leftmost bit is 63.
	
	- Each instruction in a computer treats a group of bits as a single unit, often called as *word*.
		1. Quadword: 64 bits (63-0)
		2. DoubleWord: The low-order 32 bits (31-0)
		3. Word: The low-order 16 bits (15-0)
		4. Byte: The low-order 8 bits (7-0), and in for register bit (15-8)
		![[Pasted image 20250313145907.png]]
	- Several instructions work only with specific general purpose registers.
	
- [Status Register]: Indicates a side effects of many instructions.
	![[Pasted image 20250313150653.png]]

## C/C++ Integral Data Types and Register Sizes

- [Data Type]: Specifies the possible values for the data types, the bit patterns used to represent those values, operations that can be performed on the data, and the data's semantic usage in the program.
	
- Some programming languages like C, C++, and Java require the programmer to explicitly state the data types of values used in the program. Other languages like Python, BASIC, and JavaScript can determine a data type from the way the value is used. CPU manufacturers specify machine-level data types specific to the CPU architecture, often including specialized data types that are unique to the design.
	
- The C and C++ language specifications provide ranges for values that can be stored in a variable of each data type. For example, an int must be able to store a value in the range –32,767 to + 32,767; thus, it must be at least 16 bits in size. An unsigned int must be at least 0 to 65,525, so it also must be at least 16 bits. Compiler designers are free to exceed the minimums specified in the language specifications.
	![[Pasted image 20250313151307.png]]
- A value can usually be represented with more than one data type.

## Using gdb to View the CPU Registers
- Using gdb to view the contents of the CPU register:
	![[Pasted image 20250313151722.png]]
	1. Using the register storage class modifier to request that the compiler use a CPU register for the feet and inchesRem variables.
	2. No register storage class modifier was used.
	3. The inches variable must be placed in a memory since scanf needs a pointer to the location of the inches to store the value read from the keyboard.
	
- When you hit a breakpoints in a program that has been running, here are some additional commands that you might find useful for moving through the program under your control and viewing information about the program
	
	- [n (next)]: Executes the current source code statement; if it’s a call to a function, the entire function is executed.
		
	- [s (step)]: Executes the current source code statement; if it’s a call to a function, step into the function, arriving at the first instruction of the called function.
		
	- [si (step instruction)]: Executes the current machine instruction; if it’s a call to a function, step into the function.
		
	- [i r (info register)]: Displays the contents of the registers, except the floating-point and vector registers.
	
- Using gdb to control the execution of the program and observe the register contents:
	![[Pasted image 20250313152949.png]]
	1. Compile the program
	2. Load it with gdb, and then list the source code to see where to set the breakpoint.
	3. Using the `ENTER` key repeats the previous command.

<h2 style="color:#6290C3"><center> Programming in Assembly Language </center></h2>
## Compiling a Program Written in C

- [Preprocessing]: This step resolves compiler directives such as `#include` (ﬁle inclusion), `#define` (macro deﬁnition), and `#if` (conditional compilation) by invoking the program cpp. The compilation process can be stopped at the end of the preprocessing phase with the `-E` option, which writes the resulting C source code to standard out. 
	
	- Standard out is usually the terminal window. You can redirect the output to a file with the > operator, like this:
		`$ gcc -Wall -O0 -masm=intel -E filename.c > filename.i`
		
	- The file extension `.i` denotes a file that does not require preprocessing.
	
- [Compilation]: Next, the compiler translates the source code that results from preprocessing into assembly language. The compilation process can be stopped at the end of the compilation phase with the `-S` option (upper- case S), which writes the assembly language source code to `filename.s.`
	
- [Assembly]: After the compiler generates the assembly language that implements the C source code, the assembler program, as, translates the assembly language into machine code. The process can be stopped at the end of the assembly phase with the `-c` option, which writes the machine code to an object file, named `filename.o`. Some call this assembler gas, for GNU assembler.
	
- [Linking]: The `ld` program determines where each function and data item will be located in memory when the program is executed. It then replaces the programmer’s symbolic names where each of these items is referenced with the memory address of the item. The result of this linking is written to an executable ﬁle. The default name of the executable file is a.out, but you can specify another name with the `-o` option.
	
- As you might know, if you don’t use any of the gcc options to stop the process at the end of one of these steps (-E, -S, -c), the compiler will perform all four steps and automatically delete the intermediate files, leaving only the executable program as the final result. You can direct gcc to keep all the intermediate files with the `-save-temps` option.
	
- The complement of being able to stop gcc along the way is that we can supply files that have effectively gone through the earlier steps, and gcc will incorporate those files into the remaining steps. If we supply only object files (.o), gcc will go directly to the linking step. An implicit benefit of this is that we can write programs in assembly language that call functions in the C standard library (which are already in object file format), and gcc will automatically link our assembly language with those library functions.
## From C to Assembly Language

- Programs written in C are organized into functions. Each function has a name that is unique within the program. After the C runtime environment is set up, the main function is called, so our program starts with main.
	```
	/* doNothingProg.c
	 * Minimum compoents of a C program.
	 */
	 
	int main(void)
	{
		return 0;
	}
	```
	
- Even though this program accomplishes very little, some instructions need to be executed just to return 0. To see what takes place, we ﬁrst trans- late this program from C to assembly language with the following GNU/ Linux command: 
	`gcc -O0 - Wall -masm=intel -S doNothingProg.c`
	
	- The `-O0` (uppercase O and zero) option tells the compiler not to use any optimization.
		
	- The `-Wall` option asks the compiler to warn you about questionable constructions in your code.
		
	- The `-masm=intel` option directs the compiler to generate assembly language using the Intel syntax instead of the default AT&T syntax.
		
	- The `-S` option directs the compiler to stop after the compilation phase and write the assembly language resulting from the compilation to a file with the same name as the C source code file, but with the .s extension instead of `.c`.
	```
		.file	"doNothingProg.c"
		.intel_syntax noprefix
		.text
		.globl	main
		.type	main, @function
	main:
	.LFB0:
		.cfi_startproc
		push	rbp
		.cfi_def_cfa_offset 16
		.cfi_offset 6, -16
		mov	rbp, rsp
		.cfi_def_cfa_register 6
		mov	eax, 0
		pop	rbp
		.cfi_def_cfa 7, 8
		ret
		.cfi_endproc
	.LFE0:
		.size	main, .-main
		.ident	"GCC: (GNU) 14.2.1 20250110 (Red Hat 14.2.1-7)"
		.section	.note.GNU-stack,"",@progbits
	```
		
	- Many of the identifiers begin with a `.` character. All of them, except the ones followed by a `:`, are **assembler directives**, also known as **pseudo-ops**. They are instructions to the assembler program itself, not computer instructions.
	
- [Unused Assembler Directives]: Are the `.cfi` that tell the assembler to generate information that can be used for debugging and certain error situations. The identifiers beginning with `.LF`, mark places in the code used to generate this information. To not include them write:
	`gcc -O0 -Wall -masm=intel -S -fno-asynchronous-unwind-tables doNothingProg.c`
	
	- Even without the `.cfi` directives, the assembly language still includes an instruction and several directives that won't be used.
		
	- [Control-flow Enforcement Technology (CET)]: Providing better defense against types of security attacks of computer programs that hijack a program's flow.
		
	- [endbr64]: Used as the first instruction in a function to check whether program flow gets there. The instruction has no effect if the CPU does not include CET.
		
	-  The compiler also needs to include some information for the linker to use CET. This information is placed in a special section of the file that the assembler will create, denoted with the `.section .note.gnu.property`,"a" assembler directive, after the actual program code.
		
	- This commands strips advanced features:
		`$ gcc -O0 -Wall -masm=intel -S -fno-asynchronous-unwind-tables \`
		`> -fcf-protection=none doNothingProg1.c`
	```
		.file	"doNothingProg.c"
		.intel_syntax noprefix
		.text
		.globl	main
		.type	main, @function
	main:
		push	rbp
		mov	rbp, rsp
		mov	eax, 0
		pop	rbp
		ret
		.size	main, .-main
		.ident	"GCC: (GNU) 14.2.1 20250110 (Red Hat 14.2.1-7)"
		.section	.note.GNU-stack,"",@progbits
	```
	
- [Common Assembler Directives]: 
	
	- [.text]: Tells the assembler to place whatever follows in the text section.
		
	- In GNU/Linux, the object files produced by the assembler are in the Executable and Linking Format (ELF). The ELF standard speciﬁes many types of sections, each specifying the type of information stored in it. We use assembler directives to tell the assembler in which section to place the code.
		
	- The GNU/Linux operating system also divides memory into segments for speciﬁc purposes when a program is loaded from the disk. The linker gathers all the sections that belong in each segment together and outputs an executable ELF file that’s organized by segment to make it easier for the operating system to load the program into memory. The four general types of segments are as follows:
		
		- [Text]: The text segment is where program instructions and constant data are stored. The operating systems prevents a program from changing anything stored in the text segment, making it read-only.
			
		- [Data]: Global variables and static local variables are stored in the data segment. Global variables can be accessed by any of the functions in a program. A static local variable can be accessed only by the function it's defined in, but its value remains the same between calls to its function. Programs can both read form and write to variables in the data segment. These variables remain in place for the duration of the program.
			
		- [Stack]: Automatic local variables and the information that links functions are stored on the call stack. Automatic local variables are created when a function is called, and deleted when the function returns to its calling function. Memory on the stack can be both read from and write to by the program. It's allocated and deallocated dynamically as the program executes.
			
		- [Heap]: The heap is a pool of memory that's available for a program to use when running. A C program calls the `malloc` function to get a chunk of memory from the heap. It can be both read from and written to by the program. It's used to store data and is explicitly deallocated by calling `free` in the program.
		
	- [.globl]: Makes the name globally known so functions that are defined in other files can refer to this name. The code that sets up the C runtime environment was written to call the function named main, so the name must be global in scope.
		
	- [.type]: Has two arguments, `main` and `@function`. This causes the identifier `main` to be recorded in the object file as the name of a function.
		
	- [.intel_syntax noprefix]: Specifies the syntax of the assembly language.
		
	- None of these three directives gets translated into actual machine instructions, and none of them occupies any memory in the ﬁnished program. Rather, they’re used to describe the characteristics of the statements that follow.
	
- [Creating a Program in Assembly Language]: 
	```
	# doNothingProg.s
	# Minimum components of a C program, in assembly language.
		.intel_syntax noprefix
		.text
		.globl   main
		.type    main, @function
	main:
		push     rbp              # save caller's frame pointer
		mov      rbp, rsp         # establish our frame pointer
		
		mov      eax, 0           # return 0 to caller
		
		mov      rsp, rbp         # restore stack pointer
		pop      rbp              # restore caller's frame pointer
		ret                       # back to caller
	```
	
	- [Assembly In General]: It is organized by lines. Only one assembly language statement is on each line, and none of the statements spans more than one line. It is advisable to write statements across multiple lines and indentation to emphasize the structure of the code. In assembly, blank lines are used to help separate parts of an algorithm, and comment on almost every line.
		
		- [# Syntax]: Denotes a comment.
			
		- [Blank Line]: Used for readability
			
		- Assembly language lines has 4 common fields but not all the lines will have entries in all the fields. The assembler requires at least one space or tab character to separate the ﬁelds. When writing assembly language, your program will be much easier to read if you use the Tab key to move from one ﬁeld to the next so that the columns line up.
			`label:    operation    operand(s)    #comment`
			
			- [Label]: Allow us to give a symbolic name to any line in the program. Each line correspond to a memory location in the program, so other parts of the program can then refer to the memory location by name. A label consists of an identifier immediately followed by the `:` character. Identifiers are often made with a set of rules.
				
			- [Operation]: Contains either an *instruction operation code (opcode)* or *assembler directive (pseudo op)*. The assembler translates the opcode, along with its operands, into machine instructions, which are copied into memory when the program is to be executed.
				
			- [Operand]: Specifies the arguments to be used in the operation. The arguments can be explicit values, names of registers, or programmer created identifiers. The number of operands can be zero, one, two, or three, depending on the operation.
				
			- [Comment]: Everything on a line following with a `#` character is ignored by the assembler, thus providing a way for the programmer to provide human-readable comments. Since assembly language is not as easy to read as higher-level languages, good programmers will place a comment on almost every line.
				
			- Make sure comments state the purpose relative to solving the problem, not what it does.
			
		- The rules for creating an identiﬁer are similar to those for C/C++. Each identiﬁer consists of a sequence of alphanumeric characters and may include other printable characters such as `.`, `_`, and `$`. The ﬁrst character must not be a numeral. An identiﬁer may be any length, and all characters are signiﬁcant. Although the letter case of keyword identifiers (operators, operands, directives) is not signiﬁcant, it is significant for labels.
			
		- It’s a good idea to avoid beginning your own labels with the `.` or the `_` character so that you don’t inadvertently create one that’s already being used by the system.
			
		- It’s common to place a label on its own line, in which case it applies to the address of the next assembly language statement that takes up memory. This allows you to create longer, more meaningful labels while maintaining the column organization of your code.
		
	- [First Assembly Instructions]: Assembly language provides a set of mnemonics that correspond directly to the machine language instructions. A mnemonic is a short, English-like group of characters that suggests the action of the instruction.
		
		- The general format of an assembly language instruction in the assembler (Intel Syntax): 
			`operation    destination,    source1,    source2`
			
		- Where *destination* is the location where the result of the *operation* will be store, and *source1* and *source2* are the locations where the input(s) to the *operation* are located. There can be from zero to two sources, and some instructions don't require that you specify a destination. The destination can be register or memory. A source value can be in a register, in memory, or *immediate data*. *Immediate data* is stored as part of the machine code implementation of the instruction and is hence a constant value in the program. 
			
		- The values specified by the operands must be the same. There are instructions for explicitly converting from one size to another.
			
		- The size (number of bits) of the value moved must be the same for the source and the destination. When the assembler program translates the assembly language instruction to machine code, it can figure out the size from the register name.
			
		- The variant that moves an immediate value to memory, `mov mem`, `imm`, doesn’t use a register. In this case, you have to tell the assembler the data size with a size directive placed before the `mem` operand.
			![[Pasted image 20250323192032.png]]
		- The size directive includes `ptr` because it specifies how many bytes the memory address points to. For immediate data, this address is in the `rip` register.
			`mov    byte ptr x[ebp], 123`
			`mov    qword ptr y[ebp], 123`
			would store 123 in the one-byte variable, x, and 123 in the four-byte variable, y.
			
		- Notice that you can’t move data from one memory location directly to another memory location. You have to first move the data into a register from memory and then move it from that register to the other memory location.
			
		- The other three instructions are `push`, `pop`, and `ret`. These three instructions use the call stack. The `rsp` register always contains the address of the item on top of the call stack; hence it's called the *stack pointer*.
			
			- [push-Push onto Stack]: Moves a 64-bit source value to the top of the call stack. `push reg` places the 64-bit value in a `reg` on the call stack, changing the `rsp` register such that it has the memory address of this new item on the stack. `push mem` places the 64-bit value in `mem` on the call stack, changing the `rsp` register such that it has the memory address of this new item on the stack. The `push` instruction does not affect the status flags in the `rflags`.
				
			- [pop-Pop from Stack]: Moves a 64-bit value from the top of the call stack to a destination. `pop reg` copies the 64-bit value at the top of the stack to reg, changing the `rsp` register such that it has the memory address of the next item on the stack. `pop` `mem` copies the 64-bit value at the top of the stack to `mem`, changing the `rsp` register such that it has the memory address of the next item on the stack. The pop instruction does not affect the status flags in the `rflags` register.
				
			- [ret-Return from Function]: Returns from a function call. `ret` has no operands. It pops the 64-bit value at the top of the stack into the instruction pointer, `rip`, thus transferring program control to that memory address. The `ret` instruction does not affect the status flags in the `rflags` register.
		
	- [Minimal Processing in a Function]: Aside from the data processing that a function does, it needs to perform some processing just so it can be called and return to the calling function. The call stack is a great place for functions to temporarily store information. Each function uses a portion of the call stack for storage, which is called a `stack frame`. The function needs a reference to its stack frame, and this address is stored in the `rbp` register, usually called the `frame pointer`.
		```
		# doNothingProg.s
		# Minimum components of a C program, in assembly language.
			.intel_syntax noprefix
			.text
			.globl   main
			.type    main, @function
		main:
			push     rbp              # save caller's frame pointer
			mov      rbp, rsp         # establish our frame pointer
					
			mov      eax, 0           # return 0 to caller
					
			mov      rsp, rbp         # restore stack pointer
			pop      rbp              # restore caller's frame pointer
			ret                       # back to caller
		```
			
		- The first thing a function must do is to save the calling function’s frame pointer so the calling function can use `rbp` for its own frame pointer and then restore the calling function’s frame pointer before returning. It does this by pushing the value onto the call stack. Now that we’ve saved the calling function’s frame pointer, we can use the `rbp` register as the frame pointer for the current function. The frame pointer is set to the current location of the stack pointer.
			
		- Make sure that every function you write in assembly language begins with these two instructions, in this order. Together, they make up the beginning of the **function prologue** that prepares the call stack and the registers for the actual computational work that will be done by the function. And we need to follow a strict protocol for preparing the call stack and registers for return to the calling function. This is accomplished with the **function epilogue**. The function epilogue is essentially the mirror image of the function prologue. The first thing to do is to make sure the stack pointer is restored to where it was at the beginning of the prologue. Make sure to restoring the stack pointers since in most functions it will be changed. Now that we’ve restored the stack pointer from the `rbp` register, we need to restore the calling function’s value in the `rbp` register. That value was pushed onto the stack in the prologue, so we’ll pop it off the top of the stack back into the `rbp` register. Finally, we can return to the calling function. Since this is the main function, this will return to the operating system.
		
	- [Using gdb to Learn Assembly Language]:
		`as -–gstabs -o doNothingProg.o doNothingProg.s`
		`gcc -o doNothingProg doNothingProg.o`
		`./doNothingProg`
		
		- The `--gstabs` option (note the two dashes here) tells the assembler to include debugging information with the object file. The gcc program recognizes that the only input file is already an object file, so it goes directly to the linking stage. There is no need to tell gcc to include the debugging information because it was already included in the object file by the assembler.
			
		- The `gdb` debugger has a mode that’s useful for seeing the effects of each assembly language instruction as it’s executed one step at a time. The *text user interface* (TUI) mode splits the terminal window into a display area at the top and the usual command area at the bottom. The display area can be further split into two display areas.
			
		- Each display area can show either the source code (src), the registers (regs), or the *disassembled machine code* (asm). Disassembly is the process of translating the machine code (1s and 0s) into the corresponding assembly language. The disassembly process does not know the programmer-defined names, so you will see only the numerical values that were generated by the assembly and linking processes.
			```
			$ gdb ./doNothingProg
			--snip--
			Reading symbols from ./doNothingProg...
			(gdb) set disassembly-flavor intel
			(gdb) b main
			Breakpoint 1 at 0x1129: file doNothingProg.s, line 8.
			(gdb) r
			Starting program: /home/bob/progs/chap11/doNothingProg_asm/doNothingProg
			
			Breakpoint 1, main () at doNothingProg.s:8
			8    push    rbp    # save caller's frame pointer
			(gdb) tui enable
			```
## AT&T Syntax

```
	# doNothingProg_att.s
	# Minimum components of a C program, in assembly language.
		.text
		.globl   main
		.type    main, @function
	main:
		pushq     %rbp              # save caller's frame pointer
		mov       %rbp, %rsp        # establish our frame pointer
		
		mov       %0, %rax          # return 0 to caller
		
		mov       %rsp, %rbp        # restore stack pointer
		pop       %rbp              # restore caller's frame pointer
		ret                         # back to caller
```
	
- The first difference that you probably notice is that a character specifying the size of the operand is added as a suffix to most instruction mnemonics. The next difference you probably see is that each register is prefixed with the % character. The most significant difference is that the order of the operands is reversed Instead of placing the destination first, it’s last. If you move between the two syntaxes, Intel and AT&T, it’s easy to get the operands in the wrong order, especially with instructions that use two registers. You also need to prefix an immediate data value with the $ character
	![[Pasted image 20250323195732.png]]
 