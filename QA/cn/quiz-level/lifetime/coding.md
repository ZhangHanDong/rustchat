# 编码实现题


## 编码实现 1

假设我们有一个结构体 Person，它包含一个名为 name 的 String 字段。现在，请实现一个函数 longest_name，该函数接受两个 Person 的不可变引用，并返回一个指向具有较长名字的 Person 的引用。请考虑生命周期规则，确保函数在编译时不会产生错误。

```rust
struct Person {
    name: String,
}

fn longest_name<'a>(p1: &'a Person, p2: &'a Person) -> &'a Person {
    // 请在此处实现函数
}

```