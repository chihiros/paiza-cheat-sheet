# Paizaチートシート
## 標準入力を受け取る
### 一次元配列を受け取る場合
- 入力例
```sh
go run main.go
8
3 5
```

```go
package main

import (
	"bufio"
	"fmt"
	"os"
	"strconv"
	"strings"
)

func main() {
	sc := bufio.NewScanner(os.Stdin)

	sc.Scan()
	num, _ := strconv.Atoi(sc.Text())
	fmt.Printf("num: %d\n", num)

	sc.Scan()
	line := strings.Split(sc.Text(), " ")

	var row []int
	for _, data := range line {
		tmp, _ := strconv.Atoi(data)
		row = append(row, tmp)
	}

	fmt.Printf("%#v\n", row)
  
  // ---- ここ以降に関数を実装していく ----
}  
```

### 多次元配列を受け取る場合
- 入力例
```sh
go run main.go
2 3
1 2 2
2 3 5
10 4 5
```

```go
package main

import (
	"bufio"
	"fmt"
	"os"
	"strconv"
	"strings"
)

func main() {
	sc := bufio.NewScanner(os.Stdin)

	sc.Scan()
	size := strings.Split(sc.Text(), " ")
	y, _ := strconv.Atoi(size[0])
	x, _ := strconv.Atoi(size[1])

	rows := make([][]int, y)
	for i := 0; i < y; i++ {
		rows[i] = make([]int, x)
		sc.Scan()

		line := strings.Split(sc.Text(), " ")
		for j := 0; j < x; j++ {
			rows[i][j], _ = strconv.Atoi(line[j])
		}
	}
	fmt.Printf("%#v\n", rows)
  
  // ---- ここ以降に関数を実装していく ----
}
```
