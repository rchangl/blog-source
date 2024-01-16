# toml

## 层级

```toml
[package]
name = "demo"

[dependencies]
rand = "0.8.3"
```

## `Cargo.toml`

### 版本号

`0.8.5` 是 `^0.8.5` 的简写，表示大于等于 0.8.5 但小于 0.9.0 的版本。

## `Cargo.lock`

确保构建是可重现的。固定依赖的版本

### 更新 lock

`cargo update` 讲lock更新到符合toml的最新版本
