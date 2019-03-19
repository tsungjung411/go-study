## Q: 找出 2～100 的質數

## 檔名：basic-for-loop-4.go 
```go
package main

import (
  "fmt" // format
  "math"
)

func main() {
  for i := 2; i <= 100; i++ {
    
    // cannot use i (type int) as type float64 in argument to math.Sqrt
    // end := math.Floor(math.Sqrt(i))
    end_condition := int(math.Floor(math.Sqrt(float64(i))))
    
    //is_prime := true
    var is_prime bool = true
    
    for j := 2; j <= end_condition; j++ {
      if i % j == 0 {
        is_prime = false
        break
      }
    }
    
    if is_prime {
      fmt.Println(i, "是質數")
    }
  }
}
```

```bash
$ go run basic-for-loop-4.go 
2 是質數
3 是質數
5 是質數
7 是質數
11 是質數
13 是質數
17 是質數
19 是質數
23 是質數
29 是質數
31 是質數
37 是質數
41 是質數
43 是質數
47 是質數
53 是質數
59 是質數
61 是質數
67 是質數
71 是質數
73 是質數
79 是質數
83 是質數
89 是質數
97 是質數
```

## API 參考
- [math.Sqrt](https://golang.org/pkg/math/#Sqrt)
- [math.Floor](https://golang.org/pkg/math/#Floor)
