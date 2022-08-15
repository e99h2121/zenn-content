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
