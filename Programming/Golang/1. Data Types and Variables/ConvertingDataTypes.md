## Converting between data types

### Type casting

- The process of verting on data type to another is known as Type Casting

- Data types can be converted to other data types, but this does not guarante that the value will remain intact



Integer to float


```go

package main

import "fmt"


func main() {

    var i int = 90
    var f float64 = float64(i)

    fmt.Printf(".2f\n", f)

}

>>> go run main.go

90.00
```


Float to integer


```go

package main
import "fmt"


func main() {

    var f float64 = 45.89
    var i int = int(f)

    fmt.Printf(".v\n", i)

}

>>> go run main.go

45
```


`strconv` package

`Itoa()`
- converts integer to string
- returns on value - string formed with the given integer

`Atoi()`
- Converts string to integer
- returns two values - the corresponding integer, error (if any).



Integer to string


```go

package main
import (
"fmt"
"strconv")

func main () {

    var i int = 42
    var s string = strconv.Itoa(i) // conver int to string

    fmt.Printf("%q", s)

}

>>> go run main.go

"42"
```

string to integer

```go
package main
import (
"fmt"
"strconv")

func main () {

    var s string = "200"
    i, err := strconv.Atoi(s)

    fmt.Printf("%v, %T \n", i, i)
    fmt.Printf("%v, %T", err, err)
}

>>> go run main.go
200, int
<nil>, <nil>

```



```go
package main
import (
"fmt"
"strconv")

func main () {

    var s string = "200abc"
    i, err := strconv.Atoi(s)

    fmt.Printf("%v, %T \n", i, i)
    fmt.Printf("%v, %T", err, err)
}

>>> go run main.go
0, int
strconv.Atoi: parsing "200a": invalid syntax, *strconv.NumError

```
