# 选择题


## 选择题1：

在以下代码中：

```rust
fn foo(s: String) -> usize {
    s.len()
}

fn main() {
    let s = String::from("hello");
    let length = foo(s);
    println!("The length of '{}' is {}.", s, length);
}
```

这段代码在编译时会出现什么情况？

A. 编译成功，输出 "The length of 'hello' is 5."
B. 编译成功，输出 "The length of '' is 5."
C. 编译失败，因为 s 的所有权已经被移动到 foo 函数。
D. 编译失败，因为 String 类型不能用作函数参数。

