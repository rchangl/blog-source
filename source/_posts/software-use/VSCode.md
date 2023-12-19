# VSCode

## Markdown paste image

VSCode 1.79 更新，支持 Markdown 中直接粘贴图片

但此特性在实际当中展现出了不一致

路径当中的字符：  
纯url可用字符，即为英文字符，则为普通链接  
纯英文加空格，链接会被 `<>` 包裹  
中文无空格，中文字符会被encode  
中文加空格，链接却**不会被encode**，而是链接会被 `<>` 包裹
