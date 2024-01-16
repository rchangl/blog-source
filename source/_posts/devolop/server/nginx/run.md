# 运行

## 启动服务

```shell
nginx
```

启动成功没有任何提示，失败则有提示

浏览器访问 localhost 即本机IP 可检查启动成功情况

## 控制服务

```shell
nginx -s 
    quit # 正常停止
    stop # 立即停止
    reload # 重新加载配置文件
    reopen # 重新打开日志文件
```

## 查看进程

```shell
ps -ef|grep nginx
```

master 进程：Nginx主进程。读取验证配置文件，管理 worker 进程

worker 进程：具体执行

## 查看端口占用

```shell
lsof -i:80 # 只查看80端口

# 需要安装 net-tools
sudo netstat -tulpn | grep :80
```