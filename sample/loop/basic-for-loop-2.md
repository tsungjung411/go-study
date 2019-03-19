## Q: 1 + 3 + 5 + 7 + ... + 97 + 99 = ? （求奇數和）<br>以及 2 + 4 + 6 + 8 + ... + 98 + 100 = ? （求偶數和）

## 檔名：basic-for-loop-2.go 
```go
package main

import (
  "fmt" // format
)

func main() {
  sum_odd := 0
  sum_even := 0
  
  for i := 1; i <= 100; i++ {
    if i % 2 == 0 {
      sum_odd += i
    } else {
      sum_even += i
    }
  }
  
  fmt.Printf("sum_odd = %d\n", sum_odd)
  fmt.Println("sum_even =", sum_even)
}
```

```bash
$ go run basic-for-loop-1.go 
sum_odd = 2550
sum_even = 2500
```
