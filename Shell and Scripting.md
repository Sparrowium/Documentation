<center><h2> Terminal </h2></center>
- A program that provides a textual user interface.
	
- A terminal supports reading characters from the keyboard and displaying them on the screen.
	
- Terminal also support so-called escape sequences, or escapes codes, for cursor and screen handling and potentially support for colors.
	
- Can be referred as terminal emulator or soft terminal.

<center><h2> Shell </h2></center>
- A program that runs inside the terminal and acts as a command interpreter.
	
- It offers input and output handling via streams, supports variables, has some built-in commands, deals with command execution and status, and usually supports both interactive usage as well as scripted usage.
	
- Shell often formally defined in `sh`, and often the term `POSIX Shell`. 
### Streams

### Variables

- To store and change a value.
	Use case:
	- When you want to handle a configuration items that Linux exposes.
		
	- When you want to interactively query the user for a value, say, in the context of a script.
		
	- When you want to shorten input by defining a long value once.
	
- Two kinds of variables: 
	- Environment Variables: Shell-wide settings; list them with env.
		
	- Shell variables: Valid in the context of the current executions; list with set in bash. Shell variables are nor inherited by subprocesses.

### Exit Status

- Shell communication the completion of a command execution to the caller. 
	
- 2 types of termination:
	- Normal termination (happy path): Yield a 0 exit status means that the command was successfully run, no errors.
		
	- Abnormal termination (something went wrong): Yield a value between 1-255 signals a failure.

### Built-in commands

- Command that comes preinstalled with the Linux Distro. Can be found in `/usr/bin` (for user commands) or `/usr/sbin`(for administrative commands).

### Job control

- Job Control and Background Jobs: to launch a process in the background, put an & at the end, or to send a foreground process to the background, press CTRL + Z.

### Terminal Multiplexer

- 
	
- Sessions: a logical unit that you can think of as a working environment dedicated to a specific task such as "working on project X" or "writing blog post Y". It's the container for all other units.
- Windows: tabs in a browser/terminal.
	
- Panes: a single shell instance running. A part of a window that you can easily split it horizontally or vertically, as well as expand/collapse it and close panes as you need them.

<center><h2> Scripting </h2></center>
