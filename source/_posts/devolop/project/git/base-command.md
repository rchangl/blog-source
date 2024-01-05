# Git 基本命令

## 初始化

```shell
git init
```

## 分支

```shell
git branch <branchname> # 分支创建

git branch # 分支查看

# 分支切换
git checkout <branchname>
git switch <branchname>

git branch -d <branchname) # 分支删除

git merge <other-branch> # 分支合并
```

## commit

```shell
git commit -a 'describe text' # 自动add并commit所有更改
```

## push

带上 `-u` 参数其实就相当于记录了push到远端分支的默认值，这样当下次我们还想要继续push的这个远端分支的时候推送命令就可以简写成 `git push` 即可。

```shell
git push <远程主机名> <本地分支名>:<远程分支名>
git push <远程主机名> <本地分支名> # 本地分支名与远程分支名相同，可省略冒号
```
