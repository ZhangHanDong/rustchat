# 编码实现



## 编码实现1

```rust
struct Person {
    name: String,
}

fn longest_name<'a>(p1: &'a Person, p2: &'a Person) -> &'a Person {
    if p1.name.len() > p2.name.len() {
        p1
    } else {
        p2
    }
}
```

这个实现接受两个具有相同生命周期 'a 的 Person 引用，并返回一个具有相同生命周期的 Person 引用。这样可以确保返回的引用在调用方的上下文中是有效的。函数内部比较 p1.name.len() 和 p2.name.len() 的大小，根据名字的长度返回相应的 Person 引用。