# Working with source code
  go run vs go build
      |           \
      cache         vendors/produces binaries
                      go build -o hello_world hello.go  
                      
# 3-rd parties
  can be installed with
    go install URL@version
    go install github.com/rakyll/hey@latest

  if GOPATH is configured => $GOPATH/bin
  else $HOME/go/bin

!UPDATES are done in the same way:
  go install URL@version

# vending & linting
  1. go install golang.org/x/tools/cmd/goimports@latest
      goimports -l -w .
                /    \  \
               /      \  \ 
              /        \  ./ - entry point 
            linting     \
                    format in-place

    go install golang.org/x/lint/golint@latest

  2. go install golang.org/x/lint/golint@latest
      * golint ./...      ->> static check
      * go vet ./...      ->> non-trivial analysis
      * go fmt ./...      ->> autoformating
      * golangci-lint run ->> a package for linting & formating  

# MAKEFILE (for automation)

# escaping literals hierarchy 
  `--> '---> \n "string"'`

# var VS :=
  := limits a scope to a function level (within a package)
  var & const for package level variables, constants that should almost never change their values after assignment if being exported

# const
  immutability of value in Go can be achieved only at compile time:
- Numeric literals
- booleans
- strings
- runes
- the built-in functions: complex, real, imag, len and cap
- expressions that consist of operations and preceding values

# untyped VS typed constants
      /           \
  const x = 10    const x int = 10


# switch 

switch myFunc(){
    case x:
    case y || z || format(z):
    default:
}

switch{
    case x > y:
    case z == y:
    default:
}

# defer

# structs: function fields vs methods

type ABC struct {
        A []int
        B []byte
        C func(int) []int // good for callbacks. See "http" package

    }

var a = ABC{
        A:  iArr,
        B:  bArr,
        C:  increment()
    }

a.C() //usage

type DEF struct {
        D string
        E float64
        F bool
    }

func (def *DEF) increment(i int) []int {  // good for mutexes and oop stuff
        r := []rune(def.D)
        return r
   }
   

# Arrays & slices

// nil slice
var s []int

var arr[10]int
var s1 []int = arr[3:4]

len(arr)/cap(arr)

# maps

//nil map
var m[string][]int

// check for an empty map
if m == nil {
        err.Log(msg)
    }

// check for a key&value pair to be present
_, ok := m[key] // --> true/false

// insert a pair
m[newKey] = newValue

// retrieve value
val, ok := m[key]
if !ok { 
    ...
    }


newMap := oldMap

// looping through a map
for keym value := range mapName {

    }

for k, _ := range mapname {

    }

// delete a pair
delete(mapName, key)

// modify a value
m[key] = newValue


# function (as) values

func a(fn func(int, int)[]int) []int{
        return fn(3,5)
    }


# pointers
// pointer's zero value = nil
var i int
var p *int = &* 

p = *p + 1// update pointer value
*p = 30 //set directtly

# functions & methods
func action(args [T]) (return values [T]) { 
    //body 
    return result
    }

type a struct {
        field1 [T]
        field2 [T]
    }
func (a a) Method(args [T]) (return values [T]) { 
    //body
    return result
}

a.Method()

# pointer receivers

type a struct {
        field1 [T]
        field2 [T]
    }
func (a *) Method(...args [T]) (...returnValues [T]) { 
    //body
    return result
}

//somewhere in the project
a.Method()


# interfaces
type I interface {
        M()
    }

type T struct {
        S string
    }

func (t T) M() {
        fmt.Println(t.S)
    }

var hello_world I = T{
    S: "hellow world" 
    }

//prints S value to the terminal
hellow_world.M()





# type assertions
# Erorrs
    custom errors
    if err != nil{}  idiom
    when to panic
    logging errors
    
    debugging toolchain:
        DAP in neovim
        stack trace
        go run -v 
 
# generics
    when

# goroutines
# channels
# sync & waitgroups
# testing
    fizzing
    benching
    unit testing
    integration tests

