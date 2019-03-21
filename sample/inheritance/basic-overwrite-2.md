
## Q: 覆寫父類別方法

## 檔名：basic-overwrite-2.go 
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
//     @Override
//     public void Talk() {...}
// }
type Person struct {
  *Animal // not equal to: Animal *Animal
}

func (person *Person) Talk() {
  fmt.Println("Hi! I'm " + person.Name + ".")
}


func main() { // entry point
  person := &Person{
    &Animal{"Jeremy"},
  }
  
  fmt.Println("person.Name: " + person.Name)
  fmt.Println("person.Animal.Name: " + person.Animal.Name)
  fmt.Println()
  
  fmt.Print("person.Talk(): "); person.Talk()
  fmt.Print("person.Animal.Talk(): "); person.Animal.Talk()
  fmt.Println()
}
```

## 執行結果
```bash
$ go run basic-extend-2.md.go 
person.Name: Jeremy
person.Animal.Name: Jeremy

person.Talk(): Hi! I'm Jeremy.
person.Animal.Talk(): Hello! My name is Jeremy.
```
