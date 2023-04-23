# 编码实现题


## 编码实现 1

以下代码在编译时会报错，因为在 main 函数中，s 的所有权被移动到了 foo 函数。请修改代码，使其能够正确编译并输出 "The length of 'hello' is 5."。

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

