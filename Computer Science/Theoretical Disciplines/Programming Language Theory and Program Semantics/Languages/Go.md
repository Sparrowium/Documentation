High level General Purpose Language
<h2><center> Basic </center></h2>
## Setting Up Environment

- Installing [Go Tools](https://go.dev/dl/)
	
- Troubleshooting Your Go Installation:
	
	- Type go --version
		
	- If Go doesn't exist, check whether Go is added to the executable path.
	
- [Go Tooling]: All of the Go development tools are accessed via the go command. In addition to go version, there’s a compiler (go build), code formatter (go fmt), dependency manager (go mod), test runner (go test), a tool that scans for common coding mistakes (go vet), and more.
	
- Making a [Go Module]:
	
	- Create a Go Directory:
		`mkdir Go`
		`cd Go`
		
	- Run `go mod init` to mark the directory as a [Go Module].
		`go init hello_world`
		
	- #Note Go project is called a module. A module is not just source code. It is also an exact specification of the dependencies of the code within the module. Every module has a go.mod file in its root directory.
		 
	- When editing go.mod file, it is recommended to use the `go get` and `go mod tidy` commands in the terminal to manages changes.
	
- Building a [Go Program]:
	
	- Write a simple hello.go program
		``` 
		package main
		
		import fmt
		
		func main() {
			fmt.Println("Hello , World!")
		}
		```
		
	-  The first line is a package declaration. Within a Go module, code is organized into one or more packages. The main package in a Go module contains the code that starts a Go program.
		
	- Next there is an import declaration. The import statement lists the packages referenced in this file. Unlike other languages, Go imports only whole packages. You can’t limit the import to specific types, functions, constants, or variables within a package.
		
	- All Go programs start from the main function in the main package. You declare this function with func main() and a left brace.
		
	- After that type `go build` in terminal to build a go program.
		`go build`
	- And then type `./{folder name}` to run your Go Program.
		
	- If you wish to call it under a different name or store it in another location, use the `-o` flag.
	
- [Go fmt]: Go standard code formatter for indentation and other use cases.
	`go fmt ./...`
	
- [Go vet]: Detect code errors.
	`go vet ./...`
	
- [Makefiles]: A special file used by the make build automation tool to control the build process of a project.

## Predeclared Types and Declarations

- [Predeclared Types]: Types that are built into the language. 
	
- [The Zero Value]: A defaults value that is assigned to any variables that is declared but not assigned a value.
	
- [Literals]: An explicitly specified number,character, or string
	
	- [Integer Literal]: A sequence of number. Base 10 by default. Underscore is used as a separator for long integer literals, these underscores have no effect on the value of the number.
		
	- [Floating-point Literal]: Involves a decimal point to indicate the fractional portion of the value. It can also have an exponent specified with the letter e, hexadecimal with 0x prefix.
		
	- [Rune Literal]: Represents a character and is surrounded by single quote.
		
	- [String Literal]: Are characters that is enclosed in double quotes.
		
	- [Raw String Literal]: These are delimiters with backquote (`` ` ``) and can contain any character except backquote. There are no escape character, therefore all are included as is.
		
	- Literals are considered untyped and most of the time undeclared literal are `default`.
	
- [Booleans]: The `bool` type represent Boolean value.
	
- [Numeric Types]:
	
	- [integer Types]: Go provides both signed and unsigned integers in a variety of size from 1-8 bytes.
		![[Pasted image 20250114212242.png]]
	- [The Special Integer Types]: A byte is an alias for `uint8`. `int` is a 32-bit signed integer like `int32`. `uint` is just unsigned.
		
	- Choose integer that fits the use case.
		
	- [Integer Operators]: +, -, \*, /, %, +=, -=, \*=, /=, %=, \==, !=, >, >=, <, <=
		
	- [Floating-point Types]: float32 and float64. Used to declare floating-point number, recommended not to use.
		
	- [Complex Types]: Declaring imaginary number.
	
- [Rune Types]: int32.
	
- [Explicit Type Conversion]: 
	
	- [Automatic Type Promotion]: Automatically convert from one to another when needed, but Go does not allow that.
		
	- You must type conversion manually when the variable types does not match, even the sizes must be converted to the compatible type.
		
	- Go does not allow default boolean value for nonzero value and empty string. To convert to boolean, comparison operators must be used.
	
- [Literals are Untyped]: This means they can be used with any variable whose type is compatible with the literal. However, you can’t assign a literal string to a variable with a numeric type or a literal number to a string variable, nor can you assign a float literal to an int.
	
- [var Versus :=]: var has a larger scope, := is limited to functions level. var is superior when it comes to readability, := is good for declaring assigning value to existing variable (bad).
	
- [Using const]: Declare an immutable variable.
	
- [Typed and Untyped Constants]: An untyped constant works exactly like a literal; it has no type of its own but does have a default type that is used when no other type can be inferred. A typed constant can be directly assigned only to a variable of that type. Untyped gives you more flexibility.
	
- [Unused Variable]: Will be complaint by compiler if the variable is not used even once. [Unused constant] are not included in the compiled binary there make it easy to eliminate.
	
- [Naming Variables and Constants]: Go uses Camel case. 
	` var HelloWorld string = "true"`

## Composite Types

- [Arrays - Too Rigid to Use Directly]: Because the size of the array to be part of the type of the array. In addition, you cant use a type conversion to directly convert arrays of different sizes to identical types.
	`var x = [3]int{0, 0, 0}`
	
- [Slices]: A data structure that holds a sequence of values. The length of a slice is not part of its types.
	`var x = []int{0, 0, 0}`
	



