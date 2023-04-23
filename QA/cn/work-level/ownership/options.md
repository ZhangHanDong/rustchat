# 选择题


## 选择题1：

关于 Rust 的所有权系统，以下哪项说法是正确的？

A. 所有权系统可以确保内存安全，但会导致性能降低。
B. 所有权系统允许一个变量在多个作用域中同时拥有可变引用。
C. 所有权系统的目标是在编译时确保内存安全，无需垃圾收集。
D. 所有权系统仅适用于堆上的内存，不适用于栈上的内存。


## 选择题2

```rust
#[derive(Debug, Clone, Copy)]
struct Point {
    x: i32,
    y: i32,
}

fn main() {
    let p1 = Point { x: 1, y: 2 };
    let p2 = p1;
    println!("p1: {:?}", p1);
}
```
这段代码在编译时会出现什么情况？

A. 编译成功，输出 "p1: Point { x: 1, y: 2 }"
B. 编译失败，因为 Point 类型没有实现 Copy trait
C. 编译失败，因为 Point 类型没有实现 Clone trait
D. 编译失败，因为 Point 类型没有实现 Debug trait

## 选择题 3

以下哪个类型实现了 Copy trait？

A. `Vec<i32>`
B. `String`
C. `(i32, f32)`
D. `Box<i32>`