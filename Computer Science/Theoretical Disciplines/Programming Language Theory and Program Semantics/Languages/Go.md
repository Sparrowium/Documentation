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

## Functions

- [Declaring and Calling Functions]: A function declaration contains four parts: the keyword func, the name of the function, the input parameters, and the return type. 
	
	- The input parameters are listed in parentheses, separated by commas, with the parameters name first and then type second.
	
	- The return type is written between the input parameters closing and he opening braces for function body.
	
	- Go is a *Typed* language, so the parameters must be specified.
		
	- Syntax: 
		```
		func input_name(input1 type, input2 type) type {
			if input1 == statement{
				return result
			}
			return statement/result
		}
		```
	
	- [Simulating Named and Optional Parameters]: 
	
	- Go does not have *named* and *optional input parameters*.
		
	- [Struct]: Used as a fields to simulate named parameters.
		```
		type MyFuncOpts struct{
			var1 string
			var2 int
		}
		
		func MyFunc(opts MyFuncOpts) error {// do something}
		
		func main() {
			MyFunc(MyFuncOpts{
				var1: "value"
				var2: "value"
			})
			
			MyFunc(MyFuncOpts{
				var1: "value"
				var2: "value"})
			}
		}
		```
		
	- [Variadic Input Parameters and Slices]: A parameter that must by the last (for only) parameter in the input parameter list. you indicate it by typing ... before the type ends. It's makes the variable created within a function a slice of the specified type.
		``` 
		func addTo(base int, vals ...int) []int {
			out := make([]int, 0, len(vals))
			for _, v := range vals {			
				out = append(out, base+v)
			}
		return out
		}
		```
		
	- [Multiple Return Values]: Returning multiple values.
		
	- [Multiple Return Values Are Multiple Values]: Same concept.
		
	- [Ignored Return Values]: Using *_* in front of a variable.
		
	- [Named Return Values]: Specifying name for return values.
		
	- Never use *Blank* Returns.
	
- [Functions Are Values]: The type of a function is a built out of the keyword func and the types of the parameters and return values. This combination is called the *signature* of the function. Any function that has the exact same number and types of parameters and return values meets the type signature.
	
	- The default value for a function variable is *nil*.
		
	- [Function Type Declaration]: Same concept as struct you can use the type keyword to define a function type.
	`type opFuncType func(int,int) int`
		
	- [Anonymous Functions]: Are functions that are created inside another function, sometime called inner function/ anonymous. 
		
	- You declare a anonymous function with the keyword func followed by the input parameters, the return values, and the opening braces.
		
	- They are useful for *defer statements* and *launching goroutines*.
	
- [Closures]: Functions declared inside function. They are able to access and modify variables declared in the out function.
	
	- When playing with assignment operator, make sure to use the right one since `:=` is different from `=`.
		
	- Closures allow you to limit a function's scope. If a function is going to be called from only one other function, but it’s called multiple times, you can use an inner function to “hide” the called function. This helps to reduce the number of declarations at package level.
		
	- [Passing Function as Parameters]: Since functions are values, it can be passed in as a parameters into other functions.
		
	- [Returning Functions from Functions]: Returning closure from a function.
	
- [defer]: The keyword to cleanup code and resources that is temporary.
	
- [Go is Call by Value]: This is because go always makes a copy of the value of the variable whenever you supply a variable for a parameter to a function.

## Pointers

- [Pointer]: 
	
	- A variable that holds the location in memory where the value is stored.
		
	- [Address]: A pointer that holds a number that indicates the location in memory where the data being pointed to is stored.
		
	- Zero value of a pointer is *nil*.
		
	- The & is the address operator. It precedes a value type and returns the address where the value is stored.
		`pointerToX := &x`
		
	- The * is the indirection operator. It precedes a variable of pointer type and returns the pointed-to value. This is called dereferencing.
		```
		x := 10
		pointerToX := &x
		fmt.Println(pointerToX) // prints a memory address
		fmt.Println(*pointerToX) // prints 10
		z := 5 + *pointerToX
		fmt.Println(z) // print 15
		```
		
	- [Pointer type]: A type that represent a pointer. It is written with a * before a type name. 
	
- [Don't Fear the Pointers]: When a class instance is passed to a function or method, the value being copied is the pointer to the instance. When you use a pointer variable or parameter in Go, you see the exact same behaviors. The difference between Go and these languages is that Go gives you the choice to use pointers or values for both primitives and structs. Most of the time, you should use a value. Values make it easier to understand how and when your data is modified. A secondary benefit is that using values reduces the amount of work that the garbage collector has to do.
	
- [Pointers Indicate Mutable Parameters]: 
	
	- Go constants provide names for literal expressions that can be calculated at compile time. Go has no mechanism to declare that order kinds of values are immutable. But that's where pointer comes and play.
		
	- Since Go is a call-by language, the values passed to functions are copies. For non-pointers types like primitives, structs, and arrays, this mean that the called function cannot modify the original. However, if the pointers is passed in as a parameters then mutability is available.
		
	- nil pointers will not change.
		
	- In order to assign a value to a pointer, the pointer must be dereferenced and then set is available.
	
- [Pointers Are a Last Resort]: Only use them when it is needed, in general have the function instantiate and return the struct instead.
	
	- Pointers parameters are used only when the function expects an interface.
	
- [Pointer Passing Performance]: Mostly in large structs, because the time to pass a pointer into a function is constant in all data sizes, roughly one nanosecond. 
	
- [The Zero Value vs No Value]: Go pointers are also commonly used to indicate the difference between a variable or field that's been assigned the zero value and a variable or field that hasn't been assigned a value at all. If distinction matters, use nil pointer to represent unassigned variable or struct field.
	
- [Map vs Slices]: Maps are bad when it comes to API-design level because you have to trace back. Slice that’s passed to a function can have its contents modified, but the slice can’t be resized.
	
- [Slices as Buffers]: Rather than returning a new allocation each time you read from a data source, you create a slice of bytes once and use it as a buffer to read data from the data source.
	
- [Reducing the Garbage Collector's Workload]: 
	
	- [Stack]: A consecutive block of memory.
		
	- [Stack Pointer]: Tracks the last location where memory was allocated. 
		
	- [Stack Frame]: A frame of data that got pushed on the stack.
		
	- When a function exits, its return values are copied back to the calling function via the stack, and the stack pointer is moved back to the beginning of the stack frame for the exited function, deallocating all the stack memory that was used by that function’s local variables and parameters.
		
	- In order for Go to allocate the data the pointer points to on the stack, several conditions must be true. The data must be a local variable whose data size is known at compile time. The pointer cannot be returned from the function. If the pointer is passed into a function, the compiler must be able to ensure that these conditions still hold. If the size isn’t known, you can’t make space for it by moving the stack pointer. If the pointer variable is returned, the memory that the pointer points to will no longer be valid when the function exits. When the compiler determines that the data can’t be stored on the stack, we say that the data the pointer points to escapes the stack, and the compiler stores the data on the heap.
		
	- [Heap]: Memory that's managed by the garbage collector.
		
	- Any data that’s stored on the heap is valid as long as it can be tracked back to a pointer type variable on a stack. Once there are no more variables on the stack pointing to that data, either directly or via a chain of pointers, the data becomes garbage, and it’s the job of the garbage collector to clear it out.
		
	- [Escape Analysis]: Analyze whether the data is trash and needs to be escape. Sometimes it sends to the heap which may cause memory corruption.
		
	- You reduce the garbage collector’s workload by making sure that as much as possible is stored on the stack. Slices of structs or primitive types have their data lined up sequentially in memory for rapid access. And when the garbage collector does do work, it is optimized to return quickly rather than gather the most garbage. The key to making this approach work is to simply create less garbage in the first place.
	
- [Tuning the Garbage Collector]: Doubling the value of GOGC will halve the amount of CPU time spent on GC. Limiting the amount of memory prevent unwanted memory overflow.

## Types, Methods, and Interfaces

- [Types in GO]: 
	```
	type Person struct {
		Firstname string
		Age int
		
	}
	``` 
	- This should be read as declaring a user-defined type with the name Person to have the underlying type of the struct literal that follows.
		
	- In addition to struct literals, you can use any primitive type or compound type literal to define a concrete type.
		```
		type Score int
		type Converter func(string)Score
		type TeamScores map[string]Score
		```
	- Go allows you to declare a type at any block level, from the package block down. However, you can access the type only from within its scope. The only exceptions are types exported from other packages.
	
- [Methods]: 
	```
	type Person struct {
		FirstName string
		LastName string
		Age int
	}
	func (p Person) String() string {
		return fmt.Sprintf("%s %s, age %d", p.FirstName, p.LastName, p.Age)	
	}
	```
	- The Method declaration look like function declaration, with one addition: the *receiver* specification. The receiver appears between the keyword func and the name of the method. Like all other variable declarations, the receiver name appears before the type. By convention, the receiver name is a short abbreviation of the type’s name, usually its first letter. It is nonidiomatic to use this or self.
		
	- Just like functions, method names cannot be overloaded. You can use the same method names for different types, but you can’t use the same method name for two different methods on the same type.
		
	- There is one key difference between declaring methods and functions: methods can be defined only at the package block level, while functions can be defined inside any block.
		
	- [Point Receivers and Value Receivers]: Point Receivers (the type is the pointer), Value Receivers (the type is a value type). When a type has any pointer receiver method, a common practice is to be consistent and use pointer receivers for all methods, even on the ones that doesn't modify the receivers. 
		
	- [Methods are Function Too]: Methods and Functions are really alike that sometimes you can use methods instead of function whenever there's an instance of a function type.
		
	- [Functions vs Methods]: If the data changes during run time use methods. If if just based on input, use function.
		
	- [Type Declarations aren't Inheritance]: This is because the type has no hierarchy, despite it has underlying types.
		
	- [Types are Executable Documentation]: Because they provides a name for a concept and describing the kind of data that is expected. 
	
- [iota Is for Enumerations-Sometimes]:
	
	- [Enumerations]: A concept that allow you to specify that a type can have only a limited set of values. 
		
	- Unfortunately, Go said no. Instead it has iota, which lets you assign an increasing value to a set of constants.
		
	- The iota concept is to create a struct based on *int* then use a const block to define a set of values. When the compiler see *iota* the value will increment for each constant in the block
		```
		type MailCategory int
		const (
			Uncategorized Mailcategory = iota #0
			Personal #1
			Spam #2
		)
		```
	- If you insert a new identifier, everything will be re-numbered.
	
- [Use Embedding for Composition]:
	```
	type Employee struct {
		Name string
		ID string
	}
	
	func (e Employee) Description() string {
		return fmt.Sprintf("%s (%s)", e.Name, e.ID)
	}
	
	type Manager struct {
		Employee
		Reports []Employee
	}
	
	func (m Manager) FindNewEmployees() []Employee {
		// do business logic
	}
	```
	- This makes Employee an embedded field. Any fields or methods declared on an embedded field are promoted to the containing struct and can be invoked directly on it.
		```
		m := Manager{
			Employee: Employee{
				Name: "Bob Bobson",
				ID: "12345",
			},
			Reports: []Employee{},
		}
		fmt.Println(m.ID) // prints 12345
		fmt.Println(m.Description()) // prints Bob Bobson (12345)
		```
	- If the containing struct has fields or methods with the same name as an embedded field, you need to use the embedded field’s type to refer to the obscured fields or methods.
	
- [Embedding is not Inheritance]: That is because you cannot assign a variable of a type that contains Embedded fields to a embedded variable.
	
	- Go has no *dynamic dispatch* for concrete types. The methods on the embedded field have no idea they are embedded which result in error.
	
- [Interfaces]: Are defined using the type keyword with the following syntax: 
	```
	type Stringer interface {
		String() string
	}
	```
	- In an interface declaration, an interface literal appears after the name of the interface type. It lists the methods that must be implemented by a concrete type to meet the interface. The methods defined by an interface are the methods set of the interface.
	
- [Interfaces Are Type-Safe Duck Typing]: Because Go interfaces implements implicitly. That is, If the method set for a concrete type contains all the methods in the method set for an interface, the concrete type implements the interface.
	
- [Embedding and Interfaces]: Embedding is not only for struct but for interface too.
	```
	type Reader interface {
		Read(p []byte) (n int, err error)
	}
	type Closer interface {
		Close() error
	}
	type ReadCloser interface {
		Reader
		Closer
	}
	```
- [Accept Interfaces, Return Structs]: It means that the business logic invoked by your functions should be invoked via interfaces, but the output of your functions should be a concrete type. This will allow flexibility and explicitly for the declaration of the functionality being used.
	
	- The primary reason your functions should return concrete types is they make it easier to gradually update a function’s return values in new versions of your code. When a concrete type is returned by a function, new methods and fields can be added without breaking existing code that calls the function, because the new fields and methods are ignored. The same is not true for an interface. Adding a new method to an interface means that all existing implementations of that interface must be updated, or your code breaks.
	
- [Interface and Nil]: You can use nil for representing zero value for an interface, as long as the type field is non-nil, the interface is non-nil. In order for an interface to be considered nil, both the type and the value must be nil.
	
- [Interfaces are Comparable]: Just as an interface is equal to nil only if its type and value fields are both nil, two instances of an interface type are equal only if their types are equal and their values are equal. Avoid different type comparison.
	
- [Empty Interfaces Says Nothing]: Empty interfaces stores a value of any type.
	`var i interface{}`
	
- [Type Assertions and Switches]:
	
	- [Type Assertions]: Names the concrete type that implemented the interface, or names another interface that is also implemented by the concrete type whose value is stored in the interface. 
		
	- [Type Switches]: When there are multiple possible types.
	
- [Use Type Assertions and Type Switches Sparingly]: Type assertions and type switches are useful in some use cases. One common use of a type assertion is to see if the concrete type behind the interface also implements another interface. This allows you to specify optional interfaces. Type switch statements provide the ability to differentiate between multiple implementations of an interface that require different processing. They are most useful when only certain possible valid types can be supplied for an interface. Be sure to include a default case in the type switch to handle implementations that aren’t known at development time.
	
- [Function Types Are a Bridge to Interfaces]: Because Go allows functions to implement interface by replacing a functions parameters to an interface.
	
- [Implicit Interfaces make Dependency Injection Better]:
	
	- [Dependency injection]: Is the concept that your code should explicitly specify the functionality it needs to perform its task.
	
- Go is Practical.
