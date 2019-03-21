
## Q: [人] 類別繼承自 [動物] 類別

## 檔名：basic-extend-1.go 
```go
package main

import "fmt" // format

// class Animal {
//     public String Name;
//     public void Talk() {...}
// }
type Animal struct {
  Name string
}

func (animal *Animal) Talk() {
  fmt.Println("Hello! My name is " + animal.Name + ".")
}


// class Person extends Animal {
//     public String Name;
// }
type Person struct {
  *Animal // not equal to: Animal *Animal
  Type string
}

func (person *Person) ShowType() {
  fmt.Println("I am " + person.Type)
}


func main() { // entry point
  person := &Person{
    &Animal{"Jeremy"},
    "Human",
  }
  
  fmt.Println("person.Name: " + person.Name)
  fmt.Println("person.Animal.Name: " + person.Animal.Name)
  fmt.Println()
  
  fmt.Print("person.Talk(): "); person.Talk()
  fmt.Print("person.Animal.Talk(): "); person.Animal.Talk()
  fmt.Println()
  
  fmt.Print("person.ShowType(): "); person.ShowType()
  //fmt.Print("person.Animal.ShowType(): "); person.Animal.ShowType()
  // error:
  //   person.Animal.ShowType undefined (type *Animal has no field or method ShowType)
}
```

## 執行結果
```bash
$ go run basic-extend-1.md.go 
person.Name: Jeremy
person.Animal.Name: Jeremy

person.Talk(): Hello! My name is Jeremy.
person.Animal.Talk(): Hello! My name is Jeremy.

person.ShowType(): I am Human
```
