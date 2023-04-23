# 编码实现

## 编码实现 1

```rust
fn multiply_elements(arr: [i32; 3], n: i32) -> [i32; 3] {
    let mut result = [0; 3];
    
    for (index, &value) in arr.iter().enumerate() {
        result[index] = value * n;
    }
    
    result
}
```

这个函数首先创建一个新的数组 result，其初始值为 [0; 3]。接着，使用 enumerate() 和 iter() 方法遍历输入数组 arr 中的元素及其索引。对于每个元素，我们将其值乘以 n 并将结果存储在 result 数组的相应位置。最后，返回 result 数组。