A system of notation for writing Computer Programs

<h2 style="color:#6290C3"><center> Introduction </center></h2>
## What is a Programming Language?

- A programming language is a set of instruction that enables humans to communicate with computers-using a series of symbols that serve as a bridge that allows humans to turn ideas into instructions computers can understand.

## How are they described?

- Programming Languages are described in terms of their [[#syntax]] (form) and [[#semantics]] (meaning), usually defined by a formal language.
	
- Languages are also describe by their feature such as a [[#type system]], [[#variables]], and mechanisms for [[#error handling]].

## Why is it important?

- An implementation of a programming language is required in order to execute programs, namely an interpreter or a compiler.

## Programming Languages Elements

### Syntax

- The syntax of a programming/computer language is the rules that define the combinations of symbols that are considered to be correctly structured statements or expressions in that language.
	
- The syntax of language defines its surface form. *Text-based* computer languages are based on sequences of characters, while *Visual* programming languages are based on the spatial layout and connections between symbols.
	
- [Levels of Syntax]:
	
	- Words: The lexical level, determining how characters form tokens.
		
	- Phrases: The grammar level, narrowly speaking, determining how tokens form phrases.
		
	- Context: Determining what objects or variables names refer to, if types are valid.
	
- [Syntax Error]: An error in the *syntax* of a sequence of characters that is intended to be written in a particular *programming language*.
	
	- For compiled languages, syntax errors are detected at compile-time.
		
	- For interpreted languages, syntax error are detect during program execution.

### Semantics

- The meaning and behavior of the languages
	
	- [Static Semantics]: Refers to the rules and constraints that are checked at **compile time**, before the program is executed. 
		
	- [Dynamic Semantics]: Describes the meaning of a program during its execution. It defines the behavior of constructs at **runtime**, specifying how the program operates step by step when executed.
		
	- [Denotational Semantics]: Describes the meaning of a program as a mathematical object, often using functions and mappings.
		
	- [Operational Semantics]: Describes the meaning of a program in terms of the steps or operations performs during its execution on an abstract machine.
		
	- [Axiomatic Semantics]: Use formal logical statements to specify the properties and behavior of programs.
	
- Provides a way to describe, analyze, and reason about programs.

### Type Systems

- A [Type System] is a logical system comprising a set of rules that assigns a property called a type (e.g., integer, string, boolean,...) to every single term.
	
- By associating a type, it defines a meaning to the programmable hardware to form a symbolic system composed of that hardware and that some program., which ensure **Type Safety**.
	
- [Type Error]: Occurs when an operations receives a different type of data than it expected.
	
	- [Static/Dynamic Typing]: Static typing are types that are checked at **compile time**. Dynamic Typing are times that are checked at **runtime**.
		
	- [Strong/Weak Typing]: Strong typing strictly enforce types rules, implicit type conversion (coercion) are restricted or require explicit casting. Weakly typing allows implicit conversions between types, which can lead to explicit behavior (typical JavaScript).
		
	- [Nominal/Structural Typing]: Nominal typing means that a term compatibility is determined by the name of the type. Structural typing means that a term compatibility is determined by the structure of the type, not its name.
		
	- [Subtyping and Polymorphism]: Subtyping defines a sub-type that is a specialized version of a more general type (usually in OOP). Polymorphism is the ability of a type to be used as if it were another type.
		
	- [Dependent Type]: Types that depends on values.
		
	- [Gradual Typing]: combination of both static and dynamic typing.

### Concurrency

- The ability of a program to execute multiple task, operations, or computation at the same time. Mostly through managing data shared between different threads by controlling the order of execution of key instruction, controlling access to shared data, enabling massage passing between threads.

### Exception Handling

- Refers to the mechanism provided by programming languages to handle runtime errors or exceptional conditions that occur during the execution of a program. 
	
- Common exception handling:
	
	- [Termination]: Shutting down and handling over control to the operating system.
		
	- [Resumption]: Resuming the program near where the exception is occurred.

### Programming Language Levels

- High-Level Languages: Are highly abstracted from the hardware. They are designed to be readable and easy for human to use, with syntax resembling natural language or mathematical notation.
	[[Python]]
	
- Mid-High-Level Languages: Strike a balance between abstraction and control. They allow developers to write relatively readable code while providing limited access to hardware for optimization.
	[[Go]]
	
- Mid-Level Languages: Are closer to hardware than high-level languages but provide abstraction to make programming easier than directly using machine code. Offer a mix of high-level functionality and low-level control
	[[C++]]
	
- Low-Level Languages: Are very close to machine code. They provide no abstraction and require the programmer to manage the hardware directly.
	[[Zig]], [[C]]
	

### Other Languages

- [[HTML]]: HyperText Markup Language
	
- [[CSS]]: Cascading Style Sheet
	
- [[SQL]]: Structured Query Language
	
- [[Bash]]: Shell Scripting Language

