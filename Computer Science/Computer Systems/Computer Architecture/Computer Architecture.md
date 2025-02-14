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