## User Input

`Scanf` 

### *Example:*

```go
fmt.Scanf("%<format specifier > (s)", Object_arguments)
```

### *Full example:*

Single Input:

```go

package main 
import "fmt"

func main(){
    var name string
    fmt.Print("Enter your name: ")
    fmt.Scanf("%s", &name)
    fmt.Println("Hey there, ", name)
}

```

Multiple Inputs:

```go

package main 
import "fmt"

func main(){
    
    var name string
    var is_muggle bool

    fmt.Print("Enter your name & are you a muggle: ")
    fmt.Scanf("%s %t", &name, &is_muggle)
    fmt.Println(name, is_muggle)
}

>>> go run main.go

Enter you name & are you a muggle: Hermoine false

Hermione false

```

Scanf return values
___

`count` - the number of arguments that the function writes to

`any` - any error thrown during the execution of the function

Example:

Multiple input:
```go

package main 
import ("fmt")


func main(){
    
    var a string
    var b int

    fmt.Print("Enter a string and a number: ")

    count, err := fmt.Scanf("%s %d", &a, &b)
    
    fmt.Println("count: ", count)
    fmt.Println("error: ", err)
    fmt.Println("a: ", a)
    fmt.Println("b: ", b)
}   


>>> go run main.go

Enter a string and a number: Tom yes
count: 1
error expected integer
a: Tom
b: 0

```