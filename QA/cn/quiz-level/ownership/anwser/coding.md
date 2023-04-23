# 编码实现

## 编码实现 1

```rust
fn main() {
    let s1 = String::from("hello");
    let s2 = s1.clone();
    println!("{}", s1);
}
```

要修复这个问题，我们需要避免 s1 的所有权被移动到 s2。我们可以通过调用 s1.clone() 来复制 s1 的内容，从而创建一个新的具有相同内容的 String 实例。这样，s1 和 s2 都将拥有各自的所有权，println! 语句可以正确访问 s1，并在屏幕上输出 "hello"。