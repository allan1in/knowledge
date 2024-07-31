- [1 JavaScript 介绍](#1-javascript-介绍)
  - [历史](#历史)
  - [JavaScript 实现](#javascript-实现)
    - [ECMAScript](#ecmascript)
      - [重要版本](#重要版本)
    - [DOM](#dom)
    - [BOM](#bom)
  - [HTML 中的 JavaScript](#html-中的-javascript)
    - [\<script\> 元素](#script-元素)
      - [内部脚本](#内部脚本)
      - [外部脚本](#外部脚本)
    - [标签位置](#标签位置)
    - [推迟执行脚本](#推迟执行脚本)
    - [异步执行脚本](#异步执行脚本)
    - [动态加载脚本](#动态加载脚本)
    - [\<noscript\> 元素](#noscript-元素)
- [2 JavaScript 基础语法](#2-javascript-基础语法)
  - [语法](#语法)
    - [区分大小写](#区分大小写)
    - [标识符](#标识符)
    - [严格模式](#严格模式)
    - [语句](#语句)
  - [关键字与保留字](#关键字与保留字)
  - [变量](#变量)
    - [var](#var)
    - [let](#let)
    - [const](#const)
    - [最佳实践](#最佳实践)
  - [数据类型](#数据类型)

# 1 JavaScript 介绍

## 历史

- 1995年，网景公司 Brendan Eich 开放了脚本语言 Mocha（后改名 LiveScript）
- 网景公司与 Sun 公司合作开发 LiveScript，并改名 JavaScript
- 微软发布 JScript，两个版本的并存产生冲突
- 1997年，JavaScript 被提交给 ECMA，ECMA（欧洲计算机制造商协会）打造出新的语言标准 ECMA-262，即 ECMAScript
- 此后，各家浏览器均以 ECMAScript 为标准作为 JavaScript 的实现依据

## JavaScript 实现

JavaScript 实现远远不限于 ECMAScript 的规定，完整实现包括：

- 核心（ECMAScript）
- 文档对象模型（DOM）
- 浏览器对象模型（BOM）

### ECMAScript

JavaScript 的语言标准

#### 重要版本

- ES3，支持了所有基础语法，ECMAScript 真正成为了一种编程语言
- ES6，新增Promise、类、迭代器、模块、箭头函数以及新数据类型等内容（之后一年更新一个版本）

### DOM

文档对象模型，根据 HTML 创建节点，提供了 DOM API 可以方便地修改节点，开发者可以不用刷新页面而修改页面的外观和内容

历史：

- 微软与网景采用不同的思路开发 DHTML（动态HTML）
- 万维网联盟（W3C, World Wide Web Consortium）开始制定 DOM 标准
- DOM 版本，从 DOM LEVEL 1 到 DOM LEVEL 3 ，直到最新版本 DOM4，这是一个动态标准，这意味着以后会一直在此版本上更新

浏览器中的 DOM 是由 ECMAScript 实现的，因此 JavaScript 中提供了许多方法来访问和操作 DOM

### BOM

浏览器对象模型，提供接口，开发者可以操纵浏览器显示页面之外的部分

由于在很长的一段时间内，没有 BOM 标准，因此每家浏览器都有自己的 BOM 属性和方法，不过，直到 HTML5 的出现，BOM 的实现细节会逐渐一致

## HTML 中的 JavaScript

### \<script> 元素

#### 内部脚本

```
<script>
  console.log('hello');
</script>
```

#### 外部脚本

推荐这种引入方式，原因如下：

- 可维护性
- 缓存，浏览器会缓存 js 文件，多个 html 使用同一个 js 文件时不会重复下载
- 兼容，XHTML 对内部脚本的编写有更严格的规则，而外部脚本不用考虑这个问题

```
<script src="main.js"></script>
```

### 标签位置

放在 \<head> 中，下载所有 js 文件后载执行 html，可能会很慢

防止 \<body> 后，加快页面加载速度

### 推迟执行脚本

defer 只对外部脚本有效，会在加载完 html 后再按顺序执行 js

```
<script defer src="main.js"></script>
```

### 异步执行脚本

只适用于外部脚本，不同的 js 文件不会按顺序执行

```
<script async src="main.js"></script>
```

### 动态加载脚本

js 中可以使用 DOM 添加 \<script> 标签，这种方式添加的 js 默认异步加载，但不建议使用


### \<noscript> 元素

有以下任何一种情况时，\<noscript> 中的内容会被渲染

- 浏览器不支持脚本
- 浏览器被禁用脚本

最初，此标签是用于兼容不支持 JavaScript 的浏览器，但现在对于禁用脚本的浏览器也很有用

# 2 JavaScript 基础语法

## 语法

### 区分大小写

变量名、关键字等一切都区分大小写

### 标识符

标识符，是函数、变量、属性、参数的名称，必须满足以下规则：

- 第一个字符必须是下划线（_）、字母或 $ 
- 剩下的字符可以是数字、下划线（_）、字母或 $ 

最佳实践：

```
myNewName
```

推荐驼峰命名法，因为内置函数和对象的命名也是如此

### 严格模式

ES5 增加了严格模式，开启严格模式，需要在开头加一行：

```
"use strict";
```

这是一个预处理指令，任何支持JS的引擎都会切换到严格模式，严格模式会有更多的保留字

### 语句

最佳实践：

```
// 不省略大括号
if (test) {
  //语句末尾加分号
  console.log(test);
}
```

## 关键字与保留字

关键字，有特殊用途，比如 if、else、break

保留字，给未来保留，这些保留字可能在将来成为关键字

## 变量

JS 变量是弱类型（松散类型）的，变量可以保存任何数据类型，有以下三种变量

### var

最佳实践：

```
// 不省略 var，哪怕省略也是可以的
var message = "hi";

// 定义多个变量，用逗号分隔
var message = "hi",
    age = 29;
```

声明作用域：函数作用域

- 在函数内声明是局部变量，函数调用结束后被销毁
- 如果使用 `message = "hi";` 的定义方式，会声明一个全局变量，可以被外部访问

声明提升：

如下定义一个变量：

```
function foo() {
  console.log(age);
  var age = 29;
}
```

这样不会报错，结果是 undefined，因为会被等价为以下代码：

```
function foo() {
  var age;
  console.log(age);
  age = 29;
}
```

这就是变量提升（hoist），并且这样也没有问题：

```
function foo() {
  var age = 16;
  var age = 32;
  var age = 76;
  console.log(age);
}
```

输出 76

### let

ES6 新增

let 与 var 的区别：

- let 作用域较小
- 没有变量提升
- let 在全局作用域声明的变量不会成为 window 对象的属性（var 全局变量会）

声明作用域：块作用域，例如，以下代码输出结果会报错： ReferenceError: age not defined

```
function test() {
  if (true) {
    let age = 26;
  }
  console.log(age);
}
```

没有变量提升：导致暂时性死区（temporal dead zone）

由于不会自动提升变量，let 声明之前，执行瞬间叫暂时性死区，此阶段任何对未声明变量引用都会有报错：ReferenceError

### const

const 与 let 区别：

- 声明时必须初始化
- 修改变量时会报错（如果变量引用的是一个对象，那么修改对象内的属性是可以的）

### 最佳实践

- 不使用 var
- const 优先，let 次之（只有提前知道需要修改时才使用 let）

## 数据类型

