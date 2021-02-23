## `tuple`元组

`tuple`是`复合类型`可以存储多个不同类型的数据，`复合类型`就像我们的菜篮子，里面可以放各种类型的菜。

- `tuple`长度是固定的，而且一旦定义了，就不能再次更改。
- `tuple`是下标从`0`开始。

## `tuple`元组的定义

在定义的时候可以指定存储的数据类型：

```rust linenums='1'
let tuple_name:(data_type1,data_type2,data_type3) = (value1,value2,value3);
```

`Rust` 中元组的定义很简单，就是使用一对小括号 `()` 把所有元素放在一起，元素之间使用逗号 `,` 分隔，当然也可以忽略类型声明。

```rust linenums='1'
let tuple_name = (v1,v2,v3)
```


## `tuple`元组的使用

- 下标访问
- 解构赋值

我们可以使用 `元组名.索引数字` 来访问元组中相应索引位置的元素。索引从 `0` 开始。

如果要输出元组中的所有元素，必须使用 `{:?}` 格式化符：

```rust linenums='1'
fn main() {
    let tuples: (&'static str, i8, f64) = ("🦀", 22, 3.1415927);
    println!("{:?}", tuples);
    // 声明一个可变的tuple
    let mut people = ("tom", "robin", "jarvib");
    // 通过下标访问
    println!("{},{},{}", people.0, people.1, people.2);
    // 修改下标为2的值
    people.2 = "Jarvib Ding";
    // 通过 解构赋值 (destructing)
    let (v1, v2, v3) = people;
    println!("{},{},{}", v1, v2, v3);
}
```
output:
```rust linenums='1'
("🦀", 22, 3.1415927)
tom,robin,jarvib
tom,robin,Jarvib Ding
```