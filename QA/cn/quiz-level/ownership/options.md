# 选择题


1. 选择题：

考虑以下 Rust 代码：

```rust
fn main() {
    let s1 = String::from("hello");
    let s2 = s1;
    println!("{}", s1);
}
```

这段代码在编译时会出现什么情况？

A. 编译成功，输出 "hello"。
B. 编译成功，输出 ""。
C. 编译失败，因为 s1 的所有权已经被移动到 s2。
D. 编译失败，因为 String 类型不能用作函数参数。
