## 範例程式
```go
package main

import (
  "fmt" // format
  "reflect"
)

func main() {
  
  x, y, z, w := evalXYZW()
  fmt.Println("typeof(", x, ") = ", reflect.TypeOf(x))
  fmt.Println("typeof(", y, ") = ", reflect.TypeOf(y))
  fmt.Println("typeof(", z, ") = ", reflect.TypeOf(z))
  fmt.Println("typeof(", w, ") = ", reflect.TypeOf(w))
}

func evalXYZW() (int, string, []int, bool) {
	return 123, "456", []int{123, 456}, true
}
```

## 執行結果
```
typeof( 123 ) =  int
typeof( 456 ) =  string
typeof( [123 456] ) =  []int
typeof( true ) =  bool
```
