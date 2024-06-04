# Class Notes

## Table of Contents

- [HTML Tutorial](#html-tutorial)
  - [练习网站](#练习网站)
  - [HTML Tags, Elements, and Attributes 的语法规范](#html-tags-elements-attributes-的语法规范)
  - [文档结构](#文档结构)
  - [一些小 Tips](#一些小-tips)
  - [a 标签 - 超链接](#a-标签---超链接)
  - [section 标签](#section-标签)
  - [相对路径 - 绝对路径](#相对路径---绝对路径)
  - [文本标签](#文本标签)
  - [链接和图像](#链接和图像)
  - [表格和列表](#表格和列表)
  - [表单](#表单)
  - [其他常用标签](#其他常用标签)
  - [拓展](#拓展)
    - [块级元素和行内元素](#块级元素和行内元素)
      - [块级元素](#块级元素)
      - [行内元素](#行内元素)
      - [DOM 中 HTMDivElement 继承关系](#dom-中-htmdivelement-继承关系)
  - [练习](#练习)

## HTML Tutorial

### 练习网站

[Practice Board](https://www.practiceboard.com/)

### HTML Tags, Elements, and Attributes 的语法规范

```html
elements:
<body>
  <p></p>
  <h1>
    -
    <h6>
      <br />
      <span></span>
    </h6>
  </h1>
</body>
```

### 文档结构

```html
<!DOCTYPE html>
<!-- 声明 -->
<html lang="en">
  <!-- 包含 HTML content -->
  <head>
    <!-- head 中不包含网页肉眼可见信息，但包含标题及 tag 的文字部分，meta（SEO 或者一些其他数据），icon 等元素 -->
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body></body>
</html>
```

- 开始，声明

```html
<!DOCTYPE html>
```

- 包含 HTML content tag

```html
<html></html>
```

- Invisible parts

```html
<head>
  <meta>
  <link>
  <title>
  <style>
  <script>
```

- Visible parts

```html
<body>
  <section>
    <nav>
      <div>
        <ul></ul>
      </div>
    </nav>
  </section>
</body>
```

### 一些小 Tips

- VSCode 创建新的 HTML 文件一般取名 index.html，即入口文件
- 修改 tags 和 icon 的方法：

```html
<head>
  <link
    rel="icon"
    type="image"
    href="https://jubic.notion.site/images/favicon.ico"
  />
</head>
```

- 导航栏 `nav`
  `没有具体的意思，主要告诉你这是一个导航栏`

### a 标签 - 超链接

```html
<a href="#"></a> <a href="/home"></a>
```

- `#` 表示当前页面
- `href` 表示需要跳到的链接，可实现 app 内跳转

### section 标签

- 一般用 `div` (更 general)，但可以根据语义化环境灵活使用
- 范围：`section` > `div`

### 相对路径 - 绝对路径

- 相对路径：可以引用本地的文件位置，用 `/`
- 绝对路径：直接引用网络上的图片或链接地址即可

### 文本标签

- 代表文本的 element tag

```html
<h1>
  -
  <h6>
    <p>
      <br />
      <strong>
        <i>
          <mark> <del></del></mark></i
      ></strong>
    </p>
  </h6>
</h1>
```

### 链接和图像

```html
<a href="path" target="_blank">link</a>
<img width="100" height="50" alt="cat" src="/favicon.ico" />
```

### 表格和列表

```html
<table>
  <tr>
    <th>HEAD1</th>
    <th>HEAD2</th>
    <th>HEAD3</th>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</table>
```

```html
<ul>
  <li>egg</li>
  <li>potato</li>
</ul>

<ol>
  <li>egg</li>
  <li>potato</li>
</ol>

<dl>
  <dt>coffee</dt>
  <dd>black hot drink</dd>
  <dt>tea</dt>
  <dd>refreshing hot drink</dd>
</dl>
```

### 表单

```html
<form>
  <label for="input">Label</label>
  <input id="input" type="text" />
  <textarea></textarea>
  <button type="submit">Submit</button>
  <!-- 默认的 feature 是如果放置内容在 form 里会提交所有相关内容 -->
</form>
```

### 其他常用标签

- `<span>`
- 固定:
  ```html
  <nav>
    <footer></footer>
  </nav>
  ```
- 添加视频、音频，内嵌，和页面本身完全不交互，不能修改样式
  ```html
  <iframe></iframe>
  ```
- 统称 media 标签，一般里面套 source，可修改样式
  ```html
  <audio>
    <video></video>
  </audio>
  ```
- 分隔标签
  ```html
  <hr />
  ```

### 拓展

#### 块级元素和行内元素

##### 块级元素

**h1-h6, div, section, nav, ol, ul, form**

- 总是从新的一行开始
- 块级元素可以包含块级元素和行内元素
- 高度和宽度是可控的
- 宽度没有设置时，默认是 100%

##### 行内元素

**span, strong, img（inline-block）, input, textarea, select**

- 和其他元素在一行，不会换行
- 高度和宽度都是不可控的，高度和宽度就是内容宽高
- `inline-block` 可以设置高度和宽度
- 行内元素可以包含行内元素，但不可以包含块级元素

##### DOM 中 HTMDivElement 继承关系

- HTMDivElement -> HTMElement -> Node -> EventTarget
- HTMDivElement 继承自 HTMElement，所有 HTMDivElement 是 HTMElement 的子类，HTMDivElement 有 HTMElement 所有的 feature

```html
人：EventTarget 女人、男人：Node 女生：Element
```

- HTMDivElement : div
- EventTarget : eventListener[EventTarget]

### 练习

- [Khan Academy HTML & CSS Quiz](https://www.khanacademy.org/computing/computer-programming/html-css/html-css-further-learning/e/quiz--validate-this-html)
- [W3resource HTML CSS Exercise](https://www.w3resource.com/html-css-exercise/basic/)
