# 所有权选择题答案


## 答案

1. 正确答案：C

编译失败，因为 s1 的所有权已经被移动到 s2。在 Rust 中，当一个变量被赋值给另一个变量时，前者的所有权会被移动（Move）到后者。在这个例子中，s1 的所有权被移动到了 s2，导致 s1 变得无效。因此，在 println! 语句中尝试访问 s1 时会导致编译错误。
