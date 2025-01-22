
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

