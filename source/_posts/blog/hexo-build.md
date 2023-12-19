# 搭建Hexo

## 同步源文件至Github，防止文件丢失

Github 创建仓库

```shell
# 关联远程仓库
git remote add origin https://github.com/rchangl/blog-source.git

# git 操作
git add .
git commit -m "first commit"
git push -u origin main
```

## 安装图片插件

```shell
npm install git://github.com/yiyungent/hexo-asset-img.git#main
```

`_config.yml` 配置： `post_asset_folder: true`

使用方式：

``` markdown
docname
├── xxx.jpg
└── logo.png
docname.md

![logo](docname/logo.png)
```

*注意此插件有个问题未能解决，在代码块里的*

## 安装标题生成插件

<https://www.npmjs.com/package/hexo-autotitle>  
<https://github.com/rchangl/hexo-autotitle>

```shell
npm i hexo-autotitle --save
```

## `_config.yml` 信息配置

博客根目录的 `_config.yml` 配置文件

`title: 的博客` 博客名  
`author: RC` 作者名  
`language: zh-CN` 语言

## 生成博客

```shell
hexo cl # 清除已生成的文件（避免无用目录残留等）
hexo g # 生成相关的网页文件
hexo d # 将生成好的博客同步到 Github
```

`hexo g` `hexo d` 可以合并为 `hexo g -d`

```shell
hexo s # hexo server 本地测试
```

## hexo-excerpt 插件

首页仅显示文章摘录而不是全文

使用插件：[hexo-excerpt](https://github.com/chekun/hexo-excerpt)

安装：

```shell
npm install hexo-excerpt --save
```

`_config.yml` 配置显示内容的多少：

```shell
excerpt:
  depth: 10
```

## Wikitten 主题

有非常好的分类检索

```shell
cd your-hexo-directory
git clone https://github.com/zthxxx/hexo-theme-Wikitten.git themes/Wikitten
```

`_source` `_scaffolds` 配置一些基本页面

`_config.yml.example` 重命名为 `_config.yml` 以便配置主题  
配置大多相同于 [icarus](https://ppoffice.github.io/hexo-theme-icarus/Configuration/icarus用户指南-主题配置/)

使用主题

`theme: Wikitten`

一些配合使用的插件：

```shell
hexo-autonofollow       // automatic make user open external links in new tab
hexo-directory-category // automatic categorize article according to their file directory
hexo-generator-feed     // generate Atom 1.0 or RSS 2.0 feed
hexo-generator-json-content // generate a json content file for site search
hexo-generator-sitemap  // generate sitemap
```

更多： <https://github.com/zthxxx/hexo-theme-Wikitten>

### hexo-directory-category 插件

Install :

```shell
npm install --save hexo-directory-category
```
