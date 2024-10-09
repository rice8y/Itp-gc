# C

Cはコンパイラ言語のため, Google Colaboratory上で直接セルを実行することはできません. そのため, マジックコマンド`%%writefile`を使用して, セル内のコードをファイルとして保存し, そのファイルをコンパイルします.

## Cプログラムの実行手順

1. Cファイル(`.c`)を作成する.
2. Cファイル(`.c`)をコンパイルして実行ファイルを生成する.
3. 実行ファイルを実行する.

## Hello, World!

以下は, Cで標準出力をする例です.

![c](./_images/c.png)

### 解説

#### 1つ目のセル

```c
%%writefile hello.c
#include<stdio.h>

int main(){
    printf("Hello, World!");
    return 0;
}
```

ここでは, `%%writefile hello.c`により, セル内のコード(マジックコマンド以下)を`hello.c`として保存しています.

#### 2つ目のセル

```bash
!gcc -hello.c -o hello
!./hello
```

1行目では, `hello.c`を`gcc`でコンパイルし, 実行ファイル`hello`を生成しています. 2行目では, 実行ファイル`hello`を実行しています.

```{tip}
シェルコマンドを実行する際には, `!`を使用します (複数行の場合は`%%shell`).
```
