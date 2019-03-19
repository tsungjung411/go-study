
## Q: 將數值反轉（如：1230 -> 0321, 6789 -> 9876, 數值前面沒有前綴0）

## 檔名：basic-while-loop-1.go 
```go
package main

import (
  "fmt" // format
  "os"
  "strconv" // string converter
)

func main() {
  
  // iterate each element in os.Args
  for idx, arg := range os.Args {
    fmt.Printf("Args[%d] = %s\n", idx, arg)
  }
  
  if len(os.Args) < 2 {
    os.Exit(1) // has an error
  }
  
  // array to int (string-to-int)
  num, _ := strconv.Atoi(os.Args[1]) 
  palindrome := ""
  
  tmp := num  
  for tmp > 0 {
    digit := tmp % 10
    // int to array (int-to-array)
    palindrome += strconv.Itoa(digit)
    tmp /= 10
  }
  
  println(num, "->", palindrome)
}
```

```bash
$ go run basic-while-loop-1.go
Args[0] = /tmp/go-build801510665/b001/exe/basic-while-loop-1
exit status 1

$ go run basic-while-loop-1.go 1230
Args[0] = /tmp/go-build801510665/b001/exe/basic-while-loop-1
Args[1] = 1230
1230 -> 0321

$ go run basic-while-loop-1.go 6789
Args[0] = /tmp/go-build285300072/b001/exe/basic-while-loop-1
Args[1] = 6789
6789 -> 9876
```

## API 索引
- [strconv.Atoi](https://golang.org/pkg/strconv/#Atoi)
- [strconv.Itoa](https://golang.org/pkg/strconv/#Itoa)
