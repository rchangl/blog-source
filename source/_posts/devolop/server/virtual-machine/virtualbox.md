# VirtualBox 虚拟机配置

## net 网络设置

7.0 UI 在 工具->网络 可以配置 NAT网络。但需要注意的是，端口转发在这配置无效（这是个坑，可能是个bug）

端口转发设置在具体虚拟机的局部设置， 网络->选择net->端口转发按钮点击进行设置

## VirtualBox Headless 启动虚拟机

VBOX 6.1，运行 VboxManager.exe 命令才能使用参数 --type headless。

VirtualBoxVM.exe 使用 --type headless 参数无效。

也可以直接使用 `VBoxHeadless.exe` 运行。

相关实现： [onlyfang/VBoxVmService: Windows Service to run VirtualBox VMs automatically](https://github.com/onlyfang/VBoxVmService)
