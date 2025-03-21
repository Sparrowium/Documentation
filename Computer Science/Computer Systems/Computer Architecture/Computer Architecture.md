<h2 style="color:#6290C3"><center> Introduction </center></h2>
## Inside Common Devices

- [Desktop PC]: 
	
	
	- Contains the mainboard/motherboard, which contains the essential parts of the computer including the Processor and main Memory. 
		
	- The mainboard aka **Printed Circuit Board** started off with an acid-proof fiberglass insulator board, completely covered with a layer of copper, then design the board in a CAD program, print it onto transparency, and shine light through transparency to selectively mask a light sensitive chemical on the board. After that, dip it into acid to remove the unmasked copper and the rest of the copper will become the wiring. You then solder the electronic components onto the appropriate location on the board. 
		
	- Beyond that, the rest of the Desktop components are power transformers (PSU), Cooler, and Storage devices.
	
- [Laptop]:
	
	- Same as the PCs, but they use smaller, less power consuming components with less computing power and higher manufacturing cost.
		
	- The motherboard is shaped to fit the available space with many components soldered directly together to fit under the keyboard.
		
	- Some laptop have secure boot which prevent customization regarding to the Operating System.
	
- [Smartphone]:  
	
	- The word "smart" mean *is a computer*. The smartphone motherboard design is based around the CPU, including with other chips that are specialized for phone-specific roles. Th
		
	- The memory is different from laptop since it uses LPDDR (Low Power Ram). This reduces battery usages by clearing and turning off unused parts.
		
	- Most connectors are limited due to the phone size.
	
- [Washing Machine]: 
	
	- Contains proprietary circuit boards that are design to run arbitrary programs. These circuit boards contains *firmware*, a single program "burned" into the chip that performs only one task.

<h2 style="color:#6290C3"><center> Fundamental Concepts </center></h2>
## Historical Architectures

### What is a Computer?

- A computer is a machine that can simulate any other machine, given as mush memory it asks for.
	`Read, Write, and Process Data`
	`Read, Write, and Execute Program
	`Add (And do other arithmetic)`
	`Jump (goto statements`
	`Branch (if statements`

### Before the Industrial Revolution

- [The Stone Age]:
	
	- [Lebombo Bone]: A bone with carved notches that may have been used as a tally stick around 40000 BCE, in a tally, one marks represents one physical thing. An example of Data Representation.
		
	- [Ishango Bone]: A bone containing marks that appeared to be grouped into tally-like clusters of mostly prime number betweens 3-19, and these clusters are grouped into three lines that sum to 60 or 48. AN example of Advanced Calculation.
	
- [The Bronze Age]:
	
	- [Abacus]: A "sandbox" which implement the accumulator architecture, where the first number is loaded onto the device and the second is added to it, leaving only the final result as the state of the system.
	
- [The Iron Age]: 
	
	- [Antikythera Mechanism]: A odometers devices that were used to survey the maps.
	
- [The Islamic Golden Age]:
	
	- [The automatic flute player of Baghadad]: Uses rotating barrels with movable pins around its edge to indicate the positions of musical notes. The movable nature of pins allows different compositions to be programmed into the device, making it the first known *programmable* automatic machine.
	
- [The Renaissance and Enlightment]:
	
	- [Codex Madrid]: Contains an unbuilt design for a mechanical analog calculator based on Antikythera-like principle.
		
	- [Pascal Calculator]: Includes a digital mechanism similar to the odometer to implementing carry mechanism in mathematics.
	
- [The Steam Age]: 
	
	- [The Jacquard Loom]
		
	- [Victorian Barrel Organs with Music Boxes]
		
	- [Babbage's Difference Machine]
		
	- [Babbage's Analytics Machine]
	
- [The Diesel Age]: 
	
	- [IBM Hollerith Tabulating Machine]: A machine to automate data processing and big data analytics on information.
		
	- [Electromechanical Differential Analyzers]: Used to solve differential equations.
		
	- [Electromechanical Machines of WW2]: Mostly for crytography.
		
	- [The Zuse Z3]: The Z3 was an electromechanical machine using 2,000 electromechanical relay switches and a mechanical binary memory with 64 addresses of 22 bits. It could run up to 10 instructions per second
	
- [The Electrical Age]: 
	
	- [Vacuum Tubes]: An efficient replacement for relays.
		
	- [Eniac]: Electronic Numerical Integrator and Computer.
		
	- [The Manchester Baby]: Electronic Stored-Program Computer.
	
- [The Transistor Age]:
	
	- [Transistor]: Performs the same function as a vacuum tube, but it's smaller, faster, and cheaper, and consume less power and more reliable.
		
	- [Integrated Circuit]
	
- [The Golden Age]: The age of computer architecture.
	
- [The 2000s and Reconnecting the Community]: Linux becomes popular and becoming the open platform for various engineers to develop on.
	
- [The 2010s and the End of Moore's Law]: Clock speed maxed out due to power consumption which leads to overheating, but new innovation burst and become a hit.
	
	- [Multicore Processor]
		
	- [Cluster Computing]
		
	- [The Evolution of Graphics Cards]
	
- [The 2020s, the Cloud, and the Internet of Things]: Where everything becomes data centered

## Data Representation

### A Brief History of Data Representations

- [Tally Sticks and Trading Tokens]: The oldest-known data representations. 
	
- [Roman Numerals]: A closer representation to the human perception of numbers based on the notation of grouped tallies. Larger numbers are usually an approximation or *numerosity*.
	
- [Split Tallies]: Was a variation of tally stick, in which the stick was marked up, then split into two pieces down its length. They were used to record loans, with the long and short halves (the stock and foil) given to the lender and the borrower, the origin of our modern financial *long* and *short* positions in stocks.
	
- [Arabic and Other Numerals]: Arabic system introduced the base-exponent method with fixed columns containing symbols for numbers of 10, 100, 1000, and so on. It also introduced the concept of zero filling in columns that have no count.

### Modern Number Systems

- [Base and Exponents]: Exponentiation is the repeated multiplication of a base.
	
- [Base 10: Decimal]: For base 10 we have an alphabet of 10 symbols: 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9. Strings of n symbols from this alphabet can specify one of 10^n numbers.
	`123 = 1 x 10^2 + 2 x 10^1 + 3 x 10^1`
	
- [Base 2: Binary]: Known as *binary* ad is used in almost modern computers. It has an alphabet of two symbols, usually written as 0 and 1, but sometimes as T and F for *true* and *false*. In electronic computers, the symbols are represented using high and low voltages. *High* is usually system's positive voltage (ex: 5V), *Low* is usually ground or 0V.
	`1001 = 1 x 2^3 + 0 x 2^2 + 0 2^1 + 1 x 2^0`
	
- [Base 1000]: A type of compound notation.
	`123,456 = 123 x 1000^1 + 456 x 1000^0`
	
- [Base 60: Sexagesimal]: A hybrid notation of base 10 and base 12. Used to represent time.
	`11 x 60^2 + 23 x 60^1 + 13 x 60^0 = 39,889 base 10 = 39889 seconds`
	
- [Base 16: Hexadecimal]: Often called *hex code*. Its symbol are a mix of the digits from 0-10 and letters from a-f, often prefixed by 0x to indicate they are hex. Grouped binary.
	`0010 × 2^12 + 1111 × 2^8 + 0100 × 2^4 + 11012 × 2^0`
	`2 × 16^3 + 15 × 16^2 + 4 × 16^1 + 13 × 16^0`
	
- [Base 256: Bytes]: Hex code but grouped into pairs of hex digits. 

### Representing Data

- [Natural Numbers]: Traditionally denoted by the set symbol N, are the numbers 1,2,3,4, and so on. They are often used to represent numbers of physical things in the world.
	
- [Integers]: Set symbol Z, are whole numbers from negative inf to positive inf. They can be defined as pairing natural numbers with positive or negative signs.
	
- [Rationals]: Set symbol Q, are define as, and may be represented by, pairs or integer a/b with b not 0.
	
- [Fixed Point]: Are numbers with a limited number of digits before and after the point.
	
- [Floating Point]: Are composed of a fixed point mantissa and an integer exponent.
	
- [Arrays]: 
	
	- [One-Dimensional Array]: Is a sequence of R values.
		`{a of r} with r = 0: R-1`
		
	- [Two-Dimensional Array]: Is a collection of R x C (standing for numbers of rows and columns).
		`{a of r and c}r=0:R-1, c=0:C-1`
		
	- [D-Dimensional Array]: Is a collection of values with D indices, such as the 3D R x C x D array. 
		`{t of r,c,d }r=0∶R–1,c=0∶C–1,d=0∶D–1`
		
	- The values in Array maybe numbers or other types of data. Often arrays are used for represent vectors, matrices, and tensors.
	
- [Text]: A bunch or natural numbers in an array are used to represent strings of text. Evolved from ASCII to UNICODE.
	
- [ASCII]: The *American Standard Code for Information Exchange* allows for uppercase and lowercase letters, digits, symbols, and punctuation, as well as historical control such as delete, carriage return, line feed, and ring a bell.
	
- [Unicode]: Refers to three different but related standards defined in 1991: UTF-8, UTF-16, and UTF-32. UTF-8 extends ASCII by making use of the previously unused eighth bit. If it’s a 1, then a second byte follows to enlarge the space of symbols. If the second byte starts with a 1, then a third byte follows as well. If the third byte starts with a 1, then a final, fourth byte is also used. UTF-8 thus allows for more than one million different characters. Its standard doesn’t use all of them, but it includes mappings to symbols needed for all major world languages.
	
- [Multimedia Data Representation]: 
	
	- [Image Data]: Grayscale image can be represented by 2D arrays of numbers, with each element representing a pixel, and its value representing the shade of gray. The type of integer representation within this array affects the quality of the image.
		
	- [Audio Data]: Continuous sound waves can be represented as a series of discrete samples. The samples need to be taken at a rate of double the highest frequency present in the signal. Human hearing ranges from around 20 to 20,000 Hz, so common audio sample rates are around 40,000 Hz. Each sample is a number, and as with color depth, the choice of the number of bits to devote to each sample affects the sound quality.
		
	- [Compression]: Compress the data without changing the human experience of it.
	
- [Data Structure]: Any data structure, such as the structs and objects found in most programming languages, can be represented through serialization, whereby the data is transformed into a series of bits to store in memory. Serialization can be performed hierarchically: if a complex structure is composed of several smaller structures, we serialize it be serializing each of these components, then joining their representations together in a series to make the total representation.

### Measuring Data

- The basic unit of data is **bit (b)**, which can take one of two possible states, usually written as 0 and 1.
	
- [SI]: An international organization of scientists and engineers that sets generally accepted standards for scientific measurement units.

## Basic CPU-Based Architecture

### A Musical Processing Unit

- A machine with a capability of reading and performs musical scores.
	
- [From Music To Calculation]: Implementing player piano-style roll of punch cards to specify sequences of instructions, and a Jacquard loom-style mechanical reader to read them and automatically activate the corresponding simple machines in return.
	
- [From Calculation to Computation]: Implementing instructions similar to the musical processing unit, facilitating repeats, codas, and the like. And Memory are required to store intermediate results.

### Babbage's Central Processing Unit

- [High-Level Architecture]: Contains CPU, RAM, and bus to connect them.
	
- [Programming Interface]: Old school programming interface were programs.
	
	- [Constants]: Specify value that is addressed into an address.
		
	- [Load and Store]: Load data for CPU to execute, Store data for future execution.
		
	- [Arithmetic]: Requires *mode*, tells the engine which of these operations you want to perform.
		
	- [Jumps]: Allows program to repeat.
		
	- [Branches]: A conditional checker which ask for whether a condition holds and jumps only if it does.
	
- [Internal Subcomponents]: 
	
	- [Registers]: Are small unit of memory location inside the CPU itself, rather than in the main RAM.
		
	- [Arithmetic Logic Unit]: A collection of independent simple machines that each perform a single arithmetic operation.
		
	- [Control Unit]: Reads instruction form the program in memory, decodes them, and passes control to the ALU or elsewhere to carry the instructions out. Then updates the position in the program according to either normal sequential execution or a jump.
	
- [Internal Operation]: 
	
	- [Fetch]: Reading the machines code for the next instruction into the CPU
		
	- [Decode]: Figuring out what this code means depending on the combinations. 
		
	- [Execute : Load and Store]: Carrying out the decoded instruction.
		
	- [Execute: Arithmetic Instructions]
		
	- [Execute: Program Flow]: Depends on jumps and branches.

<h2 style="color:#6290C3"><center> The Electronic Hierarchy </center></h2>
## Switches

### Directional Systems

- [Switch]: A directional system, takes an input and does something, causing an output.
	
- [Water Valve]: An example of a directional system.
	
	- *reverse-bias*: When pressure is applied in the opposite direction which result in the gate closes.
		
	- *forward-bias*: When pressure is applied in a direction which causes the gate to be opened.
	
- [Heat Diode]: 
	
	- [Diode]: A diode is any electrical system that enables current to flow in one, forward-bias direction and not in the other, reverse-bias direction.
	
- [p-n Junction Diode]: 
	
	- Semiconductor Crash Course: Materials that in their normal states are insulators, but can be coaxed into becoming conductor through a very small change. *Silicon (Si)*, element 1 of the period table is a semiconductor.
		
	- Quantum mechanics shows that atoms are in a low-energy state when their outmost shell is full. Informally low-energy states are called happy and high-energy states are called unhappy. Happy states are highly probable because moving into them is a directional system.
		
	- [doping]: A process of making a silicon crystal conduct by injecting/adding atoms. *p-doping* causes electron shortage (make it positive charge). *n-doping* causes surplus of electrons (making it negative). n-doping allows the material (silicon) to be conductive since the structure is loose.
		
	- [How p-n Junction Works]: A p-n junction consists of p-doped and n-doped region next to one another.
		![[Pasted image 20250130151433.png]]
	- When the junction is created, there’s no effect on the parts of the crystals that are far from the boundary where they touch. But in the region close to the boundary—called the depletion zone—something interesting happens almost instantly.In this zone, the excess electrons on the n-doped side experience a chemical force that attracts them across the boundary to complete the outer shells on the p-doped side. 
		![[Pasted image 20250130151557.png]]
	- The p-n junction functions like the water valve: in its high-energy state it’s like an open valve, enabling current to flow; in its low-energy state it’s like a closed valve, preventing current from flowing.

### Switching

- A switch turn a flow on and off automatically using another flow.
	
- [Water Current Switch]: A system consist of two water valves placed in sequence, with both of their blocks replaced by a spring-loaded moving platform.
	![[Pasted image 20250130152718.png]]
	
- [Electrical Tube Switch]: electrical tube switches extend electrical heat diodes by using one electrical current to control the flow of another electrical current. This works by inserting a metal grid in the middle of the vacuum between the cathode and anode in the heat diode.
	![[Pasted image 20250130153835.png]]
	
- [p-n-p Transistor]: two mirror-image p-n diodes stuck together to form a p-n-p sequence, with a base wire attached to the central n region.
	![[Pasted image 20250130154154.png]]
	
- [Water Pressure Effect Switch]: A water switch but implements the rubber membrane to open the valve. 
	![[Pasted image 20250130154823.png]]
	
- [Field Effect Transistors]: Field-effect transistors (FETs) are the exact analog of water pressure switches, as p-n-p transistors are to water current switches. The FET improves on the p-n-p transistor by covering the end of the base wire with an electrical insulator (such as silicon oxide, SiO2 ) where it joins the n region. The insulator allows an electrical fields to transmit through it, this means an electron on one side can push away an electron on the other side, without the electron itself crossing over.
	![[Pasted image 20250130155250.png]]
	
- [Clocks]: An automatic switch that signal on and off over a period of time.
	![[Pasted image 20250130155751.png]]

### Fabricating Transistor

- [Fabrication]: The process of creating transistors and wires and connecting them together on wafers. A *wafer* presents a two-dimensional surface on which transistors are laid out. Tiny metal wires are added to connect them together.

### Moore's Law

- Transistors will double per two years. But recently there have been a barrier when the 64bit era hits. As transistors increases, heat increases and power consumption increases.The formula below show the relationship between clock frequency, capacitance, voltage, and power:
	`P = C(V^2)F`

## Digital Logic

### Claude Shannon and Logic Gates

- [Logic Gates]: Devices that take a representation of one or more binary variables as inputs, and produce one or more binary outputs using the same representation.
	
- Simple switches are not logic gates because they lose energy, so the output representation has lower energy and is different from the input.
	 
- Any computation could be performed by combining instances of small sets of standard logic gates, such as AND, OR, and NOT.

### Logic Gates

- [Modern Logic Gates Definition]: A logic gate is any device that has some binary inputs and some binary outputs and doesn't contain any memory, where the inputs and outputs use exactly the same physical representations for two symbols, 0 and 1. A logic gate's function can be completely and deterministically described by a truth table, which lists the resulting outputs for each configuration of the inputs.
	
- [Standard Logic Gate]: AND, OR, NOT, XOR, NOR, NAND.
	![[Pasted image 20250204131018.png]]![[Pasted image 20250204131032.png]]![[Pasted image 20250204131041.png]]![[Pasted image 20250204131056.png]]![[Pasted image 20250204131105.png]]![[Pasted image 20250204131112.png]]
	
- [Identifying Universal Gates]: A group of different types of logic gates that could be reconfigured to build any machine at the hardware level. Universal gates reduces the number of types of physical gates to manufacture down to just one.
	
- [Making Logic Gates from Transistors]: The same concept derived from electrical circuit, which is where a electrons flow from the power source to the ground, then are pumped back from the ground to the power source, creating a closed loop. Creating a logic gates from transistors requires external power source to keep the "data" in the same form.
	
- [Putting Logic Gates on Chips]: To connect the logic gates you attach physical wires to appropriate pins.

### Boolean Logic

- Logic allows us to formalize statements and inferences about truth and false-hood.
	
- [Boolean Logic]: Uses variable names to represent conceptual statements whose values are either true or false.
	
- [Logic As Arithmetic]: 
	
	- [Logic]: An "arts subject" performed using natural language text and by studying rules to analyze arguments.
		
	- [Arithmetic]: "STEM subject" made of numbers and equations.
	![[Pasted image 20250204133312.png]]
	
- [Model Checking vs. Proof]:
	
	- [Model Checking]: Given a potential equality, we simply compute truth tables for both the left side and right side of the potential equation. If the truth tables match completely, then expressions are equal. 
		
	- Model checking make use of the values of the terms. If an equality has been shown by model checking, we say that it has been entailed, and it is true.
		
	- [Proof]: A list of transformations from the first to the second expression, where each transformation is justified by stating which law has been applied. If an equality has been shown by proof, we say it is proved.

### Simplifying Logic Circuits Using Boolean Logic

- Simplification can include reducing both the number of gates and the number of types of gates.
	
- This is done by translating a logic gate network into a Boolean expression, simplifying the expression using the laws of arithmetic, then translating the result back into a smaller logic gate network. 

### Laying Out Digital Logic

- [7400 Chips]: Connect a bunch of 7400 chips
	
- [Photolithogaphy]: Here, masks are prepared containing the transistor layouts needed to form the logic gates. This process gives the smallest, fastest hardware, but it’s economical only at large scales to justify the setup costs.
	
- [Programmable Logic Arrays]: A chip with many inputs and many outputs made with photo-lithography, such that every input and every input negation are connected to a series of AND and OR gates by fuses.
	
- [Field Programmable Gate Arrays]: Similar to PLA, but you can rewrite it whenever you like with the new digital logic rather than only being able to burn it once. FPGAs operates by electronically switching on and off connections between blocks of standard logic.

## Simple Machines

### Combinatorial Logic

- Digital logic networks that can be describes by Boolean Logic, without considering the role of time.
	
- [Bitwise Logical Operations]: 
	
	- [Array Operator]: A simple machine that simultaneously performs the same operations on each bit of an input array to give an output array.
		![[Pasted image 20250211204508.png]]
	
- [Multi-input Logical Operations]: Are versions of logic gates from hierarchies of the gates two-input versions.
	![[Pasted image 20250211204744.png]]
	
- [Shifters]: Performs a shifting of the to either the left or the right based on the base/natural power of a number after arithmetic operation. For base 2 depends on the power, shift according to the power to the left or right.
	![[Pasted image 20250211205102.png]]
	
- [Decoders and Encoders]: 
	
	- [Decoders]: are machines that can convert from binary representation to an alternative 1-of-N representation, which has N = 2M bits, all 0 except for a 1 in the xth bit.
		
	- [Encoders]: performs the inverse operation. 
	![[Pasted image 20250211205415.png]]
	
- [Multiplexers and Demultiplexers]: 
	
	- [Multiplexers]: Enables the ability to select which one of the multiple possible sources a user wish to connect to a single output.
		![[Pasted image 20250211205710.png]]
	- [Demultiplexers]: Performs the opposite function to a multiplexers. It takes a single input wire and a code *n*, and sends a copy of the input signal to the nth of multiple output wires.
		
	- [bus]: A shared wire.
	
- [Adders]: Performing additions.
	
	- [Half Adders]: A machine consist of one XOR and one AND to compute the sums for columns when there's no carry coming in.
		![[Pasted image 20250211210106.png]]
	- [Full Adders]: Two half adders combine with an OR gate.
		![[Pasted image 20250211210203.png]]![[Pasted image 20250211210233.png]]![[Pasted image 20250211210340.png]]
	- [Ripple-Carry Adder]: A full ladder for each column and connect the carry out from each column to the carry in of the next.
		![[Pasted image 20250211210517.png]]
	
- [Negators and Subtractors]: 
	
	- [Negator]: A machine that flip the bits and then adding 1 to the result.
		
	- [Subtractor]: A machine that subtracts one number from another.

### From Combinatorial to Sequential Logic

- A type of logic circuit that depends on both the current input and past sequence of input.
	![[Pasted image 20250211211725.png]]![[Pasted image 20250211211737.png]]

### Clocked Logic

- [Clock Signal]: Abbreviate as clk, that steadily oscillates between 0 and 1.
	
- [Tick]: A status updater.
	
- [Clocked Flip-Flops]:
	
	- [SR Flip-Flop]: A simple clocked flip-flop that implements the usage of S (set) and R (reset) and a simple clock signal to flip it's state.
		![[Pasted image 20250211213206.png]]
	- [D-Type Flip-Flop]: A data flip flop that has only one data input and clock input. It captures the data on the D input at a point of a clock cycle. For the rest it output the value on its output Q.
		![[Pasted image 20250211213639.png]]
	
- [Counters]: A digital logic version of Pascal's Calculator that uses a D-type flip-flop to store the data in each column, and wire its output to both its own data input (to refresh the storage) and also to the clock input of the next column's flip-flop as a carry.
	![[Pasted image 20250211214117.png]]
- [Sequencers]: A device that triggers a bunch of other devices at particular times. Made of counter and decoder.
	![[Pasted image 20250211214247.png]]
- [Random-Access Memory RAM]: Is memory that consist of addresses, each containing a group of bits of data known as a word, and in which any address can be read and written at equal time cost.
	
	- Basic RAM has three groups of wires as its interface:
		
		- N address wires carry a binary natural number representation specifying which of 2^N addresses is of interest.
			 
		- A group of M data wires carry copies of words to or from the specified address of the RAM.
			
		- A single control wire, called write, carries a single bit that controls whether the specified address is to be read or written.
	![[Pasted image 20250211215112.png]]
- [Hardware Description Language]:
	
	- [Mask Files]: Lowest level of chip description, containing the physical locations, sizes, and shapes of components such as transistors and wires.
		
	- [Netlist Files]: Contains descriptions of connectivity between physical components and wires, but as abstract connectivity rather than a physical layout.
		
	- [Verilog and VHDL Files]: Are text-based hardware description languages for designing electronic systems. In their most basic forms, they have a similar function to LogiSim, allowing you to instantiate and connect various electronic components. But instead of using a GUI, they use text files with a syntax similar to software programming languages. Unlike a language like C, however, which is imperative, Verilog and VHDL fundamentally describe static objects and relationships between them. In this sense, their structure is more like XML or a database, containing lists of facts rather than instructions to do things.
		
	- [Chisel]: A high-level hardware language that was developed for general architecture design usage. Chisel describes classes of hardware with object orientation.

## Digital CPU Design

### The Baby's Programmer Interface

- Store their instructions and data in the same RAM space. Each line has a number, and it gets copied to the RAM address of that same number.
	![[Pasted image 20250225125022.png]]
	- [Halting]: Stop the machine. Prevent execution of any further instructions and tell the user to inspect the results by lighting up the bulb.
		`01 : HLT`
		
	- [Constant]: Lines with NUM are considered as *data* at their address when the code is first loaded into RAM.
		`01: NUM 10`
		
	- [Load and Store]: Copy the data from RAM into the CPU, and loads the data from CPU to RAM for storage. 
		```
		01: LDN 20
		02: STO 21
		20: NUM 20
		21: NUM0
		```
	- [Arithmetic]: It only has subtraction.
		```
		01: LDN 20
		02: SUB 21
		03: STO 22
		20: NUM 0
		21: NUM 10
		22: NUM 0
		```
	- [Jumps]: Makes the program execution jump to the line whose address is one plus the number stored at the address given in the instruction. This operation is called an indirect jump, as opposed to a direct jump, which would encode the target address itself as a part of the instruction, instead of, the location of the target in this case.
		```
		01: LDN 21
		02: JMP 23
		21: NUM 10
		23: NUM 0 
		# Cause a loop because after 0 is 1
		```
	- [Branches]: Act as a condition statement, whether the current results is negative, if so, it skip the next instruction, moving to the one after it.
		```
		01: LOAD 20
		02: SKN
		03: SUB 21
		04: STO 22
		20: NUM 0
		21: NUM 20
		22: NUM 0
		# 22 is still 0 because line 03 is skipped 
		```

### Assemblers

- Automate the process of translating human-readable assembly programs into machine code. A file of 0s and 1s correspond to machine code is called an executable, as it can be executed directly by the CPU once copied to RAM.

### The Baby's Internal Structures

- [Registers]: Are fast word-length memory, usually made today as arrays of D-type flip-flops, which live inside the CPU and are readable and writable by the CU and ALU. 
	
	- The size of the registers in a CPU are usually taken to define the CPU's word length; 32-bit uses 32 bit-words that are stored in 32-bit registers. 
		
	- Like the individuals flip flops that compose them, registers must be timed to enable correct synchronization of reads and writes. An update signal can be sent to the clock inputs of all the flip-flops making up the registers. Usu- ally writes to the register are performed on the rising edge of this signal. Each register also continually outputs its latest stored value for reading as a set of parallel wires, regardless of the updates.
		![[Pasted image 20250225133016.png]]![[Pasted image 20250225133037.png]]
	- [User Registers]: Are usually the only registers that are visible to the assembly language programmer, who can give instructions to act on their content. Ex: An *accumulator* is a user register that functions both as an input and to store the results of calculation in the same place, *Accumulator Architectures* are those that have only a single user register that acts as an accumulator.
		
	- [Internal Registers]: Are not modifiable registers that is not accessible to user, exclusively to the hardware it self. It include the *program counter* to to store and keep track of the program state in a registers. In addition, the *instruction registers* store a copy of the current instruction, copied in from its address in memory.
	
- [Arithmetic Logic Unit]: 
	![[Pasted image 20250225195400.png]]
- [Control Unit]: A musical conductor liked machine that trigger all of other CPU components at the right times.
	![[Pasted image 20250225195757.png]]![[Pasted image 20250225195827.png]]
	- Tunnels, which are named point taking the place of wires. 
	![[Pasted image 20250225200150.png]]

### Putting It All Together

- [Fetch]: To bring a copy of the next instruction from RAM into the IR in the CPU. Fetching assumes that the address of the next instruction is already in the program counter. When the CPU is first turned on, the program counter-like all registers- is initialized to 0, but is immediately incremented to 1, so the firs instruction must to stored at address 1 and will be fetched.
	
	- To perform a fetch, the program counter is temporarily connected to the address lines of RAM, on tick 1. The data out lines of RAM can be permanently connected to the IR data in, but the IR takes only a copy of the word from these lines when write-enabled and clocked at tick 2
	![[Pasted image 20250225200733.png]]![[Pasted image 20250225200917.png]]
	- This is also called *register transfer language*
	
- [Decode]: In the Baby, bits 13 to 15 are the opcode, bits 0 to 12 are a single operand for some instructions, and the remaining 16 bits aren’t used. This encoding now needs to be decoded. We need to split up the opcode and operand, then convert the opcode into an activation signal.
	![[Pasted image 20250225201055.png]]
- [Execute]: Depends on what instructions has been fetched and decoded.
	
	- [Load]: The operand connect to the RAM's address input and then temporarily connect to the RAM's data output to the accumulator
		![[Pasted image 20250225202221.png]]
	- [Store]: Opposite to loading. Connecting the STO instruction's operand to the RAM's address lines. The accumulator output can be permanently connected to the RAM data input, but only write-enabled.
		![[Pasted image 20250225202238.png]]
	- [Arithmetic]: The CU makes temporary connections to the ALU's inputs from the CPU registers, and creates and sends an ALU command to the ALU's command inputs. The ALU output is then temporarily connected to a destination register.
		![[Pasted image 20250225202418.png]]
	- [Flow Control]: At the start of each instruction, the Baby moves to the next address (line) of the program. This can be done by incrementing (adding 1 to) the program counter at tick 0. If the current instruction is a flow control instruction—that is, a jump or branch—then its execution step also needs to update the program counter to get it ready for the next instruction.
		
		- The Baby uses an indirect jump instruction, JMP, in which the operand contains the address that in turn contains the actual jump target. To implement this indirect jump we thus first attach the operand to the RAM address lines, then attach the RAM data lines to the program counter.
			
		- The Baby also has a relative jump, JRP, which works similarly to JMP except that the address in the operand contains a number of lines to advance the program counter, rather than an absolute address.
			
		- For the branch instruction, SKN, we check its condition and behave as normal if it’s false, or increment the program counter an extra time if it’s true, to skip over one line of code.
		![[Pasted image 20250225202808.png]]

## Advanced CPU Design

### Number of User Registers

- Makes programming easier, makes programs run faster, in trades for, complexity. 
	
- Some architecture have a set of registers which allow programmers to take advantage of possibly simpler and faster instructions on the accumulator while retaining the flexibility to work with the other registers.

### Number of Instructions

- [Instruction Set Architecture (ISA)]: Defines the interface between what the programmer can see and can use, and what needs to be implemented by the CPU designer. 
	
	- But there's a trade off between the assembly language programmer's life and the digital logic implementer's life.
	
- **CISC** AND **RISC** are the two historically opposing philosophies of architecture. 
	
- [CISC]: Pronounced "sisc", stands for *complex instruction set computing*, which emphasizes the creation of lots of instructions in ISA. These can include adding many variations on basic instructions that each act as a new instructions.
	
- [RISC]: Stands for Reduced instruction set computing, stating that hardware is nasty, expensive to develop, and difficult to debug, so make the processor as lean as possible, then solve all the problems in software, which is less expensive and nicer. Focusing on keeping the instructions set as small as possible, then make it fast as possible.

### Duration of Instructions

- [Open Loop Architecture]: No feedback to the counter about the rest of the CPU state. 
	
- [Closed Loop Architecture]: the timing of triggers isn’t set by a central counter. Instead, each stage of work is responsible for trigger- ing the next stage when it’s ready to do so.
	
- The advantage of the closed-loop approach is that some instructions may be simpler than others, requiring fewer ticks to complete. These can use only the ticks that are necessary, then trigger the next instruction as soon as possible, rather than sitting around doing nothing.
	
- Open-loop style is usually associated with RISC, due to RISC’s emphasis on making all instructions simple and fast. Closed-loop is associated with CISC, as CISC may want to include single instructions that perform a lot of complex work and take many ticks to complete, as well as short, fast ones.

### Different Addressing Modes

- RISC aims to reduce the size of the instruction set by maintaining a clean separation between memory access instructions and arithmetic instructions.
	![[Pasted image 20250304154136.png]]
- CISC, in contrast, aims to provide multiple variations of the ADD instruction to make the programmer’s life easier. In addition to ADD, which adds the contents of two registers, we could create another instruction such as ADDM for “add from memory” that would enable the four-line RISC-style addition program to be written with a single instruction
	![[Pasted image 20250304154147.png]]
- Another common variant is to add instructions that use indirect addressing, meaning the operand of the instruction contains the address of the address to be used.
	![[Pasted image 20250304155051.png]]
- [Offset addressing]: (aka index addressing) modes are another popular ISA inclusion. The idea here is that assembly programmers often need to make repeated use of many variables that they tend to store close together in memory. Their life can be made easier if they can first use a new instruction to specify the address of this general region of variable storage, such as A7B216 , then refer to each individual variable by the difference between its address and this region’s address to pick each of the variables in order.

### Subroutines

- [Subroutine]: A piece of code sitting somewhere in memory that will do something when your main program calls it, and will return to the same line in the main program after it was called.
	
- Other subroutines names: Functions, Procedures, Method.
	
- [Stackless Architectures]: A architecture in which a "routine" cannot executed or call another routine because it would override the return address.
	
- [Stack Architecture]: 
	
	- [Stack]: A simple data structure with two operations, push and pop. Implements LIFO.
		
	- Using a stack, you can create a full trail of addresses to return through in the case of nested subroutines. Each time a subroutine is called, its return address is pushed to the stack. When the subroutine returns, this address is popped off the stack and used to set the program counter.
		
	- A **stack overflow error** is a failure condition where we run out of stack space; if you use a specific chunk of memory to hold your stack, and you run out of space, the program will create a stack overflow error as you try to write outside the stack boundaries. This usually happens because of something that’s gone wrong in an infinite loop of functions calling themselves or each other.
		
	- [stack pointer register]: An internal register that contains a pointer to the top of the stack.

### Floating Point Units

- [Floating-point registers]: Are specialized user registers designed to store floating-point data representations for use in floating-point computations.
	
- [Floating Point Unit (FPU)]: Are complex pieces of digital logic and expensive to design; they also take up lots of silicon and are prone to bugs.

### Pipelining

- A form of instruction-level parallelism.
	
- [Hazards]:
	
	- [Branching Hazards]: Somewhere down the pipeline, an if statement is found and the other, earlier stages were working to complete one outcome of the branch, but you need to go to the other outcome instead. When a conditional branch is reached, you don't know which condition will be followed until the branch gets executed.
		
	- [Data Hazards]: Two of the workers trying to hit on the same memory location-to fetch and output to.
		
		- [Read After Write]: This is where you have two instructions, the first trying to write to memory and the second trying to read from the same address. The logic of the program is supposed to be that the value that gets read should be equal to what has just been written. But when pipelining is in play, it may be possible for the RAM access of the read to occur before RAM has been changed by the write.
			
		- [Write After Read]: This is the other way around: here two instructions are supposed to first read the old RAM value and then update it with a write. But when they are interleaved by pipelining, it may be possible for the part of the write instruction that actually changes the RAM value to occur before the part of the read that accesses it.
			
		- [Write After Write]: This is where two write instructions interfere with one another when trying to write to the same address. The program logic is supposed to be that the first one writes, then the second one, leaving the address containing the second one. But again, pipelining may interleave stages of their executions, in some cases performing the intended first write after the second.
		
	- [Structural Hazards]: Where multiple stages are fighting for resources at the same time.
	
- [Hazard Correction]: 
	
	- [Programming to Avoid Hazards]: Often involves considering groups of neighboring instructions and thinking about how they could affect one another in the pipeline, and changing the order of some instructions to make them further apart and less likely to affect one another.
		
	- [Null Operation (NOP)]: Means do nothing, it still go through the pipeline, taking up time slots, so a human programmer or compiler can insert them between hazard-causing instructions to spread them out and avert the hazard. Involves less intelligence than reordering instructions but trades for execution speeds.
		
	- [Stalling]: Putting he results of the pipeline on hold to allow some stage to complete its work. Affects execution time.
		
	- [Eager Execution]: Executing both possible branches at the same time for a short period, and then killing the one not taken later on, once we figure out which it should be. Affects execution time due to doubling physical logic to perform twice as much computation in parallel during the period of uncertainty.
		
	- [Branch Prediction]: Predicting where a branch will be before execution. 
		
	- [Operand Forwarding]: Directly route the result of an instruction to become an input to a next or nearby instruction.

### Out of Order Execution

- A advanced form of instruction-level parallelism than pipelining. It involves actually swapping around the order of instructions as they come into CPU, so they're executed in a different order than they appear in the program.
	
- They key to OOOE is recognizing that instructions in a serial programs can often be swapped without changing their results.
	
- OOOE is usually performed by digital logic in the CPU, in real time during program execution. Usually only a short window—such as 10 or 20 instructions—around the current instruction in the program is considered for reordering.

### Hyperthreading

- Another way to make use of CPU resources when they would otherwise be sitting idle during the cycle. Rather than work on consecutive instructions from one program, we put them all together to form a second virtual CPU core that operates on a separate set of instructions. Each component of this virtual core runs out of phase with its use in the main CPU core, when it would otherwise be idle. By collecting all the components together, all out of phase, we create a whole extra CPU, keeping all the silicon in constant use at all times.
	
- It effectively doubles the number of apparent cores over the number of physical cores in a device, which is why you often see your computer report having twice the number of cores that were advertised on the hardware you bought.
	
- Hyperthreading has the advantage over pipelining that you no longer have to worry about hazards because the two cores can operate completely independently of one other. On the other hand, it doesn’t increase the speed of any one program. It also requires additional digital logic to read, store, and write the states of the two virtual CPUs at the right times, and duplication of some hardware components, so that one doesn’t affect the other.

## Input/Output

### Basic I/O Concepts

- [I/O Modules]: Are digital electronics that are assigned and connected to addresses in the computer's *address space*, the range of possible addresses that the CPU can access.
	
- [Devices]: Are electronic systems, including digital and analog electronics, that aren't connected directly to the computer's address space but that can communicate with it via the attached I/O modules.
	
- [Peripherals]: Are the most obvious elements of I/O for most computer users: they're physical objects that connect to the computer from outside. They're encased in their own plastic and connect to the computer's box via a wire that the end user can easily plug and unplug.
	![[Pasted image 20250311180607.png]]

### Buses

- [Bus Architecture]: A specific type of network architecture in which every device involved in communication has equal access to a shared wire or set of wires, called bus.
	
- There's no privacy in bus architecture, which may have interesting security implications if untrusted devices are allowed to access it.
	
- A bus is the simplest form of network, lacking the complexity of the internet's access, error handling, and routing.
	
- A bus is composed of several nodes (thing that want to talk to each other) and communication lines (wires) between them. Modern buses usually have many lines in parallel, though there are also buses with only one.
	
- A protocol is needed to ensure that signals don't collide with the signals being sent by other nodes, so for a node to send a message to another it must first announce whom the message is for-the address, on the address lines- and announce what type of message is it-the control, on the control line.
	
- [Bus Lines]: 
	
	- [Address Lines]: These are used to designate the source or destination of data on the data bus. The width of the address bus determines the maximum possible memory capacity.
		
	- [Data Lines]: These provides the path for the actual transfer of data among nodes. A key performance factor is the width of the data bus. A typical data bus consists of 32, 64, 128, or even more separate lines. To send messages that are longer than the data line width, you need to split them up and send them over several cycles.
		
	- [Control Lines]: These are used to control access to and use of the data and address lines.
	
- [The CPU-Bus Interface]: Most CPUs are designed to connect to an external bus, printed onto the mainboard, via pins on the CPU chip connecting to sockets on the mainboard. Where the bus wires physically connect to the CPU, the connection is known as the front side bus (FSB). The vast majority of a CPU’s pins are taken up by the FSB.
	![[Pasted image 20250311185016.png]]
	- The CPU needs to communicate with the bus, but the bus is usually slower than the CPU. Hence, CPU designers prefer to use registers to stage data going in and out of the CPU. The bus is a scarce resource, so we don’t want to use it for any longer than needed; if data is staged, it can be put on and off the bus at whatever time the bus becomes available.
		
	- Typically, these staging mechanisms include a *memory address register (MAR)*, which stores the address from which we want to read or write, and a *memory buffer register (MBR)*, which stores a copy of the data being written to or read from that address.
	![[Pasted image 20250311185319.png]]
	- To execute a load instruction, the operand containing the address to be loaded is temporarily connected from its instruction register (IR) bits to the MAR, creating a copy in the MAR. When this copy is completed, the MAR is temporarily connected to memory as a read request, and the data from memory is temporarily connected to the MBR, which takes a copy of this data. Then the control unit (CU) can temporarily connect the MBR to the accumulator or other user register.

### I/O Modules

- A chip that sits on the bus and at some address, it looks just like RAM to the CPU, but it has wires coming out of the other side that go to the device. The module presents a standardized interface to the CPU, and translates requests from the CPU to specific signals on the wires to the particular device. 
	
- Storing to these addresses might transmit commands to the device. Loading from these addresses might read data from the device.
	
- [Control and Timing]: 
	
	- An I/O module must be able to coordinate the flow of data between the internal resources and external devices. The latter may be slow, so the module manages them independently of the CPU. This allows the CPU to go and do other things while it’s waiting. This is a form of non–CPU level parallelism.
		
	- [Buffering]: Using a dedicated area of memory, called **buffer**, as a staging area. 
		
		- Which enable independent management to transfer data into and out of main memory or CPU. Slow devices can take their time writing to or reading from a buffer, independently of the CPU. The fast CPU can also read or write to the same buffer, independently of the device.
		
	- [Ring Buffers]: Are used in audio and similar real-time signal processing I/Os. Conceptually, a ring buffer is a region of data in which the data items are organized in a circle, each with a previous and next neighbor. 
		![[Pasted image 20250311190724.png]]
		- Two pointers—which can be visualized as clock hands—keep track of the read point and the write point. As new data arrives in real time, it’s written to the write point, which is then incremented to point to the next slot. Eventually the write pointer makes it all the way around the ring, at which point it starts overwriting old data. The user program can request to read the next available items at any time. When this happens, the data at the read pointer is copied out and the read pointer is incremented until the number of items requested is met or the read pointer hits the write pointer, meaning there’s no further new data available.
		
	- [Double Buffers]: Often used for graphics rendering.
		![[Pasted image 20250311190857.png]]
		- At any instant, one buffer stores a completely rendered image and is connected (shown by the thick black outlines in the figure) to the graphics display hardware, which works to physically display it. Meanwhile, the other buffer is used to gradually build up the next image to be displayed. Only when the new buffer is finished is the output line swapped over to connect it to the display; then the original buffer is cleared and used to start drawing the third image in the sequence.
		
	- [Error Detection]: Error is reported to I/O modules, then passed on to the CPU.

### I/O Module Technique

- [Polling]: The CPU requests an action by the I/O module over the bus. The I/O module starts to perform the requested action, setting appropriates bits in an internal I/O modules status registers as it goes. The CPU then periodically checks the status of the I/O module by reading this status register until it finds that the action is complete. 
	
	- Advantages of polling are that it’s simple to implement and the CPU has direct control over I/O operation, requiring very little hardware support. The disadvantage—as in the human boss case—is that the CPU must periodically poll the module to check its status. This ties up the CPU, creating long periods where it does no useful work.
	
- [Interrupts]: In interrupt architecture, the CPU is extended to enables the programmer to tell it the address of a special subroutine called a handler. The CPU is also extended by adding an extra dedicated physical pin called an *interrupt request (IRQ)* input, along with adding digital logic to the CU to make use of the pin. A high voltage on the IRQ tells the CU to alter the program flow by immediately calling the handler subroutine.
	
	- To use an interrupt architecture, the IRQ pin must be connected to a dedicated output from the I/O module. The programmer creates a handler subroutine intended to be executed once the I/O work is done, and tells the CPU its address. The programmer then writes a main program that instructs the I/O module to do actions. When an action command is sent to the I/O module, the CPU forgets all about it and continues executing the main pro- gram. The I/O module makes its device do its thing, which can take some time. When the device is done, the I/O module interrupts the CPU by setting the IRQ line to high. This calls the handler subroutine, which makes use of the new data from the device or tells it what to do next.
		
	- An advantage of interrupts is that they’re fast and efficient, with no need for the CPU to wait or to have to manage polling requests. A disadvantage of interrupts is that they can be tricky to write, especially when multiple I/O modules are in play, all sending interrupt signals at the same time. A *re-entrant architecture* allows interrupt-handling subroutines to be themselves interrupted by higher-priority IRQs, while a *non-re-entrant architecture* might ignore or delay these meta-interrupts.
	
- [Direct Memory Access]: DMA requires a dedicated hardware DMA controller to be placed on the system bus, since bus allow non-CPU nodes to communicate directly with one another, independently of the CPU. Any node can put a message to any other node on the bus, this is done in DMA: the CPU grants authority for the I/O module to communicate directly with RAM over the bus, reading from or writing to memory without any CPU involvement. 
	
	- This frees up the CPU and DMA usually sends an interrupt when a task is complete, so the CPU is involved only at the beginning and the end of the transfer.

### I/O Without Modules

- [CPU I/O Pins]: I/O modules are implemented as *pins* that is connected directly to the CPU. Reduce complexity allows the bus for other activities, comes at a cost of spaces.
	
- [Memory Mapping]: Map address directly onto the RAM, as it can be readable and writable, cost of confusion.
	
- [Bus Hierarchies]: Multiple layers or buses, improves usability.
	![[Pasted image 20250311192949.png]]

## Memory
### The Memory Hierarchy

- The arrangement of memory in a system.
	![[Pasted image 20250320162625.png]]
	- [Registers]: Memory inside the CPU.
		
	- [Cache]: Memory outside but close to the CPU, which contains fast copies of primary memory.
		
	- [Primary Memory]: Memory stored in an address space that is directly accessible by the CPU’s load and store instructions.
		
	- [Secondary Memory]: Memory not directly accessible to the CPU via its registers and address space, but that can be moved into primary memory by I/O to enable such access.
		
	- [Tertiary Memory]: Memory that isn’t directly connected to the address space or to I/O, but that can be mechanically connected to I/O without human intervention.
		
	- [Offline Memory]: Memory that can be connected only to the computer with human intervention.
### Primary Memory

- Known as *system memory*, is memory stored in an address space that's directly accessible by the CPU's load and store instructions. This includes RAM and ROM.
	
- IN primary memory each memory location is given a unique address. Each address stores a fixed-size array of bits called a *word*. Often, but not always, the word length is chosen to be the same as the address length.
	
- [Bytes And Endianess]: 
	
	- [Byte]: Means 8-bit.
		
	- [Byte Addressing]: Addressing memory per byte.
		
	- [Endianess]: The order in which the these bytes should be stored in memory addresses.
		
	- [Big Endians]: The most significant byte of a multi-byte data is stored at the lowest memory address.
		
	- [Little Endians]: The least significant byte of a multi-byte data value is stored at the lowest memory address
	
- [Memory Modules]: A printed circuit board on which memory integrated circuits are mounted via bus. All bus modules—including memory and I/O modules—are usually manufactured to respond to some default address space, such as starting at address 0.
	
	- [Memory Controllers]: A device that listen to the bus for global addresses and route them to the appropriate module, converting to the module's own local address. This is because when they’re mounted onto a bus, these addresses need to be remapped to be unique when compared to the other modules.
		
- [Random-Access Memory (RAM)]: Random access means that any random location in memory can be chosen and accessed quickly, without some regions being faster to access than others. By modern convention, RAM refers to memory that’s not only random access but also both readable and writable, as well as volatile, meaning its data is lost when the machine is powered off.
		
	- [Static RAM]: RAM that are made out of flip-flops, that are fast and expensive. They have stable memory states, meaning they don’t have to be actively refreshed. They’re available for reading almost immediately after being written to. What sets SRAM apart from CPU registers is that SRAM is addressed, and CPU registers aren’t.
			![[Pasted image 20250320174210.png]]
		
	- [Dynamic RAM]: Cheaper and more compact than SRAM, but slower. Instead of being made from flip-flops, it’s made using cheaper and slower capacitors. One bit of DRAM storage is made from just one transistor plus one capacitor. DRAM features the same addressing system as SRAM, and its circuit diagram has the same overall structure as SRAM, based on words stored at addresses. The difference is that the words are implemented with capacitors instead of flip-flops.
			![[Pasted image 20250320174135.png]]![[Pasted image 20250320174221.png]]
		
	- Single in-line memory modules (SIMMs) have a 32-bit bus width, and they were standard in 1990s PCs. Double in-line memory modules (DIMMs) replaced SIMMs in the 2000s. They have a 64-bit bus width, and each stores many gigabytes. Double data rate (DDR) DRAM doubled the speed of DRAM through technology that enables data to transfer on both the rising and falling edges of the clock. This doubles the bandwidth (as bandwidth = bus width × clock speed × data rate).
		
	- [Error Correction Code RAM (ECC-RAM)]: Has extra chip on the DIMM that store extra copies or checksums of the data and use them to automatically correct such flips at the hardware level.
	
- [Read Only Memory (ROM)]: Traditionally refers to memory chips that can only be read from, not written to, and hat are pre-programmed with permanent collections of subroutines by their manufacturer. then mounted at fixed addresses in primary memory.
		
	- ROMs nowadays have evolved to allow increasing ease of rewriting, with programs stored in ROM that are able to be rewritten in some way now known as *firmware*.
			![[Pasted image 20250320174805.png]]
		
	- [Masked ROM (MROM)]: Is ROM whose contents are programmed using photo-lithography by the manufacturer. It remains read-only forever and can't be overwritten.
		
	- [Programmable ROM (PROM)]: Manufactured to include a generic circuit with many fuses. The programmer can then selectively blow the fuses to create different structures. While PLAs enable arbitrary digital logic networks to be burned in this way, PROMs instead contain a fixed structure of addresses and words, and allow only the bits composing the words to be burned, to make a ROM. Usually each bit contains 1 when its fuse is intact and changes to 0 if its fuse is blown. Like PLAs, PROMs can never be erased once they’re programmed.
		
	- [Erasable Programmable ROM (EPROM)]: Like PROM, but the chip’s data can be erased using ultraviolet light. Then new data can be burned on. This cycle can be repeated many times.
		
	- [Electrically Erasable Programmable ROM (EEPROM)]: like EPROM in that you can wipe the entire chip and rewrite it, but here you only need to use electricity to erase and reprogram. This removes the need to physically manipulate the ROM; it can remain inside the computer. EEPROM is used today in ROMs that allow their firmware to be upgraded.
		
	- [Flash Memory]: is EEPROM that can be erased and rewritten block-wise, meaning you can selectively wipe and rewrite just one small part, or block, of the memory at a time. This way you can leave most of the ROM intact, unlike with regular EEPROM, where you have to wipe and rewrite an entire chip of ROM at a time, as in a firmware update.
### Caches

- An extra layer in the memory pyramid between the fast registers of the CPU and the slower RAM. It stores copies of the most heavily used memory contents, making them available for quick retrieval. Without a cache, RAM would connect straight to the CPU, either directly or using a bus with control (C), address (A), and data (D) lines.
	![[Pasted image 20250320180533.png]]
- The problem with this kind of cacheless architecture is that most programs need to access RAM frequently, but the capacitors that implement DRAM are slower than the flip-flops that implement the CPU’s registers. RAM thus becomes a major bottleneck for system speed. Adding an SRAM-based cache made from flip-flops between the CPU and RAM helps avoid these bottlenecks.
	![[Pasted image 20250320182419.png]]
- When the CPU needs to load some data, the cache checks if it has it, and returns it quickly if so. If not, the cache refers to the next memory level down (in Figure 10-8, RAM) and fetches the data from that level. Caching can also occur at all levels of the memory hierarchy, from registers to hard disks and jukeboxes. Initial designs began with a single cache, made from SRAM. More recent machines have made use of Moore’s law for transistor density to fill silicon with larger caches and more levels of cache. It’s common today to have at least three cache levels, called L1, L2, and L3. 
	![[Pasted image 20250320182600.png]]
- [Cache Concepts]: Caches are based on the principle of locality, which states that only a small amount of memory space is being accessed at any given time, and values in that space are being accessed repeatedly. It’s therefore useful to copy recently accessed values and their neighbors from larger, slower memory to smaller, faster memory.
	
	- [Temporal Locality]: Is the property that values tend to be accessed repeatedly at nearby times. 
		
	- [Sequential Locality]: Is the property that some sequences tend to be re-accessed in the same order multiple times.
		
	- [Spatial Locality]: Is the property that values nearby in memory tend to be accessed together. 
		
	- Cache memory is made of many cache lines. Each line contains a block with copies of several contiguous words from memory, as well as a tag, an address or other identifier describing which memory location has been copied into the block. Each line also has a dirty bit that tracks whether the CPU has changed the value in the cache, making it different from the equivalent value in memory.
		![[Pasted image 20250320183404.png]]
	- Each cache line shown in the table has a block of three 8-bit words, a tag consisting of the full address from a 16-bit address space, and a dirty bit. The 1 dirty bit for the first line indicates it’s been updated, while the 0 dirty bit for the second line indicates it hasn’t.
		
	- We don’t cache individual addresses, but rather lines because it’s very cheap to move around larger chunks of memory rather than individual words. By bringing in whole lines around a target word, we exploit spatial locality—data and programs in neighboring locations are likely to be used next. The line prepares for this.
		
	- Some cache systems use “hash functions” to choose a location in the cache for storing a piece of data, usually based on the data’s address in lower-level memory. A **hash function** is a many-to-one function that maps a big input number to a smaller output number, the hash value. It’s not usually possible to recover the original value from the hash value.
		
	- Finding an item in a cache is known as a **hit**. Not finding an item in a cache is known as a **miss**. When a miss occurs, we have to go back to the underlying memory and find the item there instead, usually making a new copy in the cache for future use. The **hit rate** is the ratio of hits to attempts (hits and misses together). This measures the proportion of cache lookups that are successful. The **miss rate** is the ratio of misses to attempts. This measures the proportion of cache lookups that are unsuccessful. The **hit time** is the time required to access requested data if a hit has occurred, and the **miss penalty** is the time required to process a miss.
		
	- A cache has only a limited number of lines, and they quickly fill up as we store cached copies of everything that we access from the underlying memory. Once the cache is full, we’ll continue to request new addresses. These will initially miss, but temporal locality suggests that these new addresses are more likely to be reused than the older ones in the cache. We should therefore choose lines in the cache to overwrite, discarding their previously cached addresses and replacing them with the new ones. The contents of the overwritten lines are called **victims**.
	
- [Cache Read Policies]:
	
	- [Direct Mapped]: Direct mapping is the simplest, easiest, and cheapest cache read policy to implement and understand. In essence, the line where we store or look for a tag is addressed using a fixed hash of the tag. A line with this tag will only ever be stored at a single location. If multiple lines compete for the location, the new one will replace the older one. The drawback is that direct mapping can’t keep multiple in-use addresses in cache if they share the same hash.
		![[Pasted image 20250320184035.png]]
	- [Fully Associative]: Contains a single set with B ways, where B is the number of blocks, including a comparator, multiplexer, and OR arrays. A memory address can map to a block in any of these ways. A fully associative cache is another name for a B-way set associative cache with one set.
		![[Pasted image 20250320184654.png]]
	- [Set Associative]: An attempt to get the best of both of the above methods. Here we partition the N-line cache into several smaller sets of lines. We use hashing on addresses to hash to a set number, rather than a line number. During caching we find the set number from this hash, similar to the direct mapping approach, then choose as the victim the line within this set that has the least usage, similar to the fully associative approach. During lookup we again find the set number from the hash, then we use parallel matching checks on all items in just the one set to quickly find the matching line.
	
- [Cache Write Policies]: Tends to be complex because store changes the state of memory.
	
	- [Write-Back]: The simpler cache writing method: it copies the contents of the cache block back to RAM only when the line is victimized.
		
	- [Write-Through]: a potentially faster alternative to write-back, although it uses more resources. In write-through, we don’t wait until our line is victimized to copy our line’s block back to RAM; rather, we do it multiple times, continually, in the background, using digital logic attached to the cache line and bus.
		
	- [Advanced Cache Architecture]:
		![[Pasted image 20250320185210.png]]
### Secondary and Offline Memory

- [Secondary Memory]: Is memory that can quickly be brought into addressed memory space via I/O. Data items in secondary memory don’t have ad- dresses in the primary memory address space. Rather, they’re accessed via I/O, usually via an I/O module that does sit in the primary address space and relays requests to the secondary storage. Secondary storage is some- times called online storage to emphasize that it’s powered, active, and available whenever the computer is on.
	
- [Offline Memory]: Is that which can’t automatically be loaded into primary memory without manual human interventions. Often this includes secondary memory media that are physically ejectable and replaceable, such as tapes, discs, and USB devices. These media are secondary memory when connected to the computer, and offline memory when disconnected. Off- line memory is typically used for backup and archival purposes, as well as for transportation. The fastest way to move petabytes of data around the world is still to put it on a truck as offline memory and drive it to its destination.
	
- Secondary Memory are measured in bits and SI unit.
	
- [Tapes]: Are one-dimensional data stores that must be scrolled left or right to locate a required datum. Tapes aren’t random access because a reading device has a position at one point in the tape, and it takes longer to move the tape (or the reader) to access a far-away location than a nearby location.
	
- [Punch Cards]: Are the original computational secondary storage, as used in the Jacquard loom and Analytical Engine.
	
- [Punched Tape]: punch cards alternative.
	
- [Magnetic Tape]: Was developed in the 1920s for analog audio recording in studios, commercialized for home use as 8-track systems in the 1960s, then used widely in 4-track compact cassettes during the 1980s. Analog magnetic tape was also widely used in the 1980s for home video recordings, following one of the first modern data standards wars between competing VHS and Betamax formats.
	
- [Disks]: Are storage device for was cylinders, a device that record sound waves through the acoustic horn and are concentrated to vibrate a needle, etching the sound wave into a spiral around a hot wax cylinder as it rotates and is slowly moved left to right. When the wax cylinder is cool it can then be spun past the needle again to make it vibrate in the same ways, and have its motions amplified by the horn, replaying the sound.
	
- [Floppy Disk]: Magnetic disks use the same technology as magnetic tape to represent data, but they arrange the magnetizable material into a 2D disk rather than a 1D tape. The disk is read and written by a magnetic head on an arm, like a gramophone needle. Floppy disks are vulnerable to damage, so they’re usually encased in a plastic sheath.
	
- [Hard Disks]: Are made of nonflexible materials. They can store higher information densities and spin faster than floppies. These devices usually require sealing the head into a package with the disk. Hard drives usually contain multiple hard disks packaged together, each with its own head, with a single address space spanning all of them. This can help reduce access times, because the heads can all read and write together. The disks spin at speeds such as 90 to 250 Hz, which causes a layer of air to lift the head off the surface, so the head doesn’t physically contact the platter. This means there’s no physical wear to the head or the disk.
	
- [Optical Disk]: Optical discs are modern-day version of the Babylonian clay tablets.
	
- [Solid State Drives]: These are manufactured to have the same form factors and I/O interfaces, and similar capacities, as hard drives, but with no moving parts. This makes them faster, more reliable, lower power, quieter, smaller, and less prone to breakage when dropped. As there are no moving parts, they can be truly random access. SSDs are flash memory, as we’ve previously reviewed.
### Tertiary Memory

- A recently proposed level in the memory hierarchy. It lies below secondary memory but above offline memory, and has been created to describe memories that used to be offline—requiring humans to physically load and eject media such as discs and tapes—but is now automated by mechanical processes.
### Data Centers

- Thousands, or tens or hundreds of thousands, of secondary and tertiary memories together in a warehouse-sized building. Built with extreme security and resilience in mind.
 



