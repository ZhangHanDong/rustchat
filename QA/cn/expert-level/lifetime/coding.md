# 编码实现题


## 编码实现 1

以下代码在编译时会报错，因为 s3 的生命周期在 result 之外。请修改代码，使其能够正确编译并输出 "The longest string is longest"。

```rust
fn longest<'a>(s1: &'a str, s2: &'a str) -> &'a str {
    if s1.len() > s2.len() {
        s1
    } else {
        s2
    }
}

fn main() {
    let s1 = String::from("short");
    let s2 = String::from("longer");

    let result;
    {
        let s3 = String::from("longest");
        result = longest(s2.as_str(), s3.as_str());
    }
    println!("The longest string is {}", result);
}
```

