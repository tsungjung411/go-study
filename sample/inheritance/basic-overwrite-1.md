
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
  Name string
}


func main() { // entry point
  person := &Person{
    &Animal{"Anonymous"},
    "Jeremy",
  }
  
  fmt.Println("person.Name: " + person.Name) // Jeremy
  fmt.Println("person.Animal.Name: " + person.Animal.Name) // Anonymous
  fmt.Println()
  
  fmt.Print("person.Talk(): "); person.Talk() // Anonymous
  fmt.Print("person.Animal.Talk(): "); person.Animal.Talk() // Anonymous
  fmt.Println()
}
```

## 執行結果
```bash
$ go run basic-extend-1.md.go 
person.Name: Jeremy
person.Animal.Name: Anonymous

person.Talk(): Hello! My name is Anonymous. <-- 並不是存取 Person 的 Name
person.Animal.Talk(): Hello! My name is Anonymous.
```
