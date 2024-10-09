# C++

C++はコンパイラ言語のため, Google Colaboratory上で直接セルを実行することはできません. そのため, マジックコマンド`%%writefile`を使用して, セル内のコードをファイルとして保存し, そのファイルをコンパイルします.

## C++プログラムの実行手順

1. C++ファイル(`.cpp`)を作成する.
2. C++ファイル(`.cpp`)をコンパイルして実行ファイルを生成する.
3. 実行ファイルを実行する.

## Hello, World!

以下は, C++で標準出力をする例です.

![cpp](./_images/cpp.png)

### 解説

#### 1つ目のセル

```cpp
%%writefile hello.cpp
#include <iostream>

int main(){
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```

ここでは, `%%writefile hello.cpp`により, セル内のコード(マジックコマンド以下)を`hello.cpp`として保存しています.

#### 2つ目のセル

```txt
!g++ -hello.cpp -o hello
!./hello
```

1行目では, `hello.cpp`を`g++`でコンパイルし, 実行ファイル`hello`を生成しています. 2行目では, 実行ファイル`hello`を実行しています.

```{tip}
シェルコマンドを実行する際には, `!`を使用します (複数行の場合は`%%shell`).
```
