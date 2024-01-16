# Markdown 编写优化

## VSCode 的 markdownlint 插件

禁用部分规则：

```json
    "markdownlint.config": {
        "MD014": false,
        "MD024": false,
        // "MD034": false, // 裸露URL
        "MD036": false, // 不得单独使用字体强调（加粗等）
        "MD040": false, // 代码块语言标记
        "MD045": false,
        "MD047": false // 文件结尾必须为空行
    },
```

## VSCode 粘贴图片

`"markdown.copyFiles.destination": {`

key: `**/*.md`  
value: `${documentBaseName}/`

待解决问题： 粘贴中文时

## VSCode 的 Markdown Paste 插件

`Ctrl+Alt+V` 带格式粘贴
