# Typst

Typstは組版システムです. 今までに挙げてきた言語とは目的が異なりますが, 実験的にGoogle ColaboratoryでTypstが使用できるのかを調査してみます. なお, Typstは, 文書ファイル(.typ)をコンパイルしてPDFを生成するため, マジックコマンド`%%writefile`を使用して, セル内のコードをファイルとして保存し, そのファイルをコンパイルします.

## インストール

TypstはGoogle Colaboratoryの初期設定では使えないため, まずはインストールします.

1. 以下のコードをGoogle Colaboratory上で実行します.

> [!CAUTION]
> Rustがインストール済みであることを前提とします. 未インストールの方は[Rust](../docs/rust.md)を参照してください.

```txt
!cargo install --git https://github.com/typst/typst --locked typst-cli
```

> [!TIP]
> シェルコマンドを実行する際には, `!`を使用します (複数行の場合は`%%shell`).

以下のような出力が得られればOKです.

![typ01](./_images/typ01.png)

2. `!cp /root/.cargo/bin/* /usr/local/bin`でバイナリファイルをローカルにコピーします.

3. `typst --version`でインストール確認をします.

以下のような出力が得られればOKです.

![typ02](./_images/typ02.png)

## Hello, World!

以下は, TypstでHello, World!をする例です.

![typ03](./_images/typ03.png)

`!ls`で確認すると, `hello.pdf`が生成されていることが分かります. 実際に, PDF Viewerで確認すると以下のようになります.

![typ04](./_images/typ04.png)

### 解説

#### 1つ目のセル

```typ
%%writefile hello.typ
#set page(width: auto, height: auto)

Hello, World!
```

ここでは, `%%writefile hello.typ`により, セル内のコード(マジックコマンド以下)を`hello.typ`として保存しています.

#### 2つ目のセル

```txt
!typst compile hello.typ
```

ここでは, `typst compile`で`hello.typ`から`hello.pdf`を生成しています.

## ニューラルネットワーク描画

せっかくなのでニューラルネットワークを描画しましょう. ニューラルネットワークの描画には, 私が作成している`cetzuron`パッケージを使用します.

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=rice8y&repo=cetzuron)](https://github.com/rice8y/cetzuron)

まずはインストールします.

### `cetzuron`のインストール

1. `git clone`します.

```txt
!git clone https://github.com/rice8y/cetzuron.git
```

2. `install.sh`でインストールします.

> [!NOTE]
> 一応, `justfile`と`.bat`のインストールスクリプトもあります.

```txt
%%shell
cd cetzuron
chmod +x install.sh
./install.sh
```

以下のような出力が得られればOKです.

![typ05](./_images/typ05.png)

### オートエンコーダ

以下は, オートエンコーダを描画する例です.

![typ06](./_images/typ06.png)

warningが出ていますが無視します. 出力は以下のようになります.

![typ07](./_images/typ07.png)

#### 解説

省略します.

---
<div style="text-align: left;">
  <a href="./go.md">< Go</a>
</div>
