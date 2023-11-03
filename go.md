# Go

`go help`

`go env` - much useful info that gos some way to explaining under the hood workings

`go mod init example/hello` - creates a go.mod file

`go get github.com/mattn/go-sqlite3` gets the package and updates go.mod 

`go get .` does the same for all imports specified in the folder

`go run filename.go`

`go run .`

`go build` makes an exe

`go install` does ?

# Exported names

In Go, a name is exported if it begins with a capital letter. For example, Pizza is an exported name, as is Pi, which is exported from the math package.
For example, pizza and pi do not start with a capital letter, so they are not exported.

When importing a package, you can refer only to its exported names. Any "unexported" names are not accessible from outside the package. 

return values may be named. If so, they are treated as variables defined at the top of the function. A return statement without arguments returns the named return values. This is known as a "naked" return. 


# Types

    bool
    string
    int
    float32 float64

    int8  int16  int32  int64
    uint uint8 uint16 uint32 uint64 uintptr
    byte // alias for uint8
    rune // alias for int32
        // represents a Unicode code point
    complex64 complex128

# Convert - use the type name

    var i int = 42
    var f float64 = float64(i)
    var u uint = uint(f)

# Constants have no shorthand form

    const World = "世界"

# Pointers hold the memory address of values 

    // & generates a pointer
    k := 8
	inc(&k) // pass the pointer to the inc func (as Go passes by value otherwise)

    *k // access the value pointed to

# Defer

    A defer statement defers the execution of a function until the surrounding function returns.
    The deferred call's arguments are evaluated immediately, but the function call is not executed until the surrounding function returns.
    Multiple deferred function calls are pushed onto a stack. When a function returns, its deferred calls are executed in last-in-first-out order. 

# Methods

    structs/types can have methods "added onto" them, like Abs here

    package main

    import (
        "fmt"
        "math"
    )

    type Vertex struct {
        X, Y float64
    }

    func (v Vertex) Abs() float64 {
        return math.Sqrt(v.X*v.X + v.Y*v.Y)
    }

    func main() {
        v := Vertex{3, 4}
        fmt.Println(v.Abs())
    }



