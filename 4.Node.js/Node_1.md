# Class Notes

## Table of Contents

- [Class Notes](#class-notes)
  - [Resources](#resources)
  - [Node_1](#node_1)
    - [什么是 Node](#什么是-node)
    - [浏览器解析引擎](#浏览器解析引擎)
    - [后端开发语言](#后端开发语言)
      - [node 能做什么](#node-能做什么)
    - [安装 node.js](#安装-nodejs)
      - [npm 安装第三方库](#npm-安装第三方库)
    - [常见控制台代码](#常见控制台代码)
    - [命令行指令](#命令行指令)
    - [JS 数据类型](#js-数据类型)
      - [8 种数据类型](#8-种数据类型)
    - [模块化](#模块化)
      - [模块化的分类](#模块化的分类)
      - [导出导入模块](#导出导入模块)

## Resources

[Node 官网](https://nodejs.org/en)<br>
[50JS](https://github.com/bradtraversy/50projects50days)<br>

## Node_1

### 什么是 Node.js

> Node.js is a JS runtime built on Chrome's V8 JS machine.

|                DOM                |                                     BOM                                     |
| :-------------------------------: | :-------------------------------------------------------------------------: |
| **_访问和操作 html 和 xml 文档_** | **_操作浏览器窗口。它包括了 window 对象、navigator 对象、location 对象等_** |

`window.location.href`: 拿到 url

### Node.js 中的 JavaScript 运行环境

- JS 前端的运行环境是浏览器\*
- JS 后端的运行环境是 Node.js\*
  > Node.js 中无法调用 DOM 和 BOM 等浏览器内置方法

#### Node.js 能做什么

`提供基础框架，更多第三方框架都基于node`

|  框架名  |         介绍          |
| :------: | :-------------------: |
| Express  |       Web 应用        |
| Electron |   跨平台的桌面应用    |
| Restify  | 快速搭建 API 接口项目 |

### 浏览器解析引擎

<p align='center'><img src='../image/Why can JS run in the browser.png' width='50%' /></p>

<p align='center'><img src='../image/JS operates DOM.png' width='50%' height='50%' /></p>

_JS 前端的运行环境是浏览器_
_JS 后端的运行环境是 Node.js_

> Node.js 中无法调用 DOM 和 BOM 等浏览器内置方法

### 后端开发语言

Java/Python/PHP/Node.js

#### node 能做什么

`很多第三方框架可以节省代码`

|  框架名  |         介绍          |
| :------: | :-------------------: |
| Express  |       Web 应用        |
| Electron |   跨平台的桌面应用    |
| Restify  | 快速搭建 API 接口项目 |

`JS基础语法 + node.js内置api + 第三方api`

#### Node.js 怎么学

- 浏览器中的 JavaScript 学习路径：
  <br/>`JavaScript基础语法 + 浏览器内置API(DOM + BOM) + 第三方库(jQuery、 art-template等)`
- Node.js 的学习路径：
  <br/>`JavaScript基础语法 + Node.js内置API模块（fs、path、http等）+第三方API模块(express、mysql等)`

### 安装 node.js

<https://nodejs.org/en>

- node -v
- 使用.exit 退出

#### npm 安装第三方库

```shell
npm i package_name
```

### 常见控制台代码

_使用 node file_name 运行_

```js
console.log("hello world");
```

### 命令行指令

- Mac

```plaintext
cd -> 进入指定文件夹路径
pwd -> 显示当前路径
ls -> 显示当前目录下的内容
mkdir -> 创建文件夹
touch -> 创建文件
mvdir -> 移动文件夹/重命名
rm -> 删除文件
rmdir/rd -> 删除空文件夹
clear -> 清除屏幕内容
date -> 显示系统当前日期
ping -> 查询ip地址
ctrl+c -> 终止命令
exit -> 退出terminal
```

- Windows

```plaintext
echo "123" > new.txt 创建非空文件
type nul > newtest.txt 创建空文件
del file.txt 删除文件
rd file 删除空文件夹
```

### JS 数据类型

#### 8 种数据类型

undefined, null, string, number, boolean, symbol(唯一表示符), bigInt(大整数), object(Function, Array, Date, RegExp, etc)

```js
console.log(999999999n); //bigInt
console.log(BigInt(999999999)); //bigInt
```

```js
let s = Symbol();
```

### 模块化

- 复用性
- 可维护性
- 按需加载

#### 模块化的分类

- 内置模块（由 Node.js 官方提供：fs\path\http）
- 自定义模块（用户创建的 js 文件）
- 第三方模块 (先安装, 再导入)

#### 加载模块

- require（）方法

#### 导出导入模块

- 使用 module.export

```js
let text = "demo";
module.exports = text;

const text = require("./text1");
console.log("text", text);
```

- 使用 global

```js
let arr=[1,2,3];
global my_Arr = arr;

require('./text1');
console.log('my_Arr', my_Arr);
```

`导出多个变量`

```js
let arr = [1, 2, 3];
let helloString = "hello world";
module.exports = { arr, helloString };

const { arr, helloString } = require("./test6");
console.log("arr", arr);
console.log("helloString", helloString);
```
