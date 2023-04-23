# 编码实现答案


## 编码实现 1

```rust
fn string_concat(s1: String, s2: String) -> String {
    s1 + &s2
}
```

这个实现利用了 String 类型的 Add trait 实现，将 s1 和 s2 的内容拼接在一起。注意，这里我们将 s2 以不可变引用的形式传递，这样就不会消耗它的所有权，避免了额外的内存拷贝。