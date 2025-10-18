# 文档导出

文档现在可以作为静态网站导出。该过程将把所有模式转换为人类可读的文档，以 '.html' 页面形式呈现。在此过程中，所有必要的图像、图标、字体、样式表和 JavaScript 库都会被传输到本地目录。

## 进程参数

参数 | 缩写 | 默认值 | 描述 
---|---|---|--
--local-directory | -l | My-Storage/_site | 这是您想要导出静态文件到的本地目录
--remote-directory | -r | My-Storage/_site | 这是文件将在远程目录下存在的文件夹。如果您想在 superalgos.org/docs/index.html 上托管它，那么您需要提供 `-r=docs`，如果您想让文件存在于根目录下，那么您需要传入一个空字符串参数 `-r=""`
--bots | -b | false | 此参数决定是否包含一个 robots.txt 文件以禁止爬取。要启用爬取，添加 `--bots` 或 `-b` 参数
--shtml | 无 | false | 此参数决定是否导出文档为 '\*.shtml' 文件而不是 '\*.html' 文件

## 执行

要导出文档，运行 `node export-docs` 并带上上面列出的所有必要参数