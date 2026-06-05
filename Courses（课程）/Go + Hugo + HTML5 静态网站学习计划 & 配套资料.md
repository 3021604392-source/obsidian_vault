
> 学习总目标：由浅入深，落地搭建可公网访问的个人静态站点｜周期：**4 周 / 28 天｜每日 1.5~2.5h**

> 学习优先级：`Hugo > HTML5 > Go语言`

---

## 目录

- [一、整体学习纲要](#%E4%B8%80%E6%95%B4%E4%BD%93%E5%AD%A6%E4%B9%A0%E7%BA%B2%E8%A6%81)
- [二、四周精细化每日学习计划表](#%E4%BA%8C%E5%9B%9B%E5%91%A8%E7%B2%BE%E7%BB%86%E5%8C%96%E6%AF%8F%E6%97%A5%E5%AD%A6%E4%B9%A0%E8%AE%A1%E5%88%92%E8%A1%A8)
    
    - [第 1 周｜Go 基础入门](#%E7%AC%AC1%E5%91%A8go%E5%9F%BA%E7%A1%80%E5%85%A5%E9%97%A87%E5%A4%A9)
    - [第 2 周｜HTML5 + 静态网站架构](#%E7%AC%AC2%E5%91%A8html5%E9%9D%99%E6%80%81%E7%BD%91%E7%AB%99%E6%9E%B6%E6%9E%847%E5%A4%A9)
    - [第 3 周｜Hugo SSG 全流程使用](#%E7%AC%AC3%E5%91%A8hugo-ssg%E5%85%A8%E6%B5%81%E7%A8%8B%E4%BD%BF%E7%94%A87%E5%A4%A9)
    - [第 4 周｜项目实战 + 部署上线 + 优化](#%E7%AC%AC4%E5%91%A8%E9%A1%B9%E7%9B%AE%E5%AE%9E%E6%88%98%E9%83%A8%E7%BD%B2%E4%B8%8A%E7%BA%BF%E4%BC%98%E5%8C%967%E5%A4%A9)
    
- [三、三大考点知识点总结](#%E4%B8%89%E4%B8%89%E5%A4%A7%E8%80%83%E7%82%B9%E7%9F%A5%E8%AF%86%E7%82%B9%E6%80%BB%E7%BB%93)
- [四、配套免费学习资源汇总](#%E5%9B%9B%E9%85%8D%E5%A5%97%E5%85%8D%E8%B4%B9%E5%AD%A6%E4%B9%A0%E8%B5%84%E6%BA%90%E6%B1%87%E6%80%BB)
- [五、学习避坑小贴士](#%E4%BA%94%E5%AD%A6%E4%B9%A0%E9%81%BF%E5%9D%91%E5%B0%8F%E8%B4%B4%E5%A3%AB)

---

## 一、整体学习纲要

### 1. 学习目标

1. ✅ Go：环境部署 + 基础语法，满足 Hugo 运行依赖，无需深耕后端
2. ✅ HTML5：掌握特性优势、手写网页、吃透**静态网站组成结构**
3. ✅ Hugo：熟练创建站点、配置、换主题、内容管理、打包生成静态文件
4. ✅ 实战：本地调试 → 免费平台上线，拥有公开可访问个人网站

### 2. 学习准则

> **实操优先，学完必敲代码；不堆砌理论，以建站为最终导向**

---

## 二、四周精细化每日学习计划表

### 第 1 周｜Go 基础入门（7 天）

> 阶段目的：环境可用、看懂基础代码，够用即可

表格

|天数|学习内容|落地实操|备注重点|
|:-:|---|---|---|
|Day1|Go 介绍、跨平台安装、终端基础命令|安装 Go，执行`go version`，编写运行`HelloWorld.go`|配置系统环境变量|
|Day2|变量 / 常量、基础数据类型（int/string/bool/float）|自定义多类型变量并控制台打印输出|熟记两种变量声明方式|
|Day3|运算符、`if/switch`分支语法|编写分数等级判断小程序|Go 的 switch 默认无 break 穿透|
|Day4|for 循环、数组、切片|循环遍历数组、切片，做简单取值练习|切片是 Go 高频数据结构|
|Day5|函数定义、参数、多返回值|自定义 3 个简易工具函数并调用|掌握多返回值接收写法|
|Day6|结构体初识、Go 包基础概念|阅读结构体示例源码，不自主开发复杂结构|了解即可，不用深挖|
|Day7|全周复盘、错题整理|整合变量 + 循环 + 函数写一段综合代码|查漏补缺收尾本周|

go

运行

```
// Go HelloWorld示例
package main
import "fmt"
func main(){
    fmt.Println("Hello Go")
}
```

### 第 2 周｜HTML5 + 静态网站架构（7 天）

> 阶段目的：掌握 H5 优势、手写页面、理清静态网站构成

表格

|天数|学习内容|落地实操|备注重点|
|:-:|---|---|---|
|Day1|网页发展史、HTML4 与 HTML5 区别、H5 优势梳理|文档整理 HTML5 六大优势笔记|语义化、原生多媒体为核心亮点|
|Day2|HTML5 文档结构、**语义化标签 (header/nav/article/aside/footer)**|搭建空白标准 H5 页面骨架|静态页面布局的核心标签|
|Day3|H5 新增：增强表单、video/audio、canvas、本地存储|页面嵌入视频、表单控件|了解用法，不用深挖底层 API|
|Day4|CSS3 基础：选择器、字体、颜色、简单流式布局|给之前页面添加样式美化|学会基础排版即可|
|Day5|JS 极简入门：变量、点击基础交互|实现按钮点击切换文字效果|只入门，放弃 JS 高阶|
|Day6|【核心】静态网站组成：技术分层 + 目录结构 + 页面结构|手绘网站目录结构图|区分源码目录与打包后目录|
|Day7|综合实训|手写完整页面：头 + 导航 + 主体 + 侧边 + 页脚|对标真实静态网站结构|

html

预览

```
<!-- HTML5标准骨架模板 -->
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>静态网页示例</title>
</head>
<body>
    <header></header>
    <nav></nav>
    <main></main>
    <aside></aside>
    <footer></footer>
</body>
</html>
```

### 第 3 周｜Hugo SSG 全流程使用（7 天）

> 阶段目的：熟练使用 Hugo 完成博客搭建全流程

表格

|天数|学习内容|落地实操|备注重点|
|:-:|---|---|---|
|Day1|Hugo 介绍、安装、核心命令、本地预览|`hugo new site blog`创建站点，`hugo server`启动本地服务|牢记两条高频命令|
|Day2|Hugo 目录结构、`config.toml`站点配置文件|修改网站名称、描述、图标等基础配置|配置文件控制全站基础信息|
|Day3|Markdown 语法、文章创建规则、路由规则|`hugo new posts/test.md`新建 3 篇测试博文|Hugo 正文全部依赖 MD 写作|
|Day4|主题下载、安装、启用、基础主题配置|themes 目录导入免费主题并启用|优先轻量化简约主题|
|Day5|导航栏、侧边栏自定义配置|增删导航菜单、调整侧边展示模块|结合 HTML 语义理解布局|
|Day6|分类 / 标签 / 归档、站内搜索配置|给文章打标签、划分栏目，开启站内检索|完善内容分类体系|
|Day7|全站调试、死链排查、样式修复|全页面预览，修正页面错位、链接失效问题|保证本地站点无报错|

bash

运行

```
# Hugo常用终端命令
hugo new site myblog      # 创建站点
cd myblog
hugo server -D            # 本地启动预览（含草稿）
hugo                     # 打包生成public上线目录
```

### 第 4 周｜项目实战 + 部署上线 + 优化（7 天）

> 阶段目的：内容填充→上线→优化→整体复盘

表格

|天数|学习内容|落地实操|备注重点|
|:-:|---|---|---|
|Day1|网站定位规划、栏目与素材整理|确定站点用途：知识库 / 个人博客，规划栏目分类|确定长期更新方向|
|Day2|全站内容填充、风格统一美化|批量添加正式文章、配图、独立页面（关于我）|统一全站配色排版|
|Day3|多浏览器兼容性全量测试|Chrome/Edge 打开页面逐项检查显示效果|修正浏览器兼容 bug|
|Day4|静态站点部署：Gitee Pages（国内首选）|上传代码，开启 Pages，生成公网访问地址|国内 Gitee 访问速度优于 Github|
|Day5|网站优化：图片压缩、HTTPS、资源瘦身|压缩图片资源，配置全站 https|提升打开速度与安全性|
|Day6|Hugo 进阶：短代码、简易组件拓展|添加公告栏、图标组件、表情拓展|按需加装功能，不堆砌插件|
|Day7|全周期复盘、踩坑汇总、后续规划|整理全套学习笔记，记录报错与解决方案|沉淀实战经验|

---

## 三、三大考点知识点总结

### 1. Go 语言简述

**Go(Golang)**：Google 开源静态编译语言，特点：编译快、跨平台、原生高并发；

本课程定位：**工具依赖语言，仅学基础，不用学习微服务、数据库、并发进阶**，作用：Hugo 底层由 Go 开发。

### 2. Hugo（Go 开发 SSG 静态生成工具）

1. **SSG 含义**：静态站点生成器，输入 Markdown + 配置 + 主题 → 输出纯 HTML/CSS/JS 静态文件
2. **工作流**

markdown

```
Markdown文稿 → Hugo编译 → public静态资源 → 直接部署至静态服务器
```

3. 适用：个人博客、文档站、小型官网。

### 3. HTML5 优势 + 静态网站完整组成

#### 3.1 HTML5 六大优势

- 1. **语义化标签**：利于 SEO 搜索引擎抓取
    
- 2. **原生多媒体**：无需 Flash，直接 video/audio
    
- 3. **原生丰富 API**：本地存储、离线缓存、Canvas 绘图
    
- 4. **响应式友好**：配合 CSS3 适配手机 / 平板 / PC
    
- 5. **代码精简**：简化 HTML 语法，开发成本更低
    
- 6. **全端兼容**：全主流浏览器原生支持
    

#### 3.2 静态网站三层技术架构

plaintext

```
结构层：HTML5（页面骨架）
样式层：CSS3（美化布局配色）
交互层：JavaScript（页面点击交互）
辅助：Markdown、TOML配置、图片/字体资源
```

#### 3.3 Hugo 项目标准目录树

tree

```
myblog/
├── config.toml       # 全站配置文件
├── content/          # MD文章存放目录
├── themes/           # 网站主题模板
├── static/           # 图片、自定义css/js资源
│   ├── images/
│   ├── css/
│   └── js/
├── assets/           # 资源源码目录
└── public/           # 【上线目录】hugo打包后最终文件
```

#### 3.4 单页面通用结构

1. Header（头部 logo 标题）
2. Nav（导航菜单）
3. Main（主体正文）
4. Aside（侧边栏）
5. Footer（页脚版权）

---

## 四、配套免费学习资源汇总

### 📚 Go 语言资源

- 交互式官方教程：[https://tour.go-zh.org/list](https://tour.go-zh.org/list)
- 菜鸟 Go 入门：[https://www.runoob.com/go/go-tutorial.html](https://www.runoob.com/go/go-tutorial.html)
- Go 中文文档：[https://studygolang.com/doc](https://studygolang.com/doc)

### 📚 HTML5 前端资源

- MDN 权威文档（常备查阅）：[https://developer.mozilla.org/zh-CN/docs/Web/HTML](https://developer.mozilla.org/zh-CN/docs/Web/HTML)
- 菜鸟 HTML5 教程：[https://www.runoob.com/html/html5-intro.html](https://www.runoob.com/html/html5-intro.html)
- 在线运行编辑器：[https://c.runoob.com/front-end/61/](https://c.runoob.com/front-end/61/)

### 📚 Hugo 学习资源

- Hugo 中文文档：[https://hugo.zg3k.org/](https://hugo.zg3k.org/)
- 官方免费主题库：[https://themes.gohugo.io/](https://themes.gohugo.io/)

> 掘金 / 简书搜索关键词：`Hugo搭建个人博客` 实战教程

### 📚 Markdown 语法（Hugo 必备）

[https://www.runoob.com/markdown/md-tutorial.html](https://www.runoob.com/markdown/md-tutorial.html)

### 📦 免费部署平台

1. **Gitee Pages（国内优选）**：[https://gitee.com](https://gitee.com)
2. GitHub Pages：[https://github.com](https://github.com)
3. Netlify 自动部署：[https://www.netlify.com](https://www.netlify.com)

---

## 五、学习避坑小贴士

> 💡 **加粗重点规则**

1. **实操第一**：看完知识点立刻敲代码，拒绝只看视频不练习
2. **抓大放小**：Go 浅尝辄止，学习重心锁定 **HTML5 + Hugo**
3. **查文档优先**：报错优先查阅官方文档，优于零散博客教程
4. **软件版本**：安装稳定正式版，规避测试版兼容异常
5. **随手记坑**：遇到报错即时存档，后续复用节省调试时间