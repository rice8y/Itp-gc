# Java

Javaはコンパイラ言語のため, Google Colaboratory上で直接セルを実行することはできません. そのため, マジックコマンド`%%writefile`を使用して, セル内のコードをファイルとして保存し, そのファイルをコンパイルします.

## Javaプログラムの実行手順

1. Javaファイル(`.java`)を作成する.
2. Javaファイル(`.java`)をコンパイルしてバイトコードファイル(`.class`)を生成する.
3. バイトコードファイル(`.class`)を実行する.

## Hello, World!

以下は, Javaで標準出力をする例です.

![java](../_images/java.png)

### 解説

#### 1つ目のセル

```java
%%writefile Hello.java
public class Hello{
   public static void main(String[] args){
     System.out.println("Hello, World!");
   }
}
```

ここでは, `%%writefile Hello.java`により, セル内のコード(マジックコマンド以下)を`Hello.java`として保存しています.

#### 2つ目のセル

```bash
!javac Hello.java
!java Hello
```

1行目では, `Hello.java`を`javac`でコンパイルし, バイトコードファイル`Hello.class`を生成しています. 2行目では, `java`でバイトコードファイル`Hello.class`を実行しています.

```{tip}
シェルコマンドを実行する際には, `!`を使用します (複数行の場合は`%%shell`).
```
