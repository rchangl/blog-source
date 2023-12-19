# heirloom-mailx 命令行邮件客户端

## 安装

`sudo apt-get install heirloom-mailx -y`

## 配置

编辑 `/etc/s-nail.rc` ，在末尾添加：

```shell
set from=xxx@qq.com
set smtp=smtps://smtp.qq.com:465
set smtp-auth-user=xxx@qq.com
set smtp-auth-password=<你的授权码>
set smtp-auth=login
```
