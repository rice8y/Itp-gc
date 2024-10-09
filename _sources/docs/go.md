# Go

Goはコンパイラ言語のため, Google Colaboratory上で直接セルを実行することはできません. そのため, マジックコマンド`%%writefile`を使用して, セル内のコードをファイルとして保存し, そのファイルをコンパイルします.

## インストール

GoはGoogle Colaboratoryの初期設定では使えないため, まずはインストールします.

1. `!apt install -y golang`でインストールします.

```{tip}
シェルコマンドを実行する際には, `!`を使用します (複数行の場合は`%%shell`).
```

以下のような出力が得られればOKです.

![go01](../_images/go01.png)

1. `!go version`でインストール確認をします.

以下のような出力が得られればOKです.

![go02](../_images/go02.png)

## Goプログラムの実行手順

1. Goファイル(`.go`)を作成する.
2. Goファイル(`.go`)を実行する (または, Goファイル(`.go`)をコンパイルして生成された実行ファイルを実行する).

## Hello, World!

以下は, Goで標準出力をする例です.

![go03](../_images/go03.png)

### 解説

#### 1つ目のセル

```go
%%writefile hello.go
package main

import "fmt"

func main() {
  fmt.Printf("Hello, World!\n")
}
```

ここでは, `%%writefile hello.go`により, セル内のコード(マジックコマンド以下)を`hello.go`として保存しています.

#### 2つ目のセル

```bash
!go run hello.go
!go build hello.go
!./hello
```

1行目では, `hello.go`を`go run`で直接実行しています (表面的に). 2行目では`go build`で`hello.go`をコンパイルし, 実行ファイル`hello`を生成しています. 3行目では, 実行ファイル`hello`を実行しています.
