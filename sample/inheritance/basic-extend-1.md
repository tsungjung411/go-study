
## Q: [人] 類別繼承自 [動物] 類別

## 檔名：basic-extend-1.md.go 
```go
package main

import "fmt" // format
import "strconv"

// class Animal {
//     void Talk() {...}
// }
type Animal struct {
  Name string
}

func (animal *Animal) Talk() {
  fmt.Println("Hello! My name is " + animal.Name + ".")
}


// class Person extends Animal {
//     void Talk() {...} // overwrite
// }
type Person struct {
  *Animal // not equal to: Animal *Animal
  Age int
}

func (person *Person) Talk() {
  fmt.Println("Hi! I'm " + person.Name +
    ". I am " + strconv.Itoa(person.Age) + " years old.")
}


func main() { // entry point
  person := &Person{
    &Animal{"Jeremy"},
    25,
  }
  fmt.Println("person.name: " + person.Name)
  fmt.Print("person.Talk(): "); person.Talk() // overwritten
  fmt.Print("person.Animal.Talk(): "); person.Animal.Talk()
}
```

## 執行結果
```bash
$ go run basic-extend-1.md.go 
person.name: Jeremy
person.Talk(): Hi! I'm Jeremy. I am 25 years old.
person.Animal.Talk(): Hello! My name is Jeremy.
```
