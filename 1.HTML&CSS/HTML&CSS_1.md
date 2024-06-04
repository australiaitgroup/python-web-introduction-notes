# Class Notes

## Table of Contents

- [Resources](#resources)
- [HTML & CSS Part 1](#html--css-part-1)
  - [HTML & CSS & JavaScript 的特点](#html--css--javascript-的特点)
  - [怎样查看一个网站源码](#怎样查看一个网站源码)
  - [HTML 详解](#html-详解)
  - [VScode 下载](#vscode-下载)
    - [VScode 插件](#vscode-插件)
    - [Live Server 使用方法](#live-server-使用方法)
    - [Live server vs 本地打开](#live-server-vs-本地打开)
  - [Terminal/ Powershell 创建文件夹](#terminal-powershell-创建文件夹)
  - [HTML 基本格式](#html-基本格式)
  - [Tag](#tag)
    - [h 标签是标题标签的一种](#h-标签是标题标签的一种)
    - [p 标签是段落标签](#p-标签是段落标签)
    - [inline vs block level elements](#inline-vs-block-level-elements)
    - [span 标签的用途](#span-标签的用途)
    - [创建 table](#创建-table)
    - [创建 listing](#创建-listing)
    - [img 标签](#img-标签)
    - [form 标签](#form-标签)
    - [a 标签](#a-标签)
    - [语义化标签](#语义化标签)
- [作业](#作业)

## HTML & CSS Part 1

### Resources

- [w3schools](https://www.w3schools.com/)
- [开发者指南](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)

### HTML & CSS & JavaScript 的特点

> HTML: 网站基本框架
> CSS: 美化网站 (color, animation, opacity, etc)
> JavaScript: 动态 (前后端交互, 功能实现)

### 解决问题实用网站

- Stack Overflow
- W3Schools
- ChatGPT

### 怎样查看一个网站源码

**_鼠标右键 + inspect/F12_**

### HTML 详解

全称是`Hyper Text Markup Language`
后缀名必须是\*.html
index.html -> `http://www.example.com`
blog.html -> `http://www.example.com/blog.html`
**_~~HTML 是编程语言~~, HTML 是标记型语言_**

> 原因: HTML 使用标签(<tag>)来描述文档的内容

### VScode 下载

[下载链接](https://code.visualstudio.com/)

#### VScode 插件

- Live Server (启动 server, 随代码更新实时更新网站)
- Prettier (排版功能)
- Auto Close Tag (自动闭合标签)
- Code Spell Checker (检查拼写)
- Color Highlight (帮助识别代码中的颜色值)
- Indent-Rainbow (缩进颜色变化)
- Image Preview (在代码旁边可以查看图片缩略图)
- VSCode Icons (更改 icons, 更加醒目)
- SonarLint (检查代码错误)

#### Live Server 使用方法

当前编辑的文件是 index.html, 点击右下角 'go live', 出现网页。
`路径问题: vscode 文件根目录决定 live server url`

1. 如果 index.html 就在根目录下 -> `http://127.0.0.1:5500/index.html`
2. 如果 index.html 在二级目录下 -> `http://127.0.0.1:5500/folder_name/index.html`

#### Live server vs 本地打开

|    Live server     |     双击打开文件      |
| :----------------: | :-------------------: |
| HTTP 协议(http://) | 本地文件协议(file://) |

> `多用 live server, 可以进行网页调试`

### Terminal/ Powershell 创建文件夹

1. cd 到自己选定的目录
2. 创建文件

|           Mac(terminal)            |                    Windows(powershell)                     |
| :--------------------------------: | :--------------------------------------------------------: |
| touch file_name, mkdir folder_name | New-Item -ItemType File -Name file_name, mkdir folder_name |


### HTML 基本格式

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <!-- content -->
  </body>
</html>
```

> content 写的越多, 关键词越多, 增加曝光机会(SEO)
> responsive web design -> 修改 viewpoint(width=device-width)

### Tag

- 大多数 tag 是要有闭合标签 (`<div></div>`)
- 少数 tag 无闭合标签 (`<br />, <img />, <input />, etc`) -> 没有 child nodes
- 有 auto close tag 插件的话一般打完前半部分就会自动补齐

#### h 标签是标题标签的一种

`<h1> -> <h6> 逐渐变小`
_h 标签是 block element_

#### p 标签是段落标签

`<p>` 标签可以包含任意文本内容，包括文本、链接、图片等。
_p 标签会根据浏览器宽度自动换行, 默认有 margin_

> **但 p 标签不能包含 block element.**

```html
<p><div></div></p>
```

_p 标签是 block element_

#### 通过 Chrome 修改网页格式

- 右键选择 check 在 style 里修改，但刷新后会恢复原样

#### 一些修改文字格式的 tag

- strong 和 b 都是加粗，一般用 strong，更加 semantic 语义化
- del 和 s 都是删除标签，一般用 del，更语义化
- em 和 i 都是倾斜文字的标签，一般用 em，更语义化
- ins 和 u 都是下划线的标签，一般用 ins，更语义化

#### inline vs block level elements

|                  Element type                  |                                       Attributes                                       |
| :--------------------------------------------: | :------------------------------------------------------------------------------------: |
| **inline element** (`<span>,<a>,<button>,etc`) | 不独占一行, 它们的大小由元素的内容决定, 设置宽高无效, 可以设置左右的 padding 和 margin |
|  **block element** (`<p>,<div>,<button>,etc`)  |               而块级元素会独占一行，并且会在前后添加换行符, 可以设置宽高               |

#### span 标签的用途

> 修改部分文字样式

```html
<p>
  He
  <span style="color:green;font-weight:bold;font-style:italic">went to</span>
  school
</p>
```

- 这里用给 p 标签一个 class selector 不容易修改部分文字的 style, span 作为行内元素很灵活, 不会独占一行。

> **但不要多用优先级高的 inline style, 多用可以复用的 class selector**

#### 创建 table

```html
<table>
  <caption>
    Demo table
  </caption>
  <thead>
    <tr>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Points</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Doe</td>
      <td>100</td>
    </tr>
    <tr>
      <td>Jane</td>
      <td>Doe</td>
      <td>200</td>
    </tr>
  </tbody>
</table>
```

#### 创建 listing

有序列表 (ol)

- 建议 ol 里面放 li
- li 里面还能放置别的标签
- ol 里的 li 前面会有序号

```html
<ol>
  <li>HTML</li>
  <li>CSS</li>
  <li>Javascript</li>
</ol>
```

无序列表 (ul)

- ul 里面只能放 li，这是一个规范（避免不同浏览器显示不同）
- li 里面还能放置别的标签
- li 为 block 性质，独占一行

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>Javascript</li>
</ul>
```

#### img 标签

```html
<img src="" alt="" />
```

**alt 在图片无法加载时显示**

#### form 标签

Form 标签 (label 和 input 一般成对出现, label 中的 for 和 input 中的 id 相对应)

- 所有的 input 只能放在 form 里面才能提交
- crtl+/ 创建一个<!-- -->注释

Input 标签

- input 是单标签
- 单选

的 type 为 radio，且必须有相同的 name 才能实现单选

Label 标签

- 当点击 label 标签，浏览器就会自动聚焦到对应的 input 上，来增加用户体验
- for 和 id 要匹配

```html
<form action="results.html" method="GET" enctype="multipart/form-data">
  <div>
    <label for="name">Name</label>
    <input type="text" name="name" id="name" placeholder="username" required />
  </div>
  <div>
    <label for="password">Password</label>
    <input
      type="password"
      name="password"
      id="password"
      placeholder="password"
      required
    />
  </div>
  <div>
    <label for="email">Email</label>
    <input type="email" name="email" id="email" placeholder="email" required />
  </div>
  <div>
    <label for="comment">Comment</label>
    <textarea name="comment" id="comment" placeholder="Write sth"></textarea>
  </div>
  <div>
    <label for="mobile">Phone</label>
    <input type="tel" id="mobile" name="mobile" placeholder="123-456" />
  </div>
  <div>
    <label for="color">Color</label>
    <input type="color" name="color" id="color" />
  </div>
  <div>
    <label for="range">Range:</label>
    <input type="range" id="range" name="range" />
  </div>
  <div>
    <label for="checkbox">remember me:</label>
    <input type="checkbox" id="checkbox" name="checkbox" />
  </div>
</form>
```

#### select 标签

- selected 默认选中状态

```html
<label for="Country">Country</label>
<select name="" id="Country">
  <option value="Australia">Australia</option>
  <option value="China">China</option>
  <option value="USA" selected>USA</option>
</select>
```

#### a 标签

```html
<a href="https://google.com/">Google</a> <a href="mailto: xxx@123.com">email</a>
<!-- 给xxx@123.com发邮件 -->
<a href="tel:123-456-789">call</a><br />
```

#### 语义化标签

可以代替 div, 有助于搜索引擎优化

`<header>, <nav>, <main>, <footer>, <article>, <section>, <aside>, <figure>, etc`

### 作业

- 在 freecodecamp 上练习
- 尝试写个人 blog

[FreeCodeCamp - Responsive Web Design](https://www.freecodecamp.org/learn/2022/responsive-web-design/)
[Dribbble - Blog Search](https://dribbble.com/search/search-blog)
