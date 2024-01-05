# Tmux 终端复用器 terminal multiplexer

## 作用

会话与窗口可以"解绑"：窗口关闭时，会话并不终止，而是继续运行，等到以后需要的时候，再让会话"绑定"其他窗口。

允许在单个窗口中，同时访问多个会话。

允许每个会话有多个连接窗口，因此可以多人实时共享会话。

支持窗口任意的垂直和水平拆分。

## 安装

```shell
# Ubuntu 或 Debian
$ sudo apt-get install tmux

# CentOS 或 Fedora
$ sudo yum install tmux

# Mac
$ brew install tmux
```

## 使用

Tmux 会话管理：

```shell
tmux # 底部[0] 表示tmux伪窗口name ，再启动一个则为[1]（依次递增）
tmux new -s <name> # 创建并指定 name ，底部提示变为指定的 name

tmux detach # 分离会话，（窗口离开当前会话并保留会话）
tmux attach -t <name> # 重接会话 进入某一个会话
tmux switch -t <name> # 切换会话

tmux kill-session -t <name> # 杀死某一个会话
exit # 退出并kill当前会话，或快捷键 Ctrl+d

tmux rename-session -t <old-name> <new-name> # 重命名会话
```

帮助命令：

```shell
<Ctrl+b> <?> # 查看帮助
<esc> / <q> #退出帮助

# 列出所有快捷键，及其对应的 Tmux 命令
tmux list-keys

# 列出所有 Tmux 命令及其参数
tmux list-commands

# 列出当前所有 Tmux 会话的信息
tmux info

# 重新加载当前的 Tmux 配置
tmux source-file ~/.tmux.conf
```

一些快捷键：

```shell
Ctrl+b d # 分离当前会话。
Ctrl+b s # 列出所有会话。
Ctrl+b $ # 重命名当前会话。
```

还有一些窗口操作： [Tmux 使用教程 - 阮一峰的网络日志](https://www.ruanyifeng.com/blog/2019/10/tmux.html)
