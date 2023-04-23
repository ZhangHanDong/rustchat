# 编码实现题


## 编码实现 1

以下代码在编译时会报错，因为在 main 函数中，s1 的所有权被移动到了 s2。请修改代码，使其能够正确编译并输出 "hello"。

```rust
fn main() {
    let s1 = String::from("hello");
    let s2 = s1;
    println!("{}", s1);
}
```