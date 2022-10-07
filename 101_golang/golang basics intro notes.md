## golang basics intro notes

Topics: [[golang]]  [[go]] [[programming]]

---
# Go (Go lang) Programming Notes and References

- Official: [go.dev](https://go.dev) formally golang.org
- Go Docs: [go.dev/doc/](https://go.dev/doc/)
- Package Info: [pkg.go.dev](https://pkg.go.dev/)
- Go PlayGround: [go.dev/play/](https://go.dev/play/)

## Go Workspace
- bin
- pkg
- src

### GOPATH
- path to go user workspace

### GOBIN
- path to go user compiled binaries

### GOROOT
- path to go installation

## Go CLI commands
```terminal
Usage:

  go <command> [arguments]

The commands are:

  bug         start a bug report
  build       compile packages and dependencies
  clean       remove object files and cached files
  doc         show documentation for package or symbol
  env         print Go environment information
  fix         update packages to use new APIs
  fmt         gofmt (reformat) package sources
  generate    generate Go files by processing source
  get         add dependencies to current module and install them
  install     compile and install packages and dependencies
  list        list packages or modules
  mod         module maintenance
  work        workspace maintenance
  run         compile and run Go program
  test        test packages
  tool        run specified go tool
  version     print Go version
  vet         report likely mistakes in packages

```

- `go fmt` format files in current path
- `go fmt ./...` format all files including sub-directory files
- `go run main.go` build and run single file only, does not create binary
- `go build` build and compile
- `go install` build, compile and create install binary


## Go Modules
- [go.dev/blog/using-go-modules](https://go.dev/blog/using-go-modules)
```
Usage:

  go mod <command> [arguments]

The commands are:

  download    download modules to local cache
  edit        edit go.mod from tools or scripts
  graph       print module requirement graph
  init        initialize new module in current directory
  tidy        add missing and remove unused modules
  vendor      make vendored copy of dependencies
  verify      verify dependencies have expected content
  why         explain why packages or modules are needed
```

- Initialise module
  - `go mod init github.com/username/repo`

- List all modules and dependancies
  - `go list -m all`

- Get latest version
  - `go get example.com/path/pkgname`

- List versions of module or dependency
  - `go list -m -versions example.com/path/pkgname`

- Get specific version of module or dependency (add version number at end of go get)
  - `go get example.com/path/pkgname@v1.0.0`


## Data Types
- Boolean types (true/false)
- Numeric types (integer or floating point values)
- String types (sequence of characters with a definite length used to represent text. Go strings are made up of individual bytes, usually one for each character.)
- Derived types (Pointer values, array types, slice types, structure types, union types, function types, interface types, map types, channel types)

### Integer Types
Go's integer types are: uint8, uint16, uint32, uint64, int8, int16, int32 and int64. 8, 16, 32 and 64 tell us how many bits each of the types use. uint means “unsigned integer” while int means “signed integer”. Unsigned integers only contain positive numbers (or zero). Bytes are an extremely common unit of measurement used on computers (1 byte = 8 bits, 1024 bytes = 1 kilobyte, 1024 kilobytes = 1 megabyte, …) and therefore Go's byte data type is often used in the definition of other types. There are also 3 machine dependent integer types: uint, int and uintptr. They are machine dependent because their size depends on the type of architecture you are using.Generally if you are working with integers you should just use the int type. (source: https://www.golang-book.com/books/intro/3#section1)

```terminal
uint8       the set of all unsigned  8-bit integers (0 to 255)
uint16      the set of all unsigned 16-bit integers (0 to 65535)
uint32      the set of all unsigned 32-bit integers (0 to 4294967295)
uint64      the set of all unsigned 64-bit integers (0 to 18446744073709551615)

int8        the set of all signed  8-bit integers (-128 to 127)
int16       the set of all signed 16-bit integers (-32768 to 32767)
int32       the set of all signed 32-bit integers (-2147483648 to 2147483647)
int64       the set of all signed 64-bit integers (-9223372036854775808 to 9223372036854775807)

byte        alias for uint8
rune        alias for int32

uint     either 32 or 64 bits
int      same size as uint
uintptr  an unsigned integer large enough to store the uninterpreted bits of a pointer value
```

### Floating Types
```terminal
float32     the set of all IEEE-754 32-bit floating-point numbers
float64     the set of all IEEE-754 64-bit floating-point numbers

complex64   the set of all complex numbers with float32 real and imaginary parts
complex128  the set of all complex numbers with float64 real and imaginary parts
```

## Value and Reference Types
### Value Types
*Use pointers to change these in functions*
- int
- float
- string
- bool
- structs

### Reference Types
- slices
- maps
- channels
- pointers
- functions

## Zero values
- false for boolean
- 0 for integers
- 0.0 for floats
- "" for strings
- nil for pointers, functions, interfaces, slices, channels and maps

## Escape Characters

Ref: [https://go.dev/ref/spec](https://go.dev/ref/spec)

```terminal
\a   U+0007 alert or bell
\b   U+0008 backspace
\f   U+000C form feed
\n   U+000A line feed or newline
\r   U+000D carriage return
\t   U+0009 horizontal tab
\v   U+000B vertical tab
\\   U+005C backslash
\'   U+0027 single quote  (valid escape only within rune literals)
\"   U+0022 double quote  (valid escape only within string literals)

```


## Maps and Structs

### Map (Reference Type)
- All keys must be the same type
- All values must be the same type
- Keys are indexed (can iterate over them)
- Used to represent a collection of closely related properties
- Don't need to know all the keys at compile time (can add and remove properties as needed)

```code
// Three ways to create a map
// Examples use string can be other type int etc.

// 1. Using var to create empty zero value map
var mapName[string]string

// 2. Using make to create empty zero value map
mapName := make(map[string]string)

// 3. Creating map with initial values
mapName := map[string]string{
  "itemOne": "This is item one",
  "itemTwo": "This is item two",
}

// Add value to existing map
mapName["itemThree"] = "This is item three"

// Remove value from existing map
delete(mapName, "itemThree")

// Loop/interate over map (k = key, v = value)
for k, v := range mapName {
  fmt.Printf("Key %v has a value of %v\n", k, v)
}
```

### Struct (Value Type)
- Values can be of a different type
- Keys don't support indexing
- Used to represent a "thing" with different properties
- You need to know all the difference fields at compile time

```code
// Example of structs (including nested struct)

// Define struct for contact information
type contactInfo struct {
  email    string
  postCode int
}

// Define struct for person including contactInfo struct
type person struct {
  firstName   string
  lastName    string
  age         int
  contactInfo
}

// Two ways to use / assign a struct
// 1. Create without field names - Not preferred as if struct fields change data may be in incorrect order or not match required type
newUser := person{"David", "Smith", 30, "davidsmith@emailaddr.com", 4001}

// 2. Create using field names - Preferred
newUser := person{
  firstName:   "David",
  lastName:    "Smith",
  contactInfo: contactInfo{
    email:     "davidsmith@emailaddr.com",
    postCode:  4001,
  },
}

```


## Interfaces

- Define a function or method set (shared code between types)
- Re-use code between types / defines contract of types
- Values can have more than one type


## Errors

```terminal
func main() {
	_, err := os.Open("thisfiledoesnotexist.txt")
	defer func() {
		fmt.Println("The deferred BEFORE function ran.")
	}()
	if err != nil {
		//log.Printf("An error occurred: %v, both deferred functions will run.\n", err)
		log.Panicf("An error occurred: %v, the deferred before function only will run.\n", err)
		//log.Fatalf("An error occurred: %v, no deferred functions will run.\n", err)
	}
	defer func() {
		fmt.Println("The deferred AFTER function ran.")
	}()

}
```

```terminal
var ErrCustom = errors.New("ErrCustom: This is a custom returned error.")

func main() {
	_, err := checkResponse("foo")
	if err != nil {
		log.Println(err)
	}
}

func checkResponse(s string) (string, error) {
	if s != "correct" {
		return "Incorrect", ErrCustom
	}
	return "That was correct", nil
}
```



## References
- [go.dev](https://go.dev)
- [golang-book.com](https://www.golang-book.com)

## Additional Information and Articles
- Our Software Dependency Problem [research.swtch.com/deps](https://research.swtch.com/deps)
