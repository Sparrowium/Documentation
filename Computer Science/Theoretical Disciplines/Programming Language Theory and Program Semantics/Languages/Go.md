
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
		
		
		
	- 

	-  The first line is a package declaration. Within a Go module, code is organized into one or more packages. The main package in a Go module contains the code that starts a Go program.
		
	- Next there is an import declaration. The import statement lists the packages referenced in this file. Unlike other languages, Go imports only whole packages. You can’t limit the import to specific types, functions, constants, or variables within a package.
		
	- All Go programs start from the main function in the main package. You declare this function with func main() and a left brace.
		
	- After that type `go build` in terminal to build a go program.
		`go build`
	- And then type `./{folder name}` to run your Go Program.


