## Q: 1 + 2 + 3 + ... + 100

```go
package main

import (
  "fmt" // format
)

func main() {
  sum := 0
  for i := 1; i <= 100; i++ {
    sum += i
  }
  fmt.Printf("sum = %d\n", sum)
  fmt.Println("sum =", sum)
}
```

```bash
$ go run basic-for-loop-1.go 
sum = 5050
sum = 5050
```
