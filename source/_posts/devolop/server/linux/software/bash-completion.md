# Linux 命令自动补全 -- bash-completion

Linux 命令行自动补全是指在输入命令或路径时，通过按下 Tab 键自动匹配并补全命令或路径的功能。这是 Linux 命令行中非常实用的功能之一，可以节省大量时间和减少输入错误。

Linux 命令行自动补全功能的实现依赖于 shell 程序。在大多数 Linux 系统中，Bash 是默认的 shell 程序，因此以下介绍如何在 Bash 中启用命令行自动补全：

## 安装 Bash 自动补全插件

在大多数 Linux 系统中，Bash 自动补全插件已经预先安装了，但是如果系统中没有预先安装，您可以使用以下命令安装：

Debian/Ubuntu 系统：`sudo apt-get install bash-completion`  
CentOS/RHEL 系统：`sudo yum install bash-completion`

## 启用 Bash 自动补全

在安装完成后，需要在 Bash 中启用自动补全功能。可以通过编辑 Bash 配置文件 ~/.bashrc 实现：

打开 `~/.bashrc` 文件：`vim ~/.bashrc`  
在文件末尾添加以下内容：

```bash
# enable bash completion in interactive shells
if ! shopt -oq posix; then
  if [ -f /usr/share/bash-completion/bash_completion ]; then
    . /usr/share/bash-completion/bash_completion
  elif [ -f /etc/bash_completion ]; then
    . /etc/bash_completion
  fi
fi
```

这段代码会检查系统中是否安装了 Bash 自动补全插件，并启用自动补全功能。  
重新加载 Bash 配置文件。

完成以上步骤后，需要重新加载 Bash 配置文件，以便使更改生效。可以通过运行以下命令实现：

```shell
source ~/.bashrc
```

或者，可以关闭终端并重新打开它，以便自动重新加载 Bash 配置文件。

## 参考

[linux 命令行自动补全 - 知乎](https://zhuanlan.zhihu.com/p/620027385)