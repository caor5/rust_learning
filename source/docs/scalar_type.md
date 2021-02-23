## 概 述
> `Rust`是一门强类型的语言，所以`类型系统`也是这门语言的重中之重，它体现了语言所支持的不同类型的值，举个例子，比如我们说 `类型系统` 存在的目的，就是`程序在存储或操作某个数之前检查这个数的有效性`。

## Scalar Type

`Rust` 语言中有四种标量数据类型：

- 整型
- 浮点型
- 布尔类型
- 字符类型

> 接下来我们会对每种标量数据类型做一个简单的介绍。

## 整 型

整型能够囊括所有的数字，虽然不可能无穷大，但已经大到足够使用了。

- 最大的整型为 `340282366920938463463374607431768211455`，由 `std::u128:MAX` 定义。

- 最小的整型为` -170141183460469231731687303715884105728`，由 `std::i128:MIN` 定义。

- 整数类型在`Rust`中又分为:`signed`和`unsigned`。

- 有符号整数类型可以存储负数，但是无符号的只能存储整数不能存储负数。

**类型列表👇**

> 当前只列出整数类型，其他类型自行查询资料。

| size   | signed | unsigned |
| ------ | ------ | -------- |
| 8bit   | i8     | u8       |
| 16bit  | i16    | u16      |
| 32bit  | i32    | u32      |
| 64bit  | i64    | u64      |
| 128bit | i128   | u128     |
| Arch   | isize  | usize    |

`arch` 是由 `CPU` 构架决定的大小的整型类型，大小为 `arch` 的整数在 `x86` 机器上为 `32` 位，在 `x64` 机器上为 `64` 位。
每种整型并不都是能存储任意数字的，每种整型只能装下固定大小的数字，如果给予的数字超出了整型的范围则会发生溢出，相信你如果之前写过`Java`也有体会。

代码例子:

```rust linenums="1"
fn main(){
    // 整型
    let i = 00_32; // default scalar type i32
    let age:u8 = 0x16;
    let num:i64 = -64;
    let iarch:isize = i; 
    let uarch:usize = 64;
    println!("i = {} age = {} num = {}",i,age,num);
    println!("iarch = {} uarch = {}",iarch,uarch);
}
```
> 整数支持整数中间存在一个下划线和十六进制赋值，如果给予的数字超出了整型的范围则会发生溢出。

## 浮点型

区分整型和浮点型的唯一指标就是 `有没有小数点`且不能互相转换，定义浮点型变量的时候要注意每种浮点型的最大值和最小值，如果超出可能会赋值失败，也有可能结果不是预期的结果。

```rust linenums="1"
fn main(){
    // 浮点型
    let f = 64.00;
    println!("f is {:?}",f)
    let f:i64 = f;
    println!("f is {:?}",f)
}
```
这段代码里面会发生编译错误，`let f:i64 = f;`

```rust linenums="1" hl_lines="4"
error[E0308]: mismatched types
  --> scalar_type.rs:21:17
   |
21 |     let f:i64 = f;
   |           ---   ^ expected `i64`, found floating-point number
   |           |
   |           expected due to this

error: aborting due to previous error

For more information about this error, try `rustc --explain E0308`.
```
因为新的`f`类型是`i64`，不能自动类型转换！！Rust 中的数字类型与 C/C++ 中不同的是 Rust 语言不允许类型自动转换。

## 布尔型

布尔类型：只有两个可能的取值 `true` 或 `false` 。

## 字符类型 

`Rust` 使用 `char` 作为字符数据类型，这点可谓是继承了 `C/C++`。但与 `C/C++` 不同的是：`Rust` 使用 `UTF-8` 作为底层的编码，`Rust` 选用 `UTF-8` 作为底层编码可谓是顺应时代的潮流。因为编程早就不极限于拉丁语系的国家，像中国、印度、日本等国家都有大量的程序员，并且互联网是开放的，而不只限于存在于中国局部的，所以`Rust`使用的`UTF-8`编码。

``` RUST  linenums="1"
fn main(){ 
    // 字符
    let special_character = '@'; //default
    let alphabet:char = 'A';
    let chinese:char = '丁';
    let emoji:char = '🦀'; // 螃蟹emoji
    println!("special character is {}",special_character);
    println!("alphabet is {}",alphabet);
    println!("chinese is {:?}",chinese);
    println!("emoji is {}",emoji);
}
```

## 其他补充

| 数字字面值     | 例子          |
| -------------- | ------------- |
| Decimal        | `98_222`      |
| Hex            | `0xff`        |
| Octal          | `0o77`        |
| Binary         | `0b1111_0000` |
| Byte(`u8`)only | b`'A'`        |


## 其他资料
- https://github.com/higker/learning-rust-zh