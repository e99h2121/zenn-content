---
title: "Rustプログラミング入門 at Udemy" # 記事のタイトル
emoji: "📝" # アイキャッチとして使われる絵文字（1文字だけ）
type: "tech" # tech: 技術記事 / idea: アイデア記事
topics: ["初心者", "Udemy", "Rust"] # タグ。["markdown", "rust", "aws"]のように指定する
published: true # 公開設定（falseにすると下書き）
---

## Rustプログラミング入門

[Rustプログラミング入門 (最高峰・最難解言語) | Udemy](https://www.udemy.com/course/rust-os-system/) の学習メモ

## Rust言語

- 2015年リリースの静的型付け言語
- C/C++ の代わり
- C/C++ 並みに高速で、C/C++のメモリ安全性を克服するため言語仕様として保証
- 「所有権」という概念
    - GC(ガベージコレクション)の複雑さに懸念を持っていた
    - [Rustのメモリ管理って面白い - Qiita](https://qiita.com/ksato9700/items/312be99d8264b553b193)
- 処理速度
- 開発者が好きな言語5年連続1位 (Stack overflow survey)
- 2021年Rust Foundationの設立
- 一度習得してしまえば一生使える (システムプログラミング言語)

## The book

https://doc.rust-jp.rs/book-ja/

https://doc.rust-lang.org/book/ch01-01-installation.html

`curl --proto '=https' --tlsv1.3 https://sh.rustup.rs -sSf | sh`


```
Rust is installed now. Great!

To get started you may need to restart your current shell.
This would reload your PATH environment variable to include
Cargo's bin directory ($HOME/.cargo/bin).

To configure your current shell, run:
source "$HOME/.cargo/env"
```

## Cargo

`cargo new rust_lesson1`

```
C:\workspaces\rust>cargo new rust_lesson1
     Created binary (application) `rust_lesson1` package
```


## Hello world

https://www.rust-lang.org/tools/install
> You may need to install the Visual Studio C++ Build tools when prompted to do so. If you are not on Windows see "Other Installation Methods".

[rustの開発環境構築メモ（on WIndows10） - 色々なメモ。](https://hebogna.hatenablog.com/entry/2017/12/31/211741)


```
 *  実行するタスク: C:\Users\s5551\.cargo\bin\cargo.exe run --package rust_lesson1 --bin rust_lesson1 

   Compiling rust_lesson1 v0.1.0 (C:\workspaces\rust\rust_lesson1)
    Finished dev [unoptimized + debuginfo] target(s) in 2.08s
     Running `target\debug\rust_lesson1.exe`
Hello, world!

```

- package
- crate
- module



```
mod vars;

fn main() {
    println!("Hello, world!");
    vars::run();
}
```

```
pub fn run(){
    println!("this is vars module")
}
```

https://github.com/GomaGoma676/rust-lesson


## アプリケーションのメモリ

- Heap ... String, Vector
- Stack ... サイズが決まった変数や配列など
- Static ... const, 文字列リテラルの実態
- Text ... コード


```
fn main() {
    let a = 10;
    let b = 20;
    println!("{} {}", a, b)
}
```

## Mutable, Immutable

- 型推論
- [アンダースコア(Rustの基本構文-3-) - Qiita](https://qiita.com/jin237/items/59ef229a4de30cb8203b)
- シャドーイング: [Rustのシャドーイングについて - やってみる](https://ytyaru.hatenablog.com/entry/2020/08/03/000000)

## 所有権

- 二重解放エラー
- 文字列スライスはデータを所有しない

## Stack overflow, Vector型

- スタックは8MB

```
error: process didn't exit successfully: `target\debug\rust_lesson1.exe` (exit code: 0xc00000fd, STATUS_STACK_OVERFLOW)
```

## その他

- 所有権・参照・借用
- ライフタイム (Non-Lexical Lifetime)
- ダングリングポインタ
- RAII (Resource Acquisition Is Initialization)
- Generics
- Generic lifetime annotation
- 構造体と列挙型
- マッチングパターン
- トレイトとトレイト境界
    - [Rustのtrait(トレイト)について - Qiita](https://qiita.com/ishishow/items/23cd4dd8291145f2db71)
- ユニットテスト
- 外部ライブラリとカスタムライブラリ
    - https://crates.io/

## 参考記事

- [Re:FizzBuzzから始めるRust生活 - Qiita](https://qiita.com/hinastory/items/543ae9749c8bccb9afbc)

