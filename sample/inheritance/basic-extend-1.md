
## Q: [狗] 類別繼承自 [動物] 類別

## 檔名：basic-extend-1.md.go 
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
  fmt.Println("Hello! My name is " + animal.Name)
}


// class Dog extends Animal {
//     void Talk() {...} // overwrite
// }
type Dog struct {
  *Animal // not equal to: Animal *Animal
}

func (dog *Dog) Talk() {
  fmt.Println("Wang! I am " + dog.Name)
}


func main() { // entry point
  dog := &Dog{
    &Animal{"Puppy"},
  }
  fmt.Println("dog.name: " + dog.Name)
  fmt.Print("dog.Talk(): "); dog.Talk() // overwritten
  fmt.Print("dog.Animal.Talk(): "); dog.Animal.Talk()
}
```

## 執行結果
```bash
$ go run basic-extend-1.md.go 
dog.name: Puppy
dog.Talk(): Wang! I am Puppy
dog.Animal.Talk(): Hello! My name is Puppy
```
