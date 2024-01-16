# std - manual

## std::io

`stdin()` 获取输入：

```rust
let mut guess = String::new();
io::stdin()
    .read_line(&mut guess)
    .expect("Failed to read line.");
```

## core::cmp::impls

`fn cmp(&self, other: &u32) -> Ordering`  
`guess.cmp(&secret_number)` 比较

## String 字符串

`pub fn trim(&self) -> &str` 删除字符串的首尾的空白字符

`let guess: u32 = guess.trim().parse().expect("Please type a number!");` 字符串转换

## std::result::Result

<https://doc.rust-lang.org/std/result/enum.Result.html>

`expect(self, msg: &str) -> T` 为Err时直接Panics  

匹配Result：

```rust
let guess: u32 = match guess.trim().parse() {
    Ok(num) => num,
    Err(_) => continue,
};
```