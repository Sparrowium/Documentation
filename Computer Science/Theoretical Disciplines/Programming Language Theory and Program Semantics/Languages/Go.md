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
	
- [Slices]: A data structure that holds a sequence of values, and it is grow-able. The length of a slice is not part of its types.
	`var x = []int{0, 0, 0}`
	
	- [Multi-dimension Slices]: Slice of Slices
		`var x [][]int`
		
	- [len]: Checking the slice length.
		
	- [append]: Used to grow slices by adding element.
		
	- [Capacity]: The number of consecutive memory locations reserved.
		`cap()`
		
	- [make]: A built-in function to specify the type, length, and the capacity
		`var := make([]int, len, cap)`
		
		- New data will be added to the end of the slice, resulting in growing the slice.
		
	- [Emptying a Slice]: Sets all of the slice's elements to zero. The slice length remain unchanged.
		`clear(slice)`
		
	- [Declaring Slice]: Depends on use cases, either zero (nil) or specified.
		
	- [Slicing Slices]: A slice expression creates a slice from a slice.
		
		- When you take a slice from a slice, you're not making a copy of a slice but instead creates two slice-holder that are sharing memory.
			
		- Whenever you take a slice from another slice, the subslice’s capacity is set to the capacity of the original slice, minus the starting offset of the subslice within the original slice.
		
	- [copy]: Used to create a slice that's independent from the original.
		
	- [Converting Arrays to Slices]: Use `[:]` syntax. It comes at a cost of memory-sharing properties.
		
	- [Converting Slices to Arrays]: By specifying the length of a slice `xArray := [num]int(xSlice)`. When converting slice into array, the memory is copied to a new memory.
	
- [String and Runes and Bytes]: String are represented by a sequence of bytes, or a composed of a sequence of UTF-8. A single rune or byte can be converted to a string. A string can be converted back and forth to a slice of bytes or runes.
	
- [Maps]: Used for sequential data, associate one value to another.
	`var NilMap map[string]int`
	`totalWins := map[string]int{}`
	
	- A map literal’s body is written as the key, followed by a colon (:), then the value. A comma separates each key-value pair in the map, even on the last line. In this example, the value is a slice of strings.
		
	- Map are another variation of slice.
		
	- [The comma ok Idiom]: Tell the difference between a key that's associate with a zero value and a key that's not in the map.
		`v, ok := map["key"]`: v is value, and ok is evaluation of v whether it exist or not.
		
	- [Deleting from Maps]: `delete(map, "key")`
		
	- [Emptying a Map]: `clear(map)`
		
	- [Comparing Maps]: `.Equal(firstmap, secondmap)`
	
- [Structs]: A group of related data.
	```
	type peson struct {
		name string
		age int
		pet string
	}
	```
	- A struct is defined with keyword *type*, the name of the struct type, the keyword *struct* and a pair of braces. Within the braces you list the fields in the struct.
		
	- A *struct literal* can be assigned to a variable.
		
	- [Anonymous Structs]: struct type without name.
		
	- [Comparing and Converting Struct]: Depends on the struct's fields.

## Blocks, Shadows, and Control Structures

- [Blocks]: A place where a declaration occurs. 
	
	- [Package Blocks]: Are declaration outside of any functions.
		
	- [File Blocks]: Are packages that are valid for the file that contains the import statement.
		
	- Within a function, every set of brace {} defines another block.
	
- [Shadowing Variables]: A variable that has the same name as a variable in a containing block.
	```
	func main() {
		x := 10
		if x>5 {
			fmt.Println(x)
			x:= 5
			fmt.Println(x)
		}
		fmt.Println(x)
	}
	```
	
- [if]: A state of wonder where things could be true or false.
	
- [for, Four Ways]: A statement to loop. But it only looping keywords in the language. Go completed this by using the for keyword in four formats.
	
	- [C-style for]: 
		```
		for i := 0; i < 10; i++{
			fmt.Println(i)
		}
		```
		
	- [Condition-Only for Statement]: 
		```
		i := 0
		for ; i<10; i++ {
			fmt.Println(i)
		}
		```
		
	- [The infinite for Statement]: 
		```
		for {
			fmt.Println("Hello")
		}
		```
		
	- [break and continue]: 
		```
		for i := 1; i <= 100; i++ {
			if i%3 == 0 && i%5 == 0 {
				fmt.Println("FizzBuzz")
				continue
			}
			if i%3 == 0 {
				fmt.Println("Fizz")
				continue
			}
			if i%5 == 0 {
				fmt.Println("Buzz")
				continue
			}
			fmt.Println(i)
		}
		```
		
	- [The for-range statement]: For iterating over elements in some of Go's built in types.
		```
		evenVals := []int{2, 4, 6, 8, 10}
		for i, v := range evenVals {
			fmt.Println(i, v)
		}
		```
		
	- [Labeling Your for Statement]: Labels are always indented to the same level as the braces for the block. Nested for loops with labels are rare.
		
	- [Choosing the Right for Statement]: for-range is the best way to walk through a string. The complete for loop are when you aren't iterating from the first element to the last element in a compound type. The condition-only for loop is just while loop. The infinite for loop is useful in some situation.
	
- [switch]: A `switch` statement is a shorter way to write a sequence of `if - else` statements.
	```
	switch variable := condition; value {
	case 1:
		statememnt
	case 2: 
		statement
	default:
		statement
	}
	```

	- [Blank Switches]: Switch statements that doesn't specify the value you're comparing against
		`switch variable := condition; {}`
	
- [goto]: A jump statement (skip statement).

