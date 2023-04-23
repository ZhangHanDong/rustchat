# 编码实现

## 编码实现 1

要修复这个问题，我们需要避免 s 的所有权被移动到 foo 函数。我们可以将 foo 函数的参数类型更改为 &str，这样它将接受一个字符串切片而非 String 类型。这样，我们可以向 foo 函数传递一个对 s 的不可变引用，而不会移动所有权。以下是修复后的代码：

```rust
fn foo(s: &str) -> usize {
    s.len()
}

fn main() {
    let s = String::from("hello");
    let length = foo(&s);
    println!("The length of '{}' is {}.", s, length);
}
```

现在，代码可以正确编译并输出 "The length of 'hello' is 5."。