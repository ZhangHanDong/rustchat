# 选择题


## 选择题1：

关于 Rust 的生命周期，以下哪项说法是正确的？

A. 生命周期是编译时概念，主要用于检查引用的有效性。
B. 生命周期注解只能应用于函数参数，而不能应用于函数返回值。
C. 生命周期会影响程序的运行时性能。
D. 生命周期会导致程序在运行时进行垃圾回收。


## 选择题 2

考虑以下 Rust 代码：

```rust
fn main() {
    let x;
    {
        let y = String::from("hello");
        x = &y;
    }
    println!("{}", x);
}
```

这段代码在编译时会出现什么情况？

A. 编译成功，输出 "hello"
B. 编译失败，因为 y 的生命周期在 x 之外
C. 编译失败，因为 x 未被初始化
D. 编译失败，因为 y 的所有权已经被移动到 x

## 选择题 3

考虑以下 Rust 代码：

```rust
fn foo<'a>(x: &'a i32, y: &i32) -> &'a i32 {
    if *x > *y {
        x
    } else {
        y
    }
}

fn main() {
    let x = 5;
    let y = 8;
    let max = foo(&x, &y);
    println!("The maximum value is {}", max);
}
```

这段代码在编译时会出现什么情况？

A. 编译成功，输出 "The maximum value is 8"
B. 编译失败，因为 x 和 y 的生命周期不同
C. 编译失败，因为返回值的生命周期不明确
D. 编译失败，因为 y 的引用没有指定生命周期