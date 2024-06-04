# Class Notes

## Table of Contents

- [Class Notes](#class-notes)
  - [Resources](#resources)
  - [Node_2](#node_2)
    - [fs 模块: 读取 + 写入文件](#fs-模块-读取--写入文件)
      - [fs 读取文件](#fs-读取文件)
      - [fs 写入文件](#fs-写入文件)
        - [score 读取写入练习](#score-读取写入练习)
    - [http 模块: 创建 web 服务器](#http-模块-创建-web-服务器)
      - [IP 地址: 每台 pc 的唯一地址](#ip-地址-每台-pc-的唯一地址)
      - [域名和域名服务器](#域名和域名服务器)
      - [端口号](#端口号)
      - [搭建 server 步骤](#搭建-server-步骤)
      - [安装 postman](#安装-postman)
        - [http 模块练习](#http-模块练习)
    - [npm 包管理和使用](#npm-包管理和使用)
      - [格式化输出 date - 常用写法](#格式化输出-date---常用写法)
      - [格式化输出 date - 使用 moment 库](#格式化输出-date---使用-moment-库)

## Resources

[Postman 官网](https://www.postman.com/)<br>
[moment 库](https://momentjs.com/docs/)<br>

## Node_2

### fs 模块: 读取 + 写入文件

_fs 模块是 Node.js 官方提供的, 用来操作文件的模块_<br>
_写入/读取成功 err 是 null, 不成功是 obj_<br>

```js
// 使用fs方法前, 先要导入fs
const fs = require("fs");
```

#### fs 读取文件

`fs.readFile(path options callback)` _读取_<br>

1. path: 路径
2. options: 编码格式(可选)
3. callback: 回调函数

```js
const fs = require("fs");
//参数1：path，参数2：编码格式， 参数3：callback 拿到读取失败和成功的结果
fs.readFile("./files/1.txt", "utf8", function (err, data) {
  if (err) {
    return console.log("err", err);
  }
  console.log("data", data);
});
```

#### fs 写入文件

`fs.writeFile(path options callback)` _写入_<br>

```js
const fs = require("fs");
//1.必选参数，指定一个文件路径的字符串
//2.必选参数，表示要写入的内容
//3.可选参数，表示什么格式，默认是utf8
//4.必选参数，文件写入完成后回调函数
fs.writeFile("./files/3.txt", "I love coding", function (err, data) {
  if (err) {
    return console.log("err", err);
  }
  console.log("write file successfully");
});
```

##### score 读取写入练习

```js
// Ben:99
// Jane:100
// John:80
// Chris:66
// Andrew:88
//1. read score.txt
//2. split to array
//3. replace = with :
//4. convert array to string
//5. write the updated score to updatedScore.txt
//提示：做一步测一步最好
const fs = require("fs");
fs.readFile("./score.txt", "utf8", function (err, data) {
  if (err) {
    return console.log("read failed", err.message);
  }
  console.log("read file successfully", data, typeof data);
  //read file succeed Ben=99 Jane=100 John=80 Chris=66 Andrew=88 string
  //2. split to array
  const arr = data.split(" ");
  console.log("arr", arr);
  //3. replace = with :
  let newArr = [];
  arr.forEach(function (item) {
    newArr.push(item.replace("=", ":"));
  });
  console.log("newArr", newArr);
  //4. convert array to string
  const newArr2 = newArr.join("\r\n");
  console.log("newArr2", newArr2, typeof newArr2);
  //5. write the updated score to updatedScore.txt
  fs.writeFile("./updatedScore.txt", newArr2, function (err, data) {
    if (err) {
      return console.log("write failed", err.message);
    }
    console.log("write file successfully");
  });
});
```

### http 模块: 创建 web 服务器

#### 什么是 http 模块

- 客户端：网络节点中负责消费的电脑叫客户端；负责对外提供网络资源的叫服务器
- http 模块是 Node.js 官方提供的，用来创建 web 服务器的模块

#### http 模块的作用

- 服务器和普通电脑不同，安装了 web 服务器软件，例如 IIS、Apache 等
- 在 Node.js 中不需要三方 web 服务器软件，可以直接运用自带的 http 模块提供 web 服务

#### IP 地址: 每台 pc 的唯一地址

`192.168.1.1` 0~255

使用`ping www.baidu.com` -> 得到 ip

#### 域名和域名服务器

DNS: ip 和 domain 是一一对应的

> DNS 自动域名解析成 ip<br>
>
> > localhost - 127.0.0.1<br>

#### 端口号

一个 port 只能 run 一个 web server

> url 的 80 端口可以被忽略
> mac 上面不要使用 5000 端口

#### 搭建 server 步骤

1. 导入 http 模块
2. 创建 web server instance
3. 绑定 request
4. 启动 server

#### 安装 postman

`browser只能做get request测试, post request要用postman测试`<br>
[Postman 官网](https://www.postman.com/)<br>

```js
const http = require("http");
const server = http.createServer();
server.on("request", function (req, res) {
  console.log("someone is visiting the server");
  const url = req.url;
  const method = req.method;
  const str = url + " and request method is " + method;
  console.log("str", str);
  res.setHeader("Content-Type", "text/html;charset=utf-8"); // 避免乱码
  res.end(str);
});

server.listen(8080, function (req, res) {
  console.log("the server is running on http://localhost:8080");
});
```

##### http 模块练习

```js
server.on("request", (req, res) => {
  const url = req.url;
  let content = "<h1>404 not found</h1>";
  if (url === "/" || url === "/home") {
    content = "<h1>welcome to home page</h1>";
  } else if (url === "/about") {
    content = "<h1>welcome to about page</h1>";
  }
  res.setHeader("Content-Type", "text/html;charset=utf-8");
  res.end(content);
});
```

### npm 包管理和使用

包是用原生方法写的, 安装包后能节省很多代码

#### 包

- 什么是包
  - Node.js 中的第三方模块又叫做包
- 包的来源
  - 包由第三方个人或者团队开发出来的，Node,js 中免费且开源
- 为什么需要包
  - Node.js 仅提供一些底层 API，效率低
  - 包时基于内置模块封装出来提供更高级的 API，提高开发效率
  - 包和内置模块之间的关系，类似与 jQuery 和浏览器内置 API 之间关系
- 下载地址
  - http://www.npmjs.com/网站上搜索自己所需要的包
  - http://registry.npmjs.org/服务器上下载自己需要的包
- 如何下载
  - Node Package Manager

```shell
npm -v # 查看npm版本号
```

#### 格式化输出 date - 常用写法

```js
function addZero(value) {
  return value < 10 ? "0" + value : value;
}

function convertDate(date) {
  const year = date.getFullYear();
  const month = addZero(date.getMonth() + 1);
  const day = addZero(date.getDate());
  const hour = addZero(date.getHours());
  const minute = addZero(date.getMinutes());
  const second = addZero(date.getSeconds());
  console.log(`${year}-${month}-${day} ${hour}:${minute}:${second}`);
}

convertDate(new Date());
```

#### 格式化输出 date - 使用 moment 库

[moment 库](https://momentjs.com/docs/)

```shell
# 第一种写法
npm install moment
# 第二种写法
npm i moment
```

```js
const moment = require("moment"); // 导入moment
console.log(moment().format("YYYY-MM-DD hh:mm:ss"));
```
