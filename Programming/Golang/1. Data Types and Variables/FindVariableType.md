## Finding the variable types

Type of variable

- `%T` format specifier

- `reflect.TypeOf` function from the reflect package

Example: 

*using %T*

```go

package main
import "fmt"

func main () {

    var grades int = 42
    var message string = "hello world"
    var isCheck bool = true
    var amount float32 = 5466.54

    fmt.Printf("variable grades = %v is type of %T \n", grades, grades)
    fmt.Printf("variable message = %v is type of %T \n", message, message)
    fmt.Printf("variable isCheck = %v is type of %T \n", isCheck, isCheck)
    fmt.Printf("variable amount = %v is type of %T \n", amount, amount)
}

>>> go run main.go

variable grades = 42 is of type of int
variable message = 'hello world' is of type string
variable isCheck = 'true' is of type bool
variable amount = 5466.54 is of type float32

```

*using `reflect.TypeOf()`*

```go

package main
import (
"fmt"
"reflect"
)

func main() {
    fmt.Printf("Type: %v \n", reflect.TypeOf(1000))
    fmt.Printf("Type: %v \n", reflect.TypeOf("Tom"))
    fmt.Printf("Type: %v \n", reflect.TypeOf(46.0))
    fmt.Printf("Type: %v \n", reflect.TypeOf(true))
}

>>> go run main.go

Type: int
Type: string
Type: float64
Type: bool
```

```go
package main
import (
"fmt"
"reflect"
)

func main() {
    var grades int = 42
    var message string = "hello world"

    fmt.Printf("variable grades=%v is of type %v \n", grades, reflect.TypeOf(grades))
    fmt.Printf("variable message='%v' is of type %v \n", message, reflect.TypeOf(message))

}


>>> go run main.go

variable grades = 42 is of type itn
variable message = 'hello world' is of type string

```