# 选择题


## 选择题1：

考虑以下 Rust 代码：

```rust
fn main() {
    let s = String::from("hello world");
    let first_word_index = s.find(' ').unwrap();
    let slice = &s[0..first_word_index];
    println!("The first word is: {}", slice);
}
```

这段代码在编译时会出现什么情况？

A. 编译成功，输出 "The first word is: hello"
B. 编译失败，因为 find 方法返回的是一个 Option<usize> 类型
C. 编译失败，因为切片的索引不能用 usize 类型
D. 编译失败，因为 s 的所有权已经被移动到 slice


## 选择题 2

以下代码片段定义了一个名为 my_slice 的切片：

```rust
let my_str = String::from("Rust is awesome!");
let my_slice = &my_str[5..7];
```

请问 my_slice 的值是什么？

A. "Rust"
B. "is"
C. "st"
D. "aw"

## 选择题 3

```rust
fn main() {
    let mut arr1 = [1, 2, 3];
    let arr2 = [4, 5, 6];
    
    arr1 = arr2;
    
    println!("arr1 is now: {:?}", arr1);
}
```

这段代码在编译时会出现什么情况？

A. 编译成功，输出 "arr1 is now: [4, 5, 6]"
B. 编译失败，因为不能将数组 arr2 直接赋值给数组 arr1
C. 编译失败，因为数组长度不匹配
D. 编译失败，因为数组 arr2 是不可变的

## 选择题 4

```rust
fn main() {
    let x = 10;
    let y = &x;
    let z = &y;

    println!("z: {}", z);
}
```

这段代码在编译时会出现什么情况？

A. 编译成功，输出 "z: 10"
B. 编译失败，因为不能将 y 的引用赋值给 z
C. 编译成功，输出 "z: &10"
D. 编译失败，因为类型不匹配

## 选择题 5

```rust
fn main() {
    let x = 5;
    let y = &x as *const i32;
    let z = y as *mut i32;
    unsafe {
        *z += 1;
    }
    println!("x: {}", x);
}
```
这段代码在编译时会出现什么情况？

A. 编译成功，输出 "x: 6"
B. 编译失败，因为不能将 *const i32 转换为 *mut i32
C. 编译失败，因为在安全代码中不允许修改 *mut i32
D. 编译成功，但运行时会出现未定义行为


