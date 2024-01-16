# 宏 macro - manual

## 属性宏

### `[derive(Debug)]`

为结构体自动生成 Debug trait 的实现

## 函数宏

### print

```rust
println!("hello");

let w = "world";
println!("Hello, {}", {w}); // 也可以是数组成员
println!("Hello, {w}"); // 只能是变量，不能是数组成员
```