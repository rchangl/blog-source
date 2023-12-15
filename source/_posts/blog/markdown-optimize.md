# Markdown 编写优化

## VSCode 的 markdownlint 插件

禁用部分规则：

```json
"markdownlint.config": {
    "MD024": false,
    "MD045": false,
    "no-hard-tabs": false
}
```

## VSCode 粘贴图片

`"markdown.copyFiles.destination": {`

key: `**/*.md`  
value: `${documentBaseName}/`

待解决问题： 粘贴中文时

## VSCode 的 Markdown Paste 插件

`Ctrl+Alt+V` 带格式粘贴
