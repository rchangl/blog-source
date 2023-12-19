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

帮助：

```shell
<Ctrl+b><?>
<esc> / <q> #退出帮助
```

启动退出：

```shell
tmux
exit # 或快捷键 Ctrl+d
```
