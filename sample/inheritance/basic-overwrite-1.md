
## Q: 覆寫父類別屬性

## 檔名：basic-overwrite-1.go 
```go
package main

import "fmt" // format

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
//     void ShowType() {...}
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
  fmt.Println("person.name: " + person.Name)
  fmt.Println("person.Animal.name: " + person.Animal.Name)
  fmt.Print("person.Talk(): "); person.Talk()
  fmt.Print("person.Animal.Talk(): "); person.Animal.Talk()
  fmt.Print("person.ShowType(): "); person.ShowType()
}
```

## 執行結果
```bash
$ go run basic-extend-1.md.go 
person.name: Jeremy
person.Animal.name: Jeremy
person.Talk(): Hello! My name is Jeremy.
person.Animal.Talk(): Hello! My name is Jeremy.
person.ShowType(): I am Human
```
