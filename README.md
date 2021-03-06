## 準備 Go 環境
- https://golang.org/dl/
  - 下載 xxx.tar.gz
  - 解壓縮放到想放的資料夾
    - 直接點選檔案解壓縮
    - 或是下指令 ```sudo tar -C /usr/local -xzf xxx.tar.gz```
    
  - 將路徑註冊到系統變數（在 ~/.bashrc 檔案裡加入底下）
    ```bash
    # 2019.03.19, Go environment
    export PATH=$PATH:/usr/local/go/bin
    ```
    
  - 重新載入設定檔
    ```bash
    $ source ~/.bashrc
    ```
  - 開新的終端機(terminal)來測試指令
    ```bash
    $ go version
    go version go1.12.1 linux/amd64
    ```
<br>

## 直接在線上寫 code
- https://play.golang.org/

<br>

## Hello, World!
- 簡易範例 (檔案名稱：```my_first_go.go```)
  ```go
  package main

  func main() {
    println("Hello, GO!")
  }
  ```
- 編譯執行：
  ```bash
  $ go run my_first_go.go 
  Hello, GO!
  ```

<br>

## 基礎學習資源
- [The Little Go Book](https://www.openmymind.net/The-Little-Go-Book/) ([PDF](https://www.openmymind.net/assets/go/go.pdf))
- [The Little Go Book 繁體中文翻譯版](https://kevingo.github.io/the-little-go-book/)
- [[中] runoob](http://www.runoob.com/go/go-tutorial.html)
- [[英] Tutorial Point](https://www.tutorialspoint.com/go/index.htm)
- [[英] Go: For loops explained](https://programming.guide/go/for-loop.html)

<br>

## 進階學習資源
- [不得不知道的golang知識點之nil](https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/5262/)

<br>

## 如何尋找 go 問題與解法
- 關鍵字加 golang (go + language)<br>如 ```golang how to get the type```

<br>

## 官方 API 文件
- [https://golang.org/pkg/fmt/#Println](https://golang.org/pkg/fmt/#Println)
