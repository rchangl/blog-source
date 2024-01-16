# 表达式

没有分号的是语句，有分号的是语句

## 范围表达式 (range expression)

`1..5` 左闭右开

`1..=5` 闭区间

## match 表达式

匹配枚举：

```rust
match guess.cmp(&secret_number) {
    Ordering::Less => println!("Too small!"),
    Ordering::Greater => println!("Too big!"),
    Ordering::Equal => println!("You win!"),
}
```
