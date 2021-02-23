# 用Rust写出你第一个程序

## 把 `Cargo` 当作习惯

对于简单项目， `Cargo` 并不比 `rustc` 提供了更多的优势，不过随着开发的深入，终将证明其价值。对于拥有多个 `crate` 的复杂项目，交给 `Cargo` 来协调构建将简单的多。


- `Rust` 内置了一个包管理器 `cargo`，它会随着 `Rust` 的安装而安装。

- `cargo` 类似于 `Python` 中的 `pip` 或 `Ruby` 中的 `RubyGems` 或 `Node.js` 中的 `NPM`。

- 当然了`cargo` 不仅仅是一个包管理器，它还是 `Rust` 的项目管理利器。

## Hello, World!

`Cargo` 是 `Rust` 的构建系统和包管理器。大多数 `Rustacean` 们使用 `Cargo` 来管理他们的 `Rust` 项目，因为它可以为你处理很多任务，比如构建代码、下载依赖库并编译这些库。

- 检测是否安装输入命令`cargo --version`

创建一个基于`cargo`的项目，在你需要工作的目录输入下面命令

``` shell
$ cargo new hello_cargo
$ cd hello_cargo
```
![步骤截图](https://tva1.sinaimg.cn/large/008eGmZEgy1gmm424ai02j30vl0ozth6.jpg)

先不急着coding，先看看`Cargo.toml`文件里面是啥

```toml linenums="1"
[package]
# 项目名字
name = "hello_cargo"
# 项目版本
version = "0.1.0"
# 开发者信息
authors = ["Dings <deen.job@qq.com>"]
# edition 字段表明代码应该使用哪个版本编译。如果该字段不存在，其默认为 2015 以提供后向兼容性
edition = "2018"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

# 项目依赖的相关配置
[dependencies]

```

**相关命令**

- `cargo build`  构建了项目
- `cargo run`    编译和运行
- `cargo check`  快速检查代码确保其可以编译
- `cargo build --release` 来优化编译项目

![相关截图](https://tva1.sinaimg.cn/large/008eGmZEgy1gmm4okc7g4j30vi0ew76r.jpg)


在你的`main.rs`写入代码

```rust linenums="1" 
// 我感觉你不是写，我估计你是复制粘贴😜
fn main() {
    println!("Hello, world!");
} 
```

使用`cargo run`跑起来你的代码

```shell
Hello, world!
```

**到此为止，恭喜你写出来了第一个Rust程序！！牛批😜**
