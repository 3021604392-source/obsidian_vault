
[夸克网盘分享](https://pan.quark.cn/s/2d212fa3965c#/list/share)
对于纯小白来说直接在官网安装解压即可。
解压后得到四个文件：.rtf与.txt——版权声明文件，.html——用户指南，pandoc.exe——命令行工具。

## 介绍

将文件从一种标记格式转换为另一种格式（比如 html 和 markdown等标记语言），它可以将文档在 Markdown、LaTeX、reStructuredText、HTML、Word docx 等多种标记格式之间相互转换，并支持输出 PDF、EPUB、HTML 幻灯片等多种格式。

## 信息查看

查看程序支持的输入文件格式：

```text
pandoc --list-input-formats
```

查看程序支持代码高亮的编程语言：

```text
pandoc --list-highlight-languages
```

查看程序帮助：

```text
pandoc --help
```

## 常用命令

Pandoc支持多种命令，以下是一些常用的命令。

### 1. 转换Markdown为HTML

```text
pandoc -s input.md -o output.html
```

其中“-s input.md”表示将Markdown文件转换为HTML文件，“-o output.html”表示将结果输出到output.html文件中。

### 2. 转换Markdown为PDF

```text
pandoc -s input.md -o output.pdf
```

和将Markdown转换为HTML的命令类似，只是输出的文件类型不同，需要使用PDF。

### 3. 转换多个文件

```text
pandoc -s file1.md file2.md -o output.html
```

可以同时将多个Markdown文件转换为同一个格式的文件。

### 4. 引入CSS样式

```text
pandoc -s input.md -o output.html --css=mycss.css
```

可以使用--css选项引入自定义的CSS样式。

### 5. 生成目录

```text
pandoc -s input.md -o output.html --toc
```

可以在生成的HTML文件中自动生成目录。

### 6. 转换为其他格式

```text
pandoc -s input.md -o output.docx
```

除了将Markdown转换为HTML或PDF，还可以将其转换为Word等其他格式

## 实际操作

桌面上放了我需要转换的word文档，（注意需要保存为docx），利用如下命令来实现格式转化。

```text
pandoc -s input.docx -t markdown -o output.md
```