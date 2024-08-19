- [0 资源链接](#0-资源链接)
- [1 JavaScript 介绍](#1-javascript-介绍)
  - [历史](#历史)
  - [JavaScript 实现](#javascript-实现)
    - [ECMAScript](#ecmascript)
      - [重要版本](#重要版本)
    - [DOM](#dom)
    - [BOM](#bom)
  - [HTML 中的 JavaScript](#html-中的-javascript)
    - [引入方式](#引入方式)
      - [内联方式](#内联方式)
      - [外部引入](#外部引入)
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
    - [typeof 操作符](#typeof-操作符)
    - [undefined](#undefined)
    - [null](#null)
    - [boolean](#boolean)
    - [number](#number)
      - [进制数](#进制数)
      - [浮点值](#浮点值)
      - [科学计数法](#科学计数法)
      - [精度问题](#精度问题)
      - [无限值](#无限值)
      - [NaN](#nan)
      - [数值转换](#数值转换)
    - [string](#string)
      - [字符串字面量](#字符串字面量)
      - [不可变](#不可变)
      - [字符串转换](#字符串转换)
      - [字符串模板](#字符串模板)
        - [字面量](#字面量)
        - [插值](#插值)
        - [标签函数](#标签函数)
      - [模板-原始字符串](#模板-原始字符串)
    - [symbol（TODO）](#symboltodo)
    - [Object](#object)
      - [属性和方法](#属性和方法)
  - [操作符](#操作符)
    - [一元操作符](#一元操作符)
      - [递增与递减](#递增与递减)
      - [一元加减](#一元加减)
    - [位操作符](#位操作符)
      - [按位非](#按位非)
      - [按位与](#按位与)
      - [按位或](#按位或)
      - [按位异或](#按位异或)
      - [左移](#左移)
      - [右移](#右移)
    - [布尔操作符](#布尔操作符)
      - [逻辑非](#逻辑非)
      - [逻辑与](#逻辑与)
      - [逻辑或](#逻辑或)
    - [乘性操作符](#乘性操作符)
      - [乘法](#乘法)
      - [除法](#除法)
      - [取模](#取模)
    - [指数操作符](#指数操作符)
    - [加性操作符](#加性操作符)
      - [加法操作符](#加法操作符)
      - [减法操作符](#减法操作符)
    - [关系操作符](#关系操作符)
    - [相等操作符](#相等操作符)
      - [等于和不等于](#等于和不等于)
      - [全等和不全等](#全等和不全等)
    - [条件操作符（三元运算）](#条件操作符三元运算)
    - [赋值运算符](#赋值运算符)
    - [逗号操作符](#逗号操作符)
  - [语句](#语句-1)
    - [if](#if)
    - [do-while](#do-while)
    - [while](#while)
    - [for](#for)
    - [for-in](#for-in)
    - [for-of](#for-of)
    - [标签、break和continue](#标签break和continue)
    - [with](#with)
    - [switch](#switch)
  - [函数](#函数)
- [3 变量、作用域与内存](#3-变量作用域与内存)
  - [原始值与引用值](#原始值与引用值)
    - [动态属性](#动态属性)
    - [复制值](#复制值)
      - [原始值的复制](#原始值的复制)
      - [引用值的复制](#引用值的复制)
    - [传递参数](#传递参数)
    - [instanceof](#instanceof)
  - [执行上下文与作用域](#执行上下文与作用域)
    - [作用域链增强](#作用域链增强)
      - [with 语句](#with-语句)
      - [try/catch 中的 catch 块](#trycatch-中的-catch-块)
    - [变量声明](#变量声明)
      - [函数作用域声明（var）](#函数作用域声明var)
      - [块级作用域声明（let）](#块级作用域声明let)
      - [常量声明（const）](#常量声明const)
      - [标识符查找](#标识符查找)
  - [垃圾回收](#垃圾回收)
    - [标记清理](#标记清理)
    - [引用计数](#引用计数)
      - [问题：循环引用](#问题循环引用)
    - [性能](#性能)
    - [内存管理（TODO）](#内存管理todo)
      - [通过 const 和 let 声明提升性能](#通过-const-和-let-声明提升性能)
      - [隐藏类和删除操作](#隐藏类和删除操作)
- [4 基本引用类型](#4-基本引用类型)
  - [Date](#date)
    - [构造函数](#构造函数)
      - [Date.parse()](#dateparse)
      - [Date.UTC()](#dateutc)
      - [Date.now()](#datenow)
    - [继承的方法](#继承的方法)
    - [日期格式化](#日期格式化)
    - [get/set 方法](#getset-方法)
  - [RegExp (TODO)](#regexp-todo)
  - [原始值包装类](#原始值包装类)
    - [包装类的创建](#包装类的创建)
      - [自动创建](#自动创建)
      - [Object() 创建包装类](#object-创建包装类)
      - [Number() 与 new Number()](#number-与-new-number)
    - [Boolean](#boolean-1)
    - [Number](#number-1)
    - [String（TODO）](#stringtodo)
      - [JavaScript 字符（TODO）](#javascript-字符todo)
      - [normalize()（TODO）](#normalizetodo)
      - [字符串操作方法](#字符串操作方法)
      - [字符串位置方法](#字符串位置方法)
      - [字符串包含方法](#字符串包含方法)
      - [字符串去除空格](#字符串去除空格)
      - [字符串填充方法](#字符串填充方法)
      - [字符串迭代与解构（TODO）](#字符串迭代与解构todo)
      - [字符串大小写转换](#字符串大小写转换)
      - [字符串模式匹配方法（TODO）](#字符串模式匹配方法todo)
      - [比较字母顺序](#比较字母顺序)
      - [HTML 方法](#html-方法)
  - [单例内置对象](#单例内置对象)
    - [Global](#global)
      - [URL 编码方法](#url-编码方法)
      - [eval()](#eval)
      - [属性](#属性)
      - [window 对象](#window-对象)
    - [Math](#math)
      - [属性](#属性-1)
      - [最大值最小值](#最大值最小值)
      - [舍入方法](#舍入方法)
      - [随机数](#随机数)
      - [其他方法](#其他方法)
- [5 集合引用类型](#5-集合引用类型)
  - [Object](#object-1)
  - [Array](#array)
    - [创建数组](#创建数组)
      - [构造函数方式](#构造函数方式)
      - [数组字面量方式](#数组字面量方式)
      - [from()](#from)
      - [of()（TODO）](#oftodo)
    - [数组空位](#数组空位)
    - [数组索引](#数组索引)
    - [检测数组](#检测数组)
      - [isArray()](#isarray)
    - [迭代器方法（TODO）](#迭代器方法todo)
    - [复制和填充方法](#复制和填充方法)
      - [fill()](#fill)
      - [copyWithin()](#copywithin)
    - [转换方法](#转换方法)
      - [toString() 和 valueOf()](#tostring-和-valueof)
      - [toLocaleString()](#tolocalestring)
      - [join()](#join)
      - [数组空位的特殊情况](#数组空位的特殊情况)
    - [栈方法](#栈方法)
      - [push()](#push)
      - [pop()](#pop)
    - [队列方法](#队列方法)
      - [shift()](#shift)
      - [unshift()](#unshift)
    - [排序方法](#排序方法)
      - [reverse()](#reverse)
      - [sort()](#sort)
    - [操作方法](#操作方法)
      - [concat()](#concat)
      - [slice()](#slice)
      - [splice()](#splice)
    - [搜索和位置方法](#搜索和位置方法)
      - [严格相等](#严格相等)
        - [indexOf()](#indexof)
        - [lastIndexOf()](#lastindexof)
        - [includes()](#includes)
      - [断言函数](#断言函数)
        - [find()](#find)
        - [findIndex()](#findindex)
    - [迭代方法](#迭代方法)
      - [every()](#every)
      - [some()](#some)
      - [filter()](#filter)
      - [forEach()](#foreach)
      - [map()](#map)
    - [归并方法](#归并方法)
      - [reduce()](#reduce)
      - [reduceRight()](#reduceright)
  - [定型数组（TODO）](#定型数组todo)
  - [Map（ES6）](#mapes6)
    - [创建](#创建)
    - [增删改查](#增删改查)
      - [set()](#set)
      - [has()](#has)
      - [get()](#get)
      - [delete()](#delete)
      - [clear()](#clear)
      - [size](#size)
    - [关于 key 的匹配性](#关于-key-的匹配性)
    - [顺序与迭代](#顺序与迭代)
      - [entries()](#entries)
      - [\[Symbol.iterator\]](#symboliterator)
      - [keys()](#keys)
      - [values()](#values)
      - [forEach()](#foreach-1)
    - [Object VS. Map](#object-vs-map)
  - [WeakMap（TODO）](#weakmaptodo)
    - [与 Map 的区别](#与-map-的区别)
    - [弱键（TODO）](#弱键todo)
  - [Set](#set-1)
    - [与 Map 的区别](#与-map-的区别-1)
    - [定义正式集合操作（TODO）](#定义正式集合操作todo)
  - [WeakSet（TODO）](#weaksettodo)
- [7 迭代器与生成器（TODO）](#7-迭代器与生成器todo)
- [8 面向对象](#8-面向对象)
  - [理解对象](#理解对象)
    - [属性的类型](#属性的类型)
      - [数据属性](#数据属性)
        - [内部特性](#内部特性)
        - [delete 操作符](#delete-操作符)
        - [修改特性](#修改特性)
      - [访问器属性](#访问器属性)
        - [内部特性](#内部特性-1)
    - [定义多个属性](#定义多个属性)
    - [读取属性的特性](#读取属性的特性)
    - [合并对象（ES6）](#合并对象es6)
    - [is()（ES6）](#ises6)
    - [语法糖（ES6）](#语法糖es6)
      - [属性值简写](#属性值简写)
      - [可计算属性](#可计算属性)
      - [简写方法名](#简写方法名)
    - [对象解构（ES6）](#对象解构es6)
      - [复制对象](#复制对象)
      - [嵌套解构](#嵌套解构)
      - [部分解构](#部分解构)
      - [参数解构](#参数解构)
  - [创建对象](#创建对象)
    - [工厂模式](#工厂模式)
    - [构造函数模式](#构造函数模式)
      - [构造函数模式与工厂模式的区别](#构造函数模式与工厂模式的区别)
      - [使用 new 操作符调用构造函数流程](#使用-new-操作符调用构造函数流程)
      - [构造函数可以区别对象类型](#构造函数可以区别对象类型)
      - [构造函数也是函数](#构造函数也是函数)
      - [构造函数的问题](#构造函数的问题)
    - [原型模式](#原型模式)
      - [理解原型](#理解原型)
      - [原型方法](#原型方法)
        - [isPrototypeOf()](#isprototypeof)
        - [Object.getPrototypeOf()](#objectgetprototypeof)
        - [Object.setPrototypeOf()](#objectsetprototypeof)
      - [原型层级](#原型层级)
        - [hasOwnProperty()](#hasownproperty)
      - [原型和 in](#原型和-in)
      - [属性枚举](#属性枚举)
        - [属性枚举顺序](#属性枚举顺序)
    - [对象迭代](#对象迭代)
      - [Object.entries()](#objectentries)
      - [Object.values()](#objectvalues)
    - [补充](#补充)
      - [创建原型对象](#创建原型对象)
      - [原型的动态性](#原型的动态性)
      - [原生对象原型](#原生对象原型)
      - [原型的问题](#原型的问题)
  - [继承](#继承)
    - [原型链](#原型链)

# 0 资源链接

- [ECMAScript® 2025 Language Specification](https://tc39.es/ecma262/)

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

### 引入方式

#### 内联方式

```
<script>
  console.log('hello');
</script>
```

#### 外部引入

推荐这种引入方式，原因如下：

- 可维护性
- 缓存，浏览器会缓存 js 文件，多个 html 使用同一个 js 文件时不会重复下载
- 兼容，XHTML 对内部脚本的编写有更严格的规则，而外部脚本不用考虑这个问题

```
<!-- 最佳实践：此标签放在 body 内中的末尾 -->
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
  console.log(age); // 76
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

一共有 6 种简单数据类型（原始类型）：

- undefined
- null
- boolean
- string
- number
- symbol

以及 1 种复杂类型：

- object

### typeof 操作符

由于 JS 的数据类型是松散的，所以需要一个方法来判断数据类型：

```
let message = 66;

//传入变量
console.log(typeof(message));  // number

//传入字符串
console.log(typeof message);  // string
```

typeof 不是一个函数，它不需要传入参数（也可以传入），会返回以下 7 种类型：

- undefined
- boolean
- string
- number
- object
- function
- symbol

typeof null 返回结果是 object，因为 null 被认为是空对象的引用

严格来说，在 JS 中，function 是一种特殊 object，但是 function 有特殊的属性，所以需要进行区分

### undefined

声明变量，但是没有进行初始化时，变量的值就是 undefined

- 设置这个数据类型，是为了区分未初始化变量和空对象指针（null）的区别
- 没有声明变量，或者声明了未初始化，结果都是 undefined，所以建议声明时就进行初始化，这样一旦出现 undefined ，你就知道是变量没有声明
- undefined 在逻辑判断中被当作假值

### null

表示空对象指针

- 在定义一个用于保存对象的变量时，建议用 null 初始化，这样之后判断如果变量的值不为 null ，那么它的引用是一个对象
- undefined == null，这是 ECMAScript 定义的
- null 的逻辑值为假

### boolean

有两个字面值：true 和 false

Boolean() 函数可以将其他类型的值转换为布尔值，满足以下规则：

- string，非空字符串为 true，空字符串 "" 为 false
- number，非零数（无穷）为 true，0、NaN 为 false
- object，对象为 true，null 为 false
- undefined，都为 false

### number

表示整数或浮点数

#### 进制数

JS 中可以有 +0 和 -0，但是这两种都等同于 0 

十进制：

```
let int = 55;
```

八进制（以 0 开头）：

```
let octal = 070; //八进制的52
let octal = 079; //无效的八进制，当作 79
```

十六进制（以 0x 开头）：

```
let hex = 0xA; //十六进制 10
```

#### 浮点值

```
let float = 1.1;
let float = .1; //不推荐
let int = 1.0; //为了节省空间，1.0 会被转换为整数 1
```

#### 科学计数法

```
let float = 3.123e5; //等于 312300
let float = 3-e4; //等于 0.0003
```

#### 精度问题

```
let a = 0.1;
let b = 0.2;
console.log(a + b == 0.3); // 结果为 false
```

因为 JS 采用的 IEEE 754 数值规则：

单精度浮点数（32位）包括：1位符号位 8位指数位 23位符号位

如何存贮浮点数？

- 0.1 被转为二进制 0.000110011...（无限循环）
- 二进制转换为科学计数法：1.100110011... * 2^-4
- 因此符号位： 0（正数），指数位：0111 1111（127+（-4）= 123，再将123转换成二进制），数值位：1001 1001 1001 1001 1001 100（超过了23位，多余的省略）

在对 0.1 进行存贮的过程中，精度丢失，因此 0.1 会有细微的偏差，可以讨论以下它在丢失精度后的值是多少：

- 符号位：0，正数
- 指数位：0111 1111，转为十进制是 123，123 - 127 = -4
- 数值位：1001 1001 1001 1001 1001 100，结合指数位得到：1.1001 1001 1001 1001 1001 100 * 2^-4，即0.0001 1001 1001 1001 1001 1001 100
- 转为十进制：0.0999999940395355

可见，虽然存储的是 0.1，但是一旦参与运算，0.1 实际上是 0.0999999940395355

#### 无限值

JS 可表示的最小数保存在 Number.MIN_VALUE 中，最大值保存在 Number.MAX_VALUE 中，如果计算结果超过最大值，或者小于最小值，就会被自动转换为无穷值：Infinity 或 -Infinity，并且该值不能再参与计算

```
console.log(5/0);  //Infinity
console.log(5/-0);  //-nfinity
```

isFinite() 函数，判断一个变量是否是无限值

#### NaN

Not a Number，表示不是数值

```
console.log(0/0);  //NaN
console.log(-0/+0);  //NaN
```

- 任何有 NaN 的运算结果都为 NaN
- NaN 不等于任何值，也不等于它自身

isNaN() 函数，会先尝试将参数内容转化为 Number 类型（比如 数字字符串会被转换成数字，true 会被转换成 1），如果可以返回 true，否则返回 false

#### 数值转换

Number()，可以转换任何类型，规则复杂

parseInt()，转换为整数，可以接受两个参数：转换对象，进制

parseFloat()，转换为浮点数，只能解析十进制数，如果参数为整数，则会返回整数

### string

#### 字符串字面量

\n 换行，\t 制表，\r 回车，\' 单引号，\" 双引号，\\\ 反斜杠

#### 不可变

字符串是不可变的（immutable），要修改其值，必须销毁之前的字符串，再创建新的字符串

#### 字符串转换

```
let age = 10;
let string = age.toString(); //"10"
let string = age.toString(2); //转换为二进制字符串 "1010"
```

由于 null 和 undefined 没有 toString() 方法，可以通过 String() 创建字符串：

```
String(10); //"10"
String(null); //"null"
String(undefined); //"undefined"
```

#### 字符串模板

##### 字面量

模板字面量会保存反引号之间的所有空格、换行

```
//以下两个字符串是等价的
let string = 'first line\nsecond line';

//使用字符串模板
let template = `first line
second line`;
```

##### 插值

可以在模板字面量中通过插值的方式，使用变量，变量会被 toString() 转换为字符串

- 插值中，可以使用变量对象的函数
- 插值中，可以对多个变量进行运算

```
let val = 5;
let template = `value is ${val}`
```

##### 标签函数

标签函数是自定义的函数：

```
function template(strings,...expressions) {
  console.log(strings);
  for (const expression of expressions) {
    console.log(expression);
  }
  return 'result';
}

let a = 6;
let b = 9;

let result = template`${a} + $ {b} = ${a + b}`;
// ["", " + ", " = ", ""]
// 6
// 9
// 15

console.log(result); // "result"
```

函数参数 strings 接受的是原始字符串数组，...expressions（数组）接受了其他插值的结果

可以自定义插值的行为

#### 模板-原始字符串

可以获取模板字面量的原始内容：

```
String.raw`first line\nsecond line`;
//first line\nsecond line
```

### symbol（TODO）

确保对象的属性使用唯一标识符，不会发生冲突

### Object

对象类型 Object，一组功能和数据的集合

开发者可以通过 new 关键字创建 Object 对象，然后再给对象添加方法或属性

```
let o = new Object();
```

Object 作为所有对象的基类，其他对象都继承以下的属性或方法，但是 BOM 和 DOM 的对象可以不遵守 ECMAscript 规则，所以有些对象可能不会继承这些方法

#### 属性和方法

- constructor：创建当前对象的构造函数，上面例子中就是 Object()
- hasOwnProperty(proptypeName)：用于判断当前对象实例（不是原型）上是否存在名为 proptypeName（字符串或符号） 的属性
- isProptypeOf(object)：判断当前对象是否为另一个对象的原型
- propertyIsEnumerable(proptypeName)：判断给定属性是否可以使用 for-in 枚举，参数必须是字符串
- toLocaleString()：返回对象的字符串表示，该字符串反应对象所在的本地化执行环境
- toString()：返回对象的字符串表示
- valueOf()：返回对象的字符串、数值或布尔值，通常与 toString() 返回值相同，用于操作符比较大小会调用这个方法

## 操作符

### 一元操作符

#### 递增与递减

```
let age = 10;
++age;
```

操作符 ++ ，等同于 age = age + 1 ，++age 与 age++ 有以下区别：

- 前缀，先计算操作符结果，再进行其他计算
- 后缀，先进行其他计算，再进行操作符计算

对于 number 之外的数据类型，也可以使用，只不过需要先转换为 number（尽可能）再运算

#### 一元加减

```
let num = 2;
num = +num;  // 2
num = -num;  // -2
```

负号取相反数

### 位操作符

ECMAscript 采用 IEEE 754 64位格式存储数值，但位操作只采用 32 位，之后再把结果转换为 64 位。对于开发者，只有 32 位整数。

#### 按位非

```
let num1 = 25;
let num2 = ~num1;   // -26
```

num2 转换为十进制是 -26，按位非等效于：-num1 -1 ，不过位运算更高效

#### 按位与

```
let result = 25 & 3; // 1
```

与运算：全是 1 结果才为 1

#### 按位或

```
let result = 25 | 3; // 27
```

或运算：有一个 1 结果就是 1

#### 按位异或

```
let result = 25 ^ 3; // 26
```

异或运算：一个是 1 一个是 0 结果才为 1

#### 左移

```
let old = 2;
let val = 2 << 5; // 64
```

左移会保留正负号

数值 m 左移 n 位 = m * 2^n

#### 右移

```
let old = 64;
let val = 64 >>> 5; // 2
```

正数 m 右移 n 位 = m / 2^n

对于正数，右移没有影响。对于负数，右移影响很大（负数符号位位 1 ，右移左边补 0 ，会变正数）

### 布尔操作符

#### 逻辑非

`!val`，将操作数 val 转换为布尔值后，取反

`!!val`，效果等同于 Boolean(val) ，表示取布尔值

#### 逻辑与

```
&&
```

短路特性：第一个操作数位 false ，则不会对第二个操作数求值

#### 逻辑或

```
||
```

短路特性：第一个操作数位 true ，则不会对第二个操作数求值

短路特性的应用：

```
let ob = preob || backob
```

preob 包含首选的值，backob 包含备用的值

### 乘性操作符

#### 乘法

```
*
```

#### 除法

```
/
```

#### 取模

```
%
```

### 指数操作符

ES7 新增 **

```
3 ** 2;           // 9
Math.pow(3, 2);   // 9
```

### 加性操作符

#### 加法操作符

```
+
```

注意：字符串之间 + 表示连接字符串，数值之间 + 表示加法运算

#### 减法操作符

```
-
```

### 关系操作符

- `>`
- `<`
- `>=`
- `<=`

注意：

- 如果有一个操作数位 NaN，结果都是 false
- 字符串之间比较，如果都可以转换为数值，那么会从左到右依次比较两个操作数每一位的字符编码大小
- 字符串之间比较，如果有操作数不可以转换为数值，那么视作 NaN

### 相等操作符

#### 等于和不等于

```
==
!=
```

比较时会自动转换操作数，即 3 == "3" 结果为 true

#### 全等和不全等

```
===
!==
```

比较时不转换操作数，即 3 === "3" 结果为 false

### 条件操作符（三元运算）

```
let max = (num1 > num2) ? num1 : num2;
```

如果 num1 > num2 为 true ，那么取值为 num1 ，否则取值 num2

### 赋值运算符

```
=
```

与其他操作符的结合（简写，并不提升性能）：a -= b，表示 a = a - b，其他数学运算符同理

### 逗号操作符

```
let num1 = 1, num2 = 2, num3 = 3;
```

逗号赋值（赋值最后一项 0 ）：

```
let num = (5, 1, 2, 0);  // 0
```

## 语句

### if

ECMAscript 会调用 Boolean() 函数将 condition 转换成布尔值

最佳实践：

```
if (condition1) {
  statement1
} else if (condition2){
  statement2
} else {
  statement3
}
```

不要省略大括号，这样可以避免错误

### do-while

最佳实践：

```
do {
  statement
} while (expression);
```

### while

最佳实践：

```
while(expression) {
  statement
}
```

### for

最佳实践：

```
for(let i = 0; i < 10; i++) {
  console.log(i);
}
```

使用 let 可以将作用域固定在循环中，因为循环外用不到这个变量了

无穷循环：

```
for(;;) {
  console.log(1);
}
```

while 循环：

```
for(;i < 10;) {
  console.log(1);
}
```

### for-in

最佳实践：

```
for (const propName in window) {
  console.log(propName);
}
```

如上，遍历了一个 window 对象的所有属性，遍历的顺序因浏览器而异

为了保证遍历的变量 propName 不被修改，推荐使用 const

如果遍历的变量是 null 或 undefined，不会执行循环

### for-of

最佳实践：

```
for (const element of [2,4,6,8]) {
  console.log(element);
}
```

for-of 会按照可迭代对象的 next() 方法产生值的顺序迭代元素

如果尝试迭代的元素不支持迭代，会抛出错误

### 标签、break和continue

- break：退出当前这一层的循环
- continue：跳过当前这一层的本次循环

label 和 break 的配合使用：

```
outermost: 
for (let i = 0; i < 10; i++) {
  for (let j = 0; j < 10; j++) {
    if (i == 5 && j == 5) {
      break outermost;
    }
  }
}
```

如上，创建了一个名为 outermost 的 label，当最内层的循环执行到 break outermost; 时，会退出到标签 outermost 的位置（即直接退出到最外层的循环）

标签可以和 break 或 continue 配合，退出或者跳过到标签所指定的位置

### with

示例如下：

```
let qs = location.search;
let hostName = location.hostname;
let url = location.href;
```

这段代码每一次赋值都有重复的 location 对象，可以使用 with 简化代码：

```
with(location) {
  let qs = search;
  let hostName = hostname;
  let url = href;
}
```

严格模式不允许 with

### switch

基本用法：

```
switch(i) {
  case 25:
    console.log(25);
    break;
  case 35:
    console.log(25);
    break;
  default:
    console.log("other");
}
```

一个结果有多个条件（最好写明注释是故意忽略 break）：

```
switch(i) {
  case 25:
    /* skip */
  case 35:
    console.log(25);
    break;
  default:
    console.log("other");
}
```

ECMAscript 中 switch 的特点：

- 可以接收任何数据类型
- 在 case 比较时会使用全等操作符（===），因此不会强制转换数据类型

## 函数

基本写法：

```
function functionName(arg0,arg1,...,argN) {
  statements
}
```

只要遇到 return 语句，函数会立即停止执行

最佳实践：要么有返回值，要不没有返回值（默认返回 undefined），只在某个条件下返回值的函数，在调试时会很麻烦

# 3 变量、作用域与内存

## 原始值与引用值

原始值：6种原始数据类型（undefined，null，string，number，boolean，symbol）

引用值：对象（object）

### 动态属性

ECMAscript 中，引用值（对象）可以有动态的属性，即可以随时为对象创建新的属性、或修改属性值

而对于原始值，不可以添加属性：

```
let str = "name";
str.age = 9;
console.log(str.age); //undefined
```

但是可以通过 new 关键字，创建一个 object 类型的实例，这个实例行为类似于对应的原始值：

```
let str = new String("name");
str.age = 9;
console.log(str.age); // 9
```

### 复制值

#### 原始值的复制

```
let num1 = 1;
let num2 = num1;
```

- 以上代码，创建了一个原始值 num1，之后创建了 num2，并将 num1 的值复制给 num2，复制的操作实际上为 num2 创建了一个独立的值，即 num1 和 num2 的值互相独立
- 在内存中，num1 和 num2 在栈内存中，它们拥有相同的值 1，但是它们相互独立
- 可以说原始值是按值访问的

#### 引用值的复制

```
let obj1 = new Object();
let obj2 = obj1;
obj1.name = "lin";
console.log(obj2.name); // "lin"
```

- 以上代码，对引用值进行了复制操作，可以看到，引用值的复制不同于原始值的复制，复制的操作不会为 obj2 创建一个新的独立的值，而是让 obj2 直接去引用 obj1 的值
- 在内存中，obj1 和 obj2 在栈内存中，它们的值指向堆内存中的同一个值
- 可以说引用值是按引用访问的

### 传递参数

***ECMAscript中所有函数的参数都是按值传递的***

按值传递（函数内对参数的操作不会影响函数外的变量）：

```
function addTen(num) {
  num += 10;
  return num;
}
let count = 10;             
// 10，没有变化，说明是按值传递
// 如果是按引用传递，那么 count 的值应该为 20
let result = addTen(count); // 20
```

参数为引用值的情况：

```
function setName(obj) {
  obj.name = "Nick";
  obj = new Object();
  obj.name = "Bob";
}

let person = new Object();
setName(person);
console.log(person.name); // "Nick"
```

- 以上代码证明了参数是按值引用的
- 为什么`obj = new Object();`不起作用？当在函数内给 obj 重新赋值时，他变成了一个指向本地对象的指针，而这个本地对象在函数执行结束时就被销毁了
- 为什么函数没有返回值，`obj.name = "Nick";`却影响到了外部的 person 变量？因为虽然函数的参数不是按引用传递的，但是引用值（object）是按引用访问的，虽然函数内的 obj 和函数外的 person 不是一个变量，但是它们指向堆内存中同一个值

### instanceof

typeof 可以区分所有的原始值，但是无法区分 null 和 object（都返回 Object），为了区分所有引用类型，使用 instanceof

判断变量是否属于某种引用类型，返回 boolean

```
console.log(person instanceof Object);
console.log(person instanceof Array);
console.log(person instanceof RegExp);
```

语法：`variable instanceof constructor`

## 执行上下文与作用域

一些定义：

- 上下文：即字面意思，代码中函数或变量的上下文，大括号内都是一处上下文
- 全局上下文：最外层的上下文，浏览器中的 window 对象
- 上下文栈：每个函数都有自己的上下文，当代码执行进入函数时，函数的上下文会入栈，当此上下文所有代码执行完毕后会被销毁，栈顶的上下文弹出，然后再执行栈顶新的上下文
- 变量对象：每个上下文都有一个变量对象，用于存储所有在这个上下文中定义的变量和函数
- 活动对象：如果上下文是函数，活动对象用作变量对象，活动对象最初只有一个定义变量：arguments
- 作用域链：代码执行时，会创建变量对象组成的作用域链，根据作用域链决定查找变量的顺序。最前端永远是当前正在执行的上下文的变量对象，下一个是外面一层上下文的变量对象，直到末尾（末尾一定是全局上下文的变量对象）

举例：

```
var color1 = "blue";
function changeColor() {
  let color2 = "red";
  function swapColor() {
    let temp = color2;
    color2 = color1;
    color1 = temp;
  }
}
```

再以上代码中，函数内部可以访问外部的变量，而外部无法访问函数内部的变量（temp），正是作用域链的顺序查找实现了这种规则

以上代码的作用域链：

```
window
  |__color1
  |__changeColor()
          |__color2
          |__swapColor()
                  |__temp
```

分析：

- 有哪几个变量对象？window 的变量对象、changeColor() 的变量对象、swapColor() 的变量对象，它们一级套一级，属于嵌套关系
- 代码执行时，如何解析标识符（查找需要的变量）？代码执行时，会先从当前变量对象查询，如果没有，再到上一级变量对象查询，直到找到变量（不能查询下一级）
- 代码执行到 `color2 = color1;`， 按什么顺序查找变量 color1？变量对象1（temp）===> 变量对象2（swapColor()）===> 变量对象2（color2）===> 变量对象3（changeColor()）===> 变量对象3（color1）===> 全局上下文的变量对象（window）

### 作用域链增强

作用域链增强：某些语句会导致作用域前端临时添加一个上下文

#### with 语句

会向作用域链前端插入 with 指定的对象

#### try/catch 中的 catch 块

会向作用域链前端插入新的变量对象，包含要抛出错误的对象的声明

### 变量声明

#### 函数作用域声明（var）

```
function add(num1, num2) {
  var sum = num1 + num2;
  return sum;
}

let result = add(10, 20);
console.log(sum); // 报错
```

如以上代码，函数内部 var 声明的变量在外部无法访问，这是因为 var 声明的变量会添加到最近的上下文（add() 内的上下文）

```
function add(num1, num2) {
  sum = num1 + num2;
  return sum;
}

let result = add(10, 20);
console.log(sum); // 30
```

如果不使用 var 声明变量，sum 会被添加到全局上下文，函数外面可以访问到，因为变量提升了

声明提升：作用域中的代码不必考虑变量是否已经声明就可以直接使用，因为变量会以 window.sum 的形式提升到全局上下文中

#### 块级作用域声明（let）

let 的作用域是块级的，块级作用域由一对大括号界定，也就是说，只要在大括号内使用 let 声明变量，外界是无法访问的，强行访问会报错

let 也不能进行重复声明，会报错，var 却可以

严格来说，let 也可以进行提升，但是由于 “暂时性死区” 的缘故，在声明前使用变量会报错

#### 常量声明（const）

const 的声明和初始化必须同时进行，不然会报错，并且一经声明，不能再重新赋值

const 被赋值为引用值时，仍然可以对引用值内部的属性进行修改，因为修改引用值属性，并没有修改变量的引用值（引用值可以看作指向对象的指针）。如果想让整个对象都无法被修改，可以使用 `Object.freeze()`（参数中传入对象），这样修改属性时虽然不会报错，但是会静默失败

#### 标识符查找

代码执行到需要某个变量时，会按作用域链的顺序查找变量，如果不同作用域中有多个重名的变量，会优先使用最近上下文中的变量：

```
var color = "red";
function getColor() {
  let color = "green";
  {
    let color = "blue";
    console.log(color); // "blue"
  }
}
```

## 垃圾回收

JS 使用了垃圾回收，即执行环境负责管理代码执行时的内存，垃圾回收是周期性的，会每隔一定时间（或者说在代码执行过程中的某个预定回收时间），对于某块内的内存是否应该进行回收，需要使用到标记策略：

### 标记清理

标记清理是 JS 最常用的垃圾回收策略。当变量进入上下文（比如函数内部声明一个变量）时，会被加上存在于上下文中的标记，当变量离开上下文时，也会被加上离开上下文的标记。

垃圾回收程序运行过程：会标记内存中所有的变量，然后对于所有在上下文当中的变量，以及被这些变量引用的变量，会去除它们的标记，剩余有标记的变量则是需要回收的变量，因为上下文中的任何变量都与它们无关了。然后会进行一次内存清理，销毁所有带有标记的变量值以及内存

### 引用计数

引用计数不大常用。堆内存中，当一个引用值被变量引用时，引用数加 1，如果一个变量不再引用这个引用值时，引用数减 1，当引用数为 0 时，表示没有变量再需要这个引用值了，垃圾回收程序下次执行时会释放引用数为 0 的值的内存。

#### 问题：循环引用

```
function problem() {
  let ob1 = new Object();
  let ob2 = new Object();
  ob1.someObject = ob2;
  ob2.anotherObject = ob1;
}
```

以上代码，ob1 的属性引用了 ob2，而 ob2 的属性引用了 ob1，如果采用标记清理策略，完全没有问题，因为当函数执行完毕，跳出当前作用域后，垃圾回收程序会将 problem() 上下文中所有的变量清除。如果采用引用计数策略，ob1 和 ob2 的引用数永远是 2，并且永远不会变为 0，内存永远不会被释放

问题不止于此。在 IE8 时期，BOM DOM 中的对象是 C++ 实现的（COM对象），而这些 COM 对象采用引用计数的垃圾回收策略，因此即使 JS 使用标记清理策略，如果 JS 中的对象和 DOM 对象产生了循环调用，DOM 对象永远不会被回收，除非在代码中将对象的属性设为 null，手动将引用数重置为 0。好在 IE9 已经将 DOM BOM 对象改为了 JS 对象，避免了问题

### 性能

如果垃圾回收频率过低，那么内存中会有太多变量，造成性能损失。如果垃圾回收频率过高，那么对于重度依赖 JS 的网页，可能需要多次加载变量，造成性能损失

IE 曾饱受诟病。它的策略如下，分配 256 个变量、4096个对象/数组字面量和数组slot、64KB字符串，只要满足其中一个条件，就会执行垃圾回收。问题在于，可能一次真的需要用到那么多的变量，这样会导致垃圾回收频繁执行，影响性能

IE7 更新了垃圾回收程序，之前固定的阈值被改良为动态阈值，阈值初始值和之前相同，如果本次回收的内存不到已分配的 15%，这些阈值就会翻倍，如果本次回收的内存超过了已分配的 85%，那么阈值会重置为初始值。极大提高了性能

### 内存管理（TODO）

JS 提供了垃圾回收程序，开发者通常无需关心内存管理，不过仍然有一些方法可以进行内存优化。优化内存的最佳手段就是保证执行代码时只保存必要的数据，如果不再需要数据，将其设为 null，这种方法叫做 ***解除引用***

还有一些内存管理的方法：

#### 通过 const 和 let 声明提升性能

let 与 const 都以块为作用域，所以相比域 var (函数作用域)，使用这两个关键字可能会更早地让垃圾回收程序介入，从而减少不必要的内存占用

#### 隐藏类和删除操作

# 4 基本引用类型

引用类型：又称为对象定义，描述了对象应有的属性和方法，引用值（对象）是某个特定引用类型的实例

ECMAscript 中的引用类型经常被人们和 Java 中的类混淆。ECMAscript 虽然上是一种面向对象语言，但是缺少传统面向对象编程语言的某些基本结构，比如类和接口

使用 new 关键字，在跟上一个构造函数，可以创建引用类型的实例：

```
let now = new Date();
```

ECMAscript 提供了许多像 Date 这样的原生引用类型，帮助开发者实现常见任务

## Date

ECMAscript 参考了 Java 早期的 java.util.Date，因此 Date 将日期保存为自协调世界时（UTC，Universal Time Coordinated）时间 1970.01.01 00:00:00 至今所经历的毫秒数，这样 Date 类型可以表示从 1970 年 1 月 1 日 前后 285616 年的日期

### 构造函数

以下代码创建了一个 Date 对象，不传参的情况下，创建的是当前的时间

```
let now = new Date();
```

如果要创建特定的时间，需要方法的协助：Date.parse() 和 Date.UTC()

#### Date.parse() 

接受一个符合要求格式的字符串，尝试将其转换为毫秒数（不符合规则返回 NaN），以下是其支持的日期格式：

- "5/23/2019"
- "May 23, 2019"
- "Tue May 23 2019 00:00:00 GMT-0700" (GMT，GreenwichMeanTime，格林威治标准时间，-0700表示是西七区的时间)
- "2019-05-23T00:00:00Z"（Z表示零时区，如果是+8表示东八区）

```
// 以下两种方式是等价的
let now = new Date("5/23/2019");
let now = new Date(Date.parse("5/23/2019"));
```

#### Date.UTC() 

可以接受多个参数：年，月（0-11），日（1-31），时（0-23），分，秒，毫秒，其中年月是必须的，其他可选

```
Date.UTC(Date.UTC(2000,0));             // 2000-01
Date.UTC(Date.UTC(2005,3,4,14,33,44));  // 2005-04-04 14:33:44
```

当使用 Date() 构造函数隐式调用 Date.UTC() 时，创建的是当地时区的时间，而直接调用 Date.UTC() 创建的是 GMT 时间

#### Date.now()

返回当前时间的毫秒值，可以用于在代码中计时：

```
let start = Date.now();

doSomething();

let finish = Date.now();

duration = finish - start;
```

### 继承的方法

- toLocaleString()，会返回浏览器环境的时间，格式通常包含 AM PM，而不包含时区，具体格式因浏览器而不同
- toString()，通常返回带时区的时间格式，时间也是 24 小时制的
- valueOf()，返回毫秒值，可以通过这个方法比较时间先后

### 日期格式化

以下格式化方法的具体格式因浏览器而异

- toDateString()，周几，年月日
- toTimeString()，时分秒，时区
- toLocaleDateString()，本地的时区，时分秒
- toLocaleTimeString()，时分秒
- toUTCString()，UTC时间（自协调世界时）

### get/set 方法

这类方法用于获取（get）或设置（set）具体的时间，每个 set 方法都有对应的 get 方法，故以下对  get 方法省略，并且每个 set 方法都有对应的 setUTC 方法，比如 `setHours(0-23)` 对应的 setUTC 方法 `setUTCHours(0-23)` ，以下也对 setUTC 方法省略

- setFullYear(四位数)
- setMonth(0-11)，大于11则加年
- setDate(1-31)，大于31则加月
- setHours(0-23)，大于23则加天
- setMinutes(0-59)，大于59则加时
- setSeconds(0-59)，大于59则加分
- setMilliseconds(0-59)，大于59则加秒

特殊的方法：

- getDay()，周几（返回0-6），有对应的 getUTC 方法，没有对应 set 方法
- setTime(毫秒值)，设置日期毫秒值，有对应的 get 方法，没有 getUTC 方法
- getTimezoneOffset()，返回本地时区与UTC时间的偏移量（分钟）

## RegExp (TODO)

正则表达式：

```
let expression = /pattern/flags;
```

pattern 是正则表达式，flags 标记用于控制表达式的模式（可以一次使用多个标记），flags 包括以下标记：

- g：全局模式，不是找到第一个匹配内容就结束
- i：不区分大小写
- m：多行模式，查找到一行末尾时会继续查找
- y：粘附模式，表示只查找从 lastIndex 开始之后的字符串
- u：Unicode 模式，启用 Unicode 匹配
- s：dotAll 模式，元字符 . 匹配任何字符（包括 \n \r）

## 原始值包装类

ECMAscript 提供了 3 种特殊的引用类型：Boolean、Number、String

### 包装类的创建

#### 自动创建

每当使用某个原始值的方法或属性时，会自动创建一个相应类型的对象，从而暴露原始值的各种方法：

```
let s1 = "text";
let s2 = s1.substring(2);
```

执行到第二行时包含以下操作：

1. 创建 String 类型的实例
2. 调用其 substring() 方法
3. 销毁实例

这三步相当于以下代码：

```
let ob = new String("text");
let s2 = ob.substring(2);
ob = null;
```

值得注意的是，这个自动创建的对象实例，不能直接给原始数据类型添加属性，因为自动创建的包装类实例会在执行完毕后被销毁：

```
let s1 = "text";
s1.color = "red";
console.log(s1.color); // undefined
```

可以显示地创建包装对象，但是不建议这么做，因为这样无法区分原始值和引用值，对包装对象实例使用 typeof 返回的都是 object

#### Object() 创建包装类

```
let obj = new Object("text");
console.log(obj instanceof String); // true
```

#### Number() 与 new Number()

```
let val = "25";
let number = Number(val);
console.log(typeof number); // number
let obj = new Number(val);
console.log(typeof obj);    // object
```

### Boolean

创建一个 Boolean 对象，使用构造函数并传入 true 或 false ：

```
let booleanObject = new Boolean(true);
```

重写方法：

- valueOf()，返回原始值 true 或 false
- toString()，返回字符串 "true" 或 "false"

强烈建议 ***永远不要使用 Boolean 包装类*** ，而是使用原始值，因为包装类容易和原始值混淆：

```
let falseObj = new Boolean(false);
let result = falseObj && true;    // true

let falseVal = new Boolean(false);
let result = falseVal && true;    // false
```

### Number

创建一个 Number 对象，使用构造函数传入数字：

```
let numberObject = new Number(10);
```

重写方法：

- valueOf()，返回原始数值
- toString()，返回数值字符串，并且可以传入数字参数，将返回转换成相应的进制数：

```
let num = 10;
num.toString(2);  // "1010"
num.toString(8);  // "12"
num.toString(10); // "10"
num.toString(16); // "a"
```

**格式化方法**：

toFixed()，参数是数值，返回值根据传入的参数决定返回的小数位数，如果指定的小数位数小于原本的小数位数，那么进行四舍五入

toExponential()，返回科学计数法格式（1.0e+1 表示 10），参数是数值，表示小数的位数

toPrecision()，参数是数值，表示希望返回结果的总位数（正数位和小数位的总和），方法会根据参数情况选择调用 toFixed() 还是 toExponential()，返回合适的结果：

```
let num = 99;
num.toPrecision(1);   // "1e+2"
num.toPrecision(2);   // "99"
num.toPrecision(3);   // "99.0"
```

和 Boolean 一样，也不建议使用 Number 包装类

**其他方法**：

isInteger()，判断一个数值是否是整数

```
Number.isInteger(1);    // true
Number.isInteger(1.00); // true
Number.isInteger(1.01); // false
```

isSafeInteger()，判断一个整数是否在保存范围之内（Number.MIN_SAFE_INTEGER: -2^53+1, Number.MAX_SAFE_INTEGER: 2^53+1）

### String（TODO）

创建一个 String 对象，使用构造函数传入字符串：

```
let stringObject = new String("hello");
```

重写方法：

- valueOf()，返回字符串
- toString()，返回字符串

String 类型提供了很多方法来解析或操作字符串：

#### JavaScript 字符（TODO）

字符：一个字符由 16 个码元（code unit）组成

length 属性，表示字符串包含多少个 16 位码元（字符）

charAt() 方法，参数为索引值，根据索引值返回字符

JS 字符串的编码：采用 UCS-2 和 UTF-16，[更多关于编码的内容](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)

#### normalize()（TODO）

规范化字符

#### 字符串操作方法

concat()，连接字符串，可接受多个字符串参数按顺序进行拼接（拼接多个字符串使用 + 更方便）

```
let str = "hello";
let result = str.concat(" world", "!"); // "hello world!"
```

slice()，提取子字符串，一个参数左闭，两个参数左闭右开，参数为负数则转换为长度加上此负数

```
let str = "hello world";

str.slice(3);       // lo world
str.slice(3, 7);    // lo w
str.slice(-3);      // rld
str.slice(3, -4);   // lo w
```

substr()，提取子字符串，一个参数左闭，两个参数：第一个参数左闭、另一个参数是区间大小，第一个参数为负数则转换为长度加上此负数，第二个参数为负数则转换为 0 （区间长度为 0）

```
let str = "hello world";

str.substr(3);      // lo world
str.substr(3, 7);   // lo worl
str.substr(-3);     // rld
str.substr(3, -4);  // ""
```

substring()，提取子字符串，一个参数左闭，两个参数左闭右开，参数若是负数都转换为 0，特性：两个参数的情况，第二个参数若小于第一个参数，那么以第二个参数为开始位置，第一个参数为结束位置

```
let str = "hello world";

str.substring(3);     // lo world
str.substring(3, 7);  // lo w
str.substring(-3);    // hello world
str.substring(3, -4); // hel
```

#### 字符串位置方法

indexOf()，传入字符串，从头开始，找到字符串第一次出现的位置，返回下标，没有则返回 -1。第二参数可选，表示从此下标位置开始寻找

```
let str = "hello world";

str.indexOf("o"); // 4
str.indexOf("o", 6); // 7
```

lastIndexOf()，传入字符串，从尾部开始，找到字符串第一次出现的位置，返回下标，没有则返回 -1。第二参数可选，表示从此下标位置开始寻找

```
let str = "hello world";

str.lastIndexOf("o"); // 7
str.lastIndexOf("o", 6); // 4
```

找到所有的目标子字符串：

```
let str = "3213217894392693847252";
let postitions = new Array();
let pos = str.indexOf("3");

while(pos > -1) {
  positions.push(pos);
  pos = str.indexOf("3", pos + 1);
}
```

#### 字符串包含方法

startsWith()，判断字符串开头是否有指定的子字符串，接受一个字符串，返回布尔值，表示是否包含

```
let str = "foobarbaz";

str.startsWith("foo"); // true
```

endsWith()，判断字符串结尾是否有指定的子字符串，接受一个字符串，返回布尔值，表示是否包含

```
let str = "foobarbaz";

str.endsWith("baz"); // true
```

includes()，判断字符串中是否有指定的子字符串，接受一个字符串，返回布尔值，表示是否包含

```
let str = "foobarbaz";

str.includes("bar"); // true
```

#### 字符串去除空格

trim()，清除字符串开始和末尾的空格

trimLeft()，清除字符串开始的空格

trimRight()，清除字符串末尾的空格

#### 字符串填充方法

repeat()，接受数值参数，表示复制多少次

```
let str = "na ";
str.repeat(4);    // "na na na na "
```

padStart()，将字符串以指定内容填充到指定长度（填充在开头），第一个参数是填充到的长度，第二个参数是要填充的内容（默认填充空格），如果填充长度小于原本长度，返回原字符串

```
let str = "hi";
str.padStart(8);        // "      hi"
str.padStart(8, ".");   // "......hi"
str.padStart(8, "abc"); // "abcabchi"
```

padEnd()，填充在末尾，其他和 padStart() 一样

```
let str = "hi";
str.padEnd(8);        // "hi      "
str.padEnd(8, ".");   // "hi......"
str.padEnd(8, "abc"); // "hiabcabc"
```

#### 字符串迭代与解构（TODO）

#### 字符串大小写转换

toLowerCase()，将字符串转换为小写

toUpperCase()，将字符串转换为大写

toLocaleLowerCase()，将字符串以当地语言的规则转换为小写

toLocaleUpperCase()，将字符串以当地语言的规则转换为大写

#### 字符串模式匹配方法（TODO）

#### 比较字母顺序

localeCompare() 可以根据所在地区语言（不一定是英文字母）比较字母顺序，靠前返回 1，相同返回 0，靠后返回 -1

```
let str = "yellow";

str.localeCompare("brick");   // 1
str.localeCompare("yellow");   // 0
str.localeCompare("zoo");   // -1
```

#### HTML 方法

早期浏览器提供了辅助生成 HTML 标签的方法，现在基本上已经没人使用了

## 单例内置对象

内置对象：由 ECMAscript 实现，与宿主环境无关，并在程序开始执行时就存在的对象

开发者不需要显示地实例化内置对象，比如：Object Array String

### Global

全局函数和全局变量都会成为 Global 对象的属性，isFinite() parseInt() parseFloat() 都属于 Global 对象

#### URL 编码方法

URL编码将字符转换成可以通过 Internet 传输的格式，URL 只能使用 ASCII 字符集通过 Internet 发送

URI(Uniform Resource Identifier)：统一资源标识符

URL(Uniform Resource Locator)：统一资源定位器

[ASCII 百分比编码](https://zh.wikipedia.org/wiki/%E7%99%BE%E5%88%86%E5%8F%B7%E7%BC%96%E7%A0%81)

编码方法：

- encodeURI() 用于对整个 URI 编码，不会编码特殊字符
- encodeURIComponent() 用于编码 URI 种单独的组件，会对所有特殊字符也进行编码

```
let uri = "http://www.wrox.com/illegal value.js#start";

encodeURI(uri);
// http://www.wrox.com/illegal%20value.js#start

encodeURIComponent(uri);
// http%3A%2F%2Fwww.wrox.com%2Fillegal%20value.js%23start
```

解码方法：

- decodeURI()，对 encodeURI() 的结果解码
- decodeURIComponent()，对 encodeURIComponent() 的结果解码

#### eval()

这个方法是一个代码解释器，参数是一个 ECMAscript 字符串

```
eval("console.log('hi')");
// 以上代码等价于：
console.log("hi");
```

eval() 内部可以正常访问外部定义的变量，在 eval() 内部定义的函数外部也可以访问，但 eval() 内部定义的变量外部访问会报错。

eval() 解析字符串的能力很强大，可以动态创建函数，可以将 JSON 字符串直接解析成 JS 对象，但是它很危险，容易受到 XSS 攻击，让恶意用户插入代码。***不要使用 eval()***

#### 属性

Global 还包含了许多属性，包括一些特殊值：undefined NaN Infinity，以及包装类和一些引用类型的构造函数，还有各种 Erorr 对象的构造函数

#### window 对象

ECMAscript 没有提供直接访问 Global 对象的方式，但浏览器将 Global 对象进行实现，即 window 对象，因此全局变量和函数都成为了 window 的属性

当一个函数没有明确指定 this 时，this 值等于 Global 对象：

```
// 创建函数并立即调用
let global = function() {
  return this;
}();
```

### Math

Math 用于数学计算

#### 属性

- PI，圆周率
- E，自然对数的基数 e
- LN10，LN2，LOG2E，LOG10E 等对数
- SQRT1_2，SQRT2 等平方根

#### 最大值最小值

min() 和 max() 接受多个数值，返回其中最大或最小值

```
let max = Math.max(1,3,4,2,5);  // 5
let vals = [4,2,3,5,1];
let min = Math.min(...vals);    // 1
```
#### 舍入方法

- ceil() 向上舍入取整
- floor() 向下舍入取整
- round() 四舍五入取整
- fround() 返回数值最接近的单精度（32位）浮点值表示

#### 随机数

random() 返回 0-1 之间的一个随机数，区间左闭右开

随机选取一个整数，区间从 first_possible_value 开始，区间长度为 total_number_of_choice，左闭右开：

```
number = Math.floor(Math.random() * total_number_of_choice + first_possible_value)
```

一般情况，给定的参数是可选区间的左右边界，所以可以封装为函数：

```
function selectFrom(low, up) {
  let choice = up - low + 1;
  return Math.floor(Math.random() * choice + low);
}

// 使用 selectFrom() 方法，在数组中随机选择一个值

let colors = ["red", "green" ,"blue"];
let color = colors[selectFrom(0, colors.length - 1)];
```

#### 其他方法

- abs() 绝对值
- pow(x, n) 返回 x 的 n 次方
- sqrt() 平方根
- cbrt() 立方根
- exp(x, n) 返回 x 的 n 次幂 
- 各种三角函数...

# 5 集合引用类型

## Object

Object 没有多少功能，但是很适合用于临时存储交换数据

构造函数创建方式:

```
let person = new Object();
person.name = "lin";
person.age = "23";
```

字面量对象创建方式（这种方式不会调用 Object() 构造函数）：

```
let person = {
  name: "lin",
  age: 23
}
// 或者：
let person = {};
person.name = "lin";
person.age = 23;
```

也可以通过 [] 设置动态属性名：

```
let key = "name"
let person = {
  [key]: "lin",
  age: 23
}
console.log(person.name);   // lin
```

对象字面量的应用：给函数传入可选参数，即给函数传入一个对象，函数内部判断对象中是否有某个属性，如果有则可以将这个属性当作一个参数使用。一般对于必选的参数采用命名参数，对可选的参数采用对象字面量封装多个参数。

属性的获取，两种方式：

```
person.name;
person["name"];
// 中括号一般用于属性名不适合使用点方法的时候：
person["first name"];
```

详见第 7 章

## Array

ECMAscript 的数组可以存储任何类型。比如，数组中第一个是对象，第二个是 Number，第三个是 String。并且数组长度是动态的

### 创建数组

#### 构造函数方式

可以省略 new 操作符

```
// 创建空数组
let colors = new Array();
// 创建时规定数组长度
let colors = new Array(20);
// 创建时传入元素
let colors = new Array("red", "blue", "green");
```

#### 数组字面量方式

这种方式不会调用 Array() 构造函数

```
// 创建空数组
let colors = [];
// 创建时传入元素
let colors = ["red", "blue", "green"];
// 多一个逗号也是可以的，等价于 [1, 2]
let colors = [1, 2,];
```

#### from()

将其他类数组结构转换为数组（ES6）：

String 转数组

```
Array.from("abcd");
// ["a", "b", "c", "d"]
```

Map 转数组

```
Array.from(new Map().set(1, 2).set(3, 4));
// [[1, 2], [3, 4]]
```

Set 转数组

```
Array.from(new Set().add(1).add(2).add(3).add(4));
// [1, 2, 3, 4]
```

对现有数组浅拷贝

```
const a1 = [1, 2, 3, 4];
const a2 = Array.from(a1);  // [1, 2, 3, 4]
alert(a1 === a2);   // false
```

可迭代对象转数组

```
const iter = {
  *[Symbol.iterator]() {
    yield 1;
    yield 2;
    yield 3;
    yield 4;
  }
}
Array.from(iter);   // [1, 2, 3, 4]
```

arguments 对象转数组

```
function getArgs() {
  return Array.from(arguments);
}
getArgs(1, 2, 3, 4);    // [1, 2, 3, 4]
```

带有必要属性的对象转数组

```
const arrayLikeObject = {
  0: 1,
  1: 2,
  2: 3,
  3: 4,
  length: 4
}
Array.from(arrayLikeObject);    // [1, 2, 3, 4]
```

from() 还可以接受第二个参数，这是一个函数参数，可以对原数组的所有值进行增强，`Array.from(ary, function)` 等价于 `Array.from(ary).map(function)`，第二种方法需要通过 from() 创建一个中间数组，在使用 map() 进行数组处理，比较麻烦，因此推荐第一种

```
const a1 = [1, 2, 3, 4];
const a2 = Array.from(a1, x => x**2);
// [1, 4, 9, 16]
```

from() 还可以接收第三个参数，用于指定第二个函数参数中 this 中的属性值

```
const a1 = [1, 2, 3, 4];
const a2 = Array.from(a1, function(x) {return x**this.exponent}, {exponent: 2});
// [1, 4, 9, 16]
```

#### of()（TODO）

将传入的参数转换为数组，代替 ES6 之前的方法 `Array.prototype.slice.call(arguments)`

```
Array.of(1, 2, 3, 4);   // [1, 2, 3, 4]
Array.of(undefined);    // [undefined]
```

### 数组空位

ECMAscript 中的数组允许有空值

```
let ary = [,,,,,];
console.log(ary.length);  // 5
console.log(ary);         // [,,,,,]
```

ES6 新增方法（比如 for-of、数组展开）将这些空位当成存在的元素，值为 undefined

ES6 之前的方法（比如 map() join()）会有其他的行为（比如忽略空位，将空位视为空字符串）

由于方法对空位的行为不一致，避免使用空位数组，如果非要使用，可以显示地用 undefined 来代替

### 数组索引

索引从 0 开始，可以通过索引获取数组某一项的值，也可以通过索引对某一项赋值

```
let colors = ["res", "blue", "green"];
// 将 green 修改为 black
colors[2] = "black";
// 为数组增添新的一项
colors[3] = "brown"
```

length 属性：

- 保存数组的长度
- 不是只读的，可以修改数值，如果新长度小于原长度，会删除末尾多余的项，如果新长度大于原长度，会使用 undefined 来填充
- 数组添加新元素时，会自动修改 length 的值

```
let colors = ["res", "blue", "green"];
// 可以将 length 作为索引值，这样表示在数组末尾添加一个新元素
let colors[colors.length] = "brown"
// 以下操作将数组扩展到 99 长度，但是其中索引值为 4-98 的元素值为 undefined
let colors[99] = "brown"
```

### 检测数组

使用 instanceof，只判断 Array 是否在 ary 的原型链上，如果网页中有多个框架，可能有两个全局上下文，此时就会有两个 Array 构造函数，这种情况下 instanceof 会失效

```
ary instanceof Array
```

#### isArray()

只判断是不是数组，不管它的原型链在哪个框架上

```
Array.isArray(ary);
```

### 迭代器方法（TODO）

### 复制和填充方法

#### fill()

fill() 可以向一个已有的数组插入全部或部分相同的值

一个参数，填充所有项为指定参数值

```
const ary = [0, 0, 0, 0, 0, 0];
ary.fill(5);  // [5, 5, 5, 5, 5, 5]
```

两个参数，用第一个参数填充数组中索引大于等于第二个参数的元素

```
const ary = [0, 0, 0, 0, 0, 0];
ary.fill(5, 3);   // [0, 0, 0, 5, 5, 5]
```

三个参数，用第一个参数填充索引大于等于第一个参数，小于第三个参数的元素

```
const ary = [0, 0, 0, 0, 0, 0];
ary.fill(5, 1, 3);   // [0, 5, 5, 0, 0, 0]
```

如果区间值为负数，转换为 ary.length + 负值

如果区间值过小或过大，不进行填充

如果区间值前大后小，无效区间，不进行填充

如果只有右区间值过大，视为一直填充到末尾

#### copyWithin()

copyWithin() 会按指定范围复制数组内的部分内容

一个参数 n，将数组从头开始到索引 n-1 的内容复制到 n 的位置，直到达到数组边界

```
let ints = [0, 1, 2, 3, 4, 5];
ints.copyWithin(4);   // [0, 1, 2, 3, 0, 1]
```

两个参数 a b，从索引为 b 的元素开始，将之后的元素复制到 a 的位置

```
let ints = [0, 1, 2, 3, 4, 5];
ints.copyWithin(1, 4);    // [0, 4, 5, 3, 4, 5]

let ints = [0, 1, 2, 3, 4, 5];
ints.copyWithin(3, 4);    // [0, 1, 2, 4, 4, 5]
```

三个参数 a b c，将索引 b 到索引 c 之间的元素（左闭右开）复制到 a 的位置

```
let ints = [0, 1, 2, 3, 4, 5];
ints.copyWithin(0, 3, 5);   // [3, 4, 2, 3, 4, 5]
```

如果区间值为负值，转换为 ints.length + 负值

如果区间值过小或过大，不进行填充

如果区间值前大后小，无效区间，不进行填充

如果只有右区间值过大，视为一直填充到末尾

### 转换方法

#### toString() 和 valueOf()

数组的 toString() 方法返回值：将每个元素的 toString() 方法结果采用逗号拼接的字符串

```
let colors = ["res", "blue", "green"];
colors.toString();  // "res,blue,green"
colors.valueOf();   // "res,blue,green"
colors;             // "res,blue,green"
```

#### toLocaleString()

数组的 toLocaleString() 方法返回值：将每个元素的 toLocaleString() 方法结果采用逗号拼接的字符串。所以一个数组的 toString() 和 toLocaleString() 返回值可能不同，依据于每个元素的具体方法

#### join()

如果不想以逗号作为打印结果的分隔符，可以使用 join()

```
let colors = ["res", "blue", "green"];
alert(colors.join("||"));   // "res||blue||green"
```

如果参数为空或者 undefined，那么仍然使用逗号为分隔符

#### 数组空位的特殊情况

对于数组空位，toString()、valueOf()、toLocaleString()、join() 会将其视为空字符串

```
let colors = ["res", "blue", "green",,,];
alert(colors.join("||"));   // "res||blue||green||||"
```

### 栈方法

ECMAscript 提供了几个方法，数组可以像栈一样进行操作（LIFO，Last-In-First-Out，后进先出），比如推入操作（push），弹出操作（pop）

#### push()

方法一次向数组中推入多个元素，返回数组长度

```
let colors = new Array();
colors.push("red", "blue"); // 2
```

#### pop()

方法删除数组中最后一个元素，并返回删除的元素值

接上例：

```
alert(colors);  // "red,blue"
colors.pop();   // "blue"
```

### 队列方法

数组也可以像队列一样进行操作（FIFO, First-In-First-Out, 先进先出）

#### shift()

方法删除数组第一个元素，并返回删除的元素值

#### unshift()

在数组开头添加多个值

### 排序方法

#### reverse() 

将数组倒序排列

#### sort()

升序排序，通过 String() 将数组中每个元素转换为字符串，然后按照字符串大小排列。在对数值排序时，会产生问题，比如 10 会排到 5 的前面，因为 "10" 的第一个字符 "1" 小于 "5"，因此 sort() 还可以接受一个比较函数

```
function compare(a, b) {
  if(a < b) {
    return -1;
  } else if (a > b) {
    return 1;
  } else {
    return 0;
  }
}
let vals = [2, 1, 4, 3, 5];
vals.sort(compare);
alert(vals);    // [1, 2, 3, 4, 5]
```

可以将比较函数简化为箭头函数：

```
vals.sort((a, b) => a < b ? -1 : a > b ? 1 : 0);
```

可以进一步简化：

```
vals.sort((a, b) => a - b);
```

### 操作方法

#### concat()

连接数组

```
let ary = ["a", "b", "c"];
let ary2 = ary.concat("d", ["e", "f"]);
alert(ary2);  // ["a", "b", "c", "d", "e", "f"]
```

可以注意到，concat() 的参数一个是字符串，一个是字符串数组，默认会打平数组参数，即将 `["e", "f"]` 视为 `"e", "f"` ，当然也可以通过一个配置来阻止打平数组的行为:

```
let ary = ["a", "b", "c"];
let letters = {
  [Symbol.isConcatSpreadable]: true,
  length: 2,
  0: "d",
  1: "e"
};
let newletters = ["d", "e"];
newletters[Symbol.isConcatSpreadable] = false;
ary.concat(letters);      // ["a", "b", "c", "d", "e"]
ary.concat(newletters);   // ["a", "b", "c", ["d", "e"]]
```

#### slice()

截取一部分数组

一个参数 n，从 n 开始截取到末尾

```
let letters = ["a", "b", "c", "d", "e"];
letters.slice(1);     // ["b", "c", "d", "e"]
```

两个参数 a b，截取索引 a 到索引 b 之间的元素（左闭右开）

```
let letters = ["a", "b", "c", "d", "e"];
letters.slice(1, 4);  // ["b", "c", "d"];
```

#### splice()

两个参数 a b，删除操作，从 a 开始，删除 b 个元素，返回删除的元素

```
let ary = ["a", "b", "c", "d", "e"];
ary.splice(0, 2);
alert(ary);   // ["c", "d", "e"]
```

多个参数 a b c d，从 a 开始，删除 b 个元素，然后在 a 处插入 c d，返回删除的元素

当第二个参数为 0 时，不会删除元素，等价于插入操作

```
let ary = ["a", "b", "c", "d", "e"];
ary.splice(1, 1, "f", "g");
alert(ary);   // ["a", "f", "g", "c", "d", "e"]
```

### 搜索和位置方法

#### 严格相等

参数和数组中的匹配项必须满足全等（===）

##### indexOf()

从头开始找，返回索引值

##### lastIndexOf()

从尾部开始找，返回索引值

##### includes()

从头开始找，返回布尔值

#### 断言函数

##### find()

接收一个断言函数，当断言函数返回 true 时，方法 find() 返回找到的对象

断言函数参数：元素、索引值、数组

```
const people = [
  {
    name: "lin",
    age: 27
  },
  {
    name: "wang",
    age: 29
  }
]

people.find((element, index, array) => element.age < 28);
// {name: 'lin', age: 27}
```

##### findIndex()

接收一个断言函数，当断言函数返回 true 时，方法 findIndex() 返回索引值

接上例：

```
people.findIndex((element, index, array) => element.age < 28);
// 0
```

### 迭代方法

迭代方法参数：一个函数，一个对象（用于指定函参中 this 的值）。这个函数的参数：元素、索引值、数组

#### every()

数组中每一项作为参数传入函数，如果所有项返回的结果均为 true，那么 every() 返回 true

```
let num = [1, 2, 3, 4, 5, 6];
num.every((item, index, array) => item > 2);
// false
```

#### some()

数组中每一项作为参数传入函数，如果有一项返回的结果为 true，那么 some() 返回 true

```
let num = [1, 2, 3, 4, 5, 6];
num.some((item, index, array) => item > 2);
// true
```

#### filter()

过滤器，数组中每一项作为参数传入函数，所有结果为 true 的项，会组成一个数组成为 some() 的返回值

```
let num = [1, 2, 3, 4, 5, 6];
num.filter((item, index, array) => item > 2);
// [3, 4, 5, 6]
```

#### forEach()

相当于 for 循环遍历数组，在函数中对数组中的每一项进行操作，没有返回值

```
let num = [1, 2, 3, 4];
num.forEach((item, index, array) => array[index] = 0);
alert(num);
// [0, 0, 0, 0]
```

#### map()

在函数中对数组中的每一项进行操作，每次函数对 item 操作的结果会组成一个数组，作为 map() 的返回值

```
let num = [1, 2, 3, 4];
num.map((item, index, array) => item = 0);
// [0, 0, 0, 0]
```

### 归并方法

归并方法的参数：一个函数。函数的参数：上一个元素，当前元素，当前索引值，数组

#### reduce()

从头开始归并，如下进行数组的累加操作：

```
let vals = [1, 2, 3, 4];
vals.reduce((prev, curr, index, array) => prev + curr);
// 10
```

#### reduceRight()

从末尾开始归并，和 reduce() 的区别只在于归并方向相反

## 定型数组（TODO）

## Map（ES6）

Map，映射

Map 用于存储键值对：`[["key", "value"], ["key", "value"]... ]`

ES6 之前，使用 Object 存储键值对，所以 Map 的大多数特性都可以通过 Object 实现

### 创建

new Map() 构造函数创建 Map：

```
// 创建空 Map
const m = new Map();

// 使用嵌套数组初始化映射
const m = new Map([
  ["k1", "v1"],
  ["k2", "v2"],
  ["k3", "v3"]
]);

// 使用自定义迭代器初始化映射
const m = new Map({
  [Symbol.iterator]: function*(){
    yield ["k1", "v1"],
    yield ["k2", "v2"],
    yield ["k3", "v3"]
  }
});

// 映射期待的键值对，无论是否提供
const m = new Map([[]]);
alert(m.has(undefined));  // true
alert(m.get(undefined));  // undefined
```

### 增删改查

#### set()

接收两个字符串参数，作为新的键值对，返回值是新的 Map 对象，因此可以连续多个 set 操作

```
const m = new Map();
m.set("key1", "val1").set("key2", "val2");
```

#### has()

传入 key 参数，查询 Map 中是否有某个键值对，返回布尔值

#### get()

传入 key 参数，返回 Map 中 key 相匹配的 value

#### delete()

传入 key 参数，删除匹配的键值对，删除成功返回 true，删除失败返回 false

#### clear()

删除 Map 中所有键值对

#### size

Map 的属性，返回 Map 中键值对的个数

### 关于 key 的匹配性

Map 的键可以使用任何数据类型，Map 内部会使用 SameValueZero 比较（内部定义，语言中无法使用），基本相当于严格对象相等来检查键的匹配性，Map 的值也可以是任何数据类型

```
const functionKey = function() {};
const m = new Map();
m.set(functionKey, "val1");
m.get(function(){});    
// undefined
// 意味着使用 SameValueZero 比较 key，独立的对象实例不会冲突
```

如果 key 是集合或数组等引用类型，假如修改集合或数组内容，key 值不会改变，仍然可以访问到

SameValueZero 比较也会出现一些冲突：

```
const m = new Map();
const a = 0/"",
      b = 0/"",
      pz = +0,
      nz = -0;

alert(a === b);     // false
alert(pz === nz);   // true

m.set(a, "vala");
m.set(pz, "valpz");

alert(m.get(b));    // vala
alert(m.get(nz));   // valpz
```

关于 JS 中[相等性介绍](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Equality_comparisons_and_sameness)

### 顺序与迭代

Map 会维护键值对的插入顺序

Map 实例会提供一个迭代器，能以插入顺序生成 [key, value] 形式的数组，有两种方式获取这个迭代器：

#### entries()

```
const m = new Map([
  ["k1", "v1"],
  ["k2", "v2"],
  ["k3", "v3"]
]);

for(let pair of m.entries()){
  alert(pair);
}
// k1, v1
// k2, v2
// k3, v3
```

#### [Symbol.iterator]

```
for(let pair of m[Symbol.iterator]){
  alert(pair);
}
// k1, v1
// k2, v2
// k3, v3
```

#### keys()

并且 Map 实例还提供了 key 的迭代器：

```
for(let key of m.keys()){
  alert(key);
}
// k1
// k2
// k3
```

在对 m.keys() 的遍历中，无法修改 key 的值，但是，如果 key 时对象，那么可以修改对象内部的属性值

#### values()

以及 value 的迭代器：

```
for(let value of m.values()){
  alert(value);
}
// v1
// v2
// v3
```

#### forEach()

不使用迭代器？回调方式：

```
m.forEach((val, key) => alert(`${key} -> ${val}`));
// k1 -> v1
// k2 -> v2
// k3 -> v3
```

forEach() 接收两个参数，第一个参数是函数，第二个参数可选，是一个指定 this 值的对象

### Object VS. Map

1. 内存占用，Map WIN!
2. 插入性能，Map WIN!
3. 查找速度，Object WIN!
4. 删除性能，Map WIN!

## WeakMap（TODO）

弱映射，API 是 Map 的子集

### 与 Map 的区别

增删改查的方法和 Map() 一致

WeakMap 的 key，只允许是 Object 类型，或者继承自 Object，否则会抛出错误 TypeError

### 弱键（TODO）

WeakMap 的 key 的引用不属于正式的引用，这意味着 key 的引用不会阻止垃圾回收。但是 value 的引用是正式的引用。只要 key 存在，键值对就会存在于 WeakMap 中，因此就不会被当作垃圾回收

## Set

Set，集合，像是增强的 Map，并且大部分 API 是共有的

### 与 Map 的区别

Set 存储的不再是键值对，而是一个值（值就是键，键就是值）

增添方法不同于 Map 中的 set()，而是 add()，其他特性一致

Set 的迭代器没有 keys()，也有 entries()，不过 entries() 返回的是两个重复的值：`[value, value]`，其他迭代方式都一致

### 定义正式集合操作（TODO）

可以自定义关于 Set 的操作

## WeakSet（TODO）

# 7 迭代器与生成器（TODO）

# 8 面向对象

## 理解对象

可以将对象想象成一个列表，列表中的内容都是键值对，值可以是属性或函数

可以通过 new Object() 创建新的对象实例，也可以使用对象字面量（大括号）创建实例

### 属性的类型

ECMA-262 规定了一些 ***内部特性*** 来描述属性的特征，这些特性不能被开发者访问到，为了标识内部特性，采用 `[[Value]]` 的方式表示内部特性

属性可以分两类：数据属性、访问器属性

#### 数据属性

##### 内部特性

- [[Configurable]]：表示属性是否可以通过 delete 删除并重新定义，是否可以修改这个属性的特性，是否可以把属性改为访问器属性，默认情况，直接定义在对象上的属性的这个特性值都为 true
- [[Enumerable]]：表示属性是否可以通过 for-in 循环返回，默认情况，直接定义在对象上的属性的这个特性值都为 true
- [[Writable]]：表示属性的值是否可以被修改，默认情况，直接定义在对象上的属性的这个特性值都为 true
- [[Value]]：包含属性的值，默认是 undefined

例如：

```
let person = {
  name: "lin";
}
```

以上代码所创建的 name 属性，他的 [[Configurable]]、[[Enumerable]]、[[Writable]] 都为 true，而 [[Value]] 的值是 lin

##### delete 操作符

delete 运算符用于删除对象的一个属性；如果该属性的值是一个对象，并且没有更多对该对象的引用，该属性所持有的对象最终会自动释放。

```
const Employee = {
  firstname: 'Maria',
  lastname: 'Sanchez',
};

console.log(Employee.firstname);
// Expected output: "Maria"

delete Employee.firstname;

console.log(Employee.firstname);
// Expected output: undefined
```

##### 修改特性

使用 Object.defineProperty(obj, prop, define-obj)，包含三个参数：第一个 obj，是要修改的对象，第二个 prop 是对象中要修改的属性，第三个 define-obj 是一个对象，可以指定所有特性的值，对于没有指定的特性，默认为 false

```
let person = {};
Object.defineProperty(person, "name", {
  writable: false,
  value: "lin"
});
console.log(person.name); 
// lin
person.name = "Grey";
console.log(person.name);
// lin
```

#### 访问器属性

##### 内部特性

- [[Configurable]]：表示属性是否可以通过 delete 删除并重新定义，是否可以修改这个属性的特性，是否可以把属性改为访问器属性，默认情况，直接定义在对象上的属性的这个特性值都为 true
- [[Enumerable]]：表示属性是否可以通过 for-in 循环返回，默认情况，直接定义在对象上的属性的这个特性值都为 true
- [[Get]]：获取函数，读取属性时使用，默认 undefined
- [[Set]]：设置函数，写入属性时使用，默认 undefined

直接定义访问器属性:

```
const book = {
  // 下划线表示这个属性不想被外界访问，属于私有属性，有的约定在属性前加入下划线，有的在属性前加入双下划线，这些方式都可以
  year_: 2017,
  edition: 1,

  get year() {
    return this.year_;
  },
  set year(newVal) {
    if(newVal > 2017) {
      this.year_ = newVal;
      this.edition += newVal - 2017;
    }
  }
};

book.year = 2018;
alert(book.edition);  // 2
```

通过 Object.defineProperty() 定义：

```
let book = {
  // 下划线表示这个属性不想被外界访问，属于私有属性
  year_: 2017,
  edition: 1
};

// 添加一个新属性 year，用于外界操作私有属性 year_
Object.defineProperty(book, "year", {
  // 设置 get 方法来访问私有属性
  get() {
    return this.year_;
  },
  // 设置给 year 赋值时的操作
  set(newVal) {
    if(newVal > 2017) {
      this.year_ = newVal;
      this.edition += newVal - 2017;
    }
  }
});

book.year = 2018;
alert(book.edition);  // 2
```

可以看出，访问器的使用场景，即设置一个属性时同时发生其他的变化

只定义 get 函数，则属性无法被修改，只定义 set 方法，非严格模式访问属性会返回 undefined，严格模式会报错

### 定义多个属性

Object.defineProperties()

```
let book = {};
Object.defineProperties(book, {

  year_: {
    value: 2017
  },

  edition: {
    value: 1
  },

  year: {
    get() {
      return this.year_;
    },
    set(newVal) {
      if(newVal > 2017) {
        this.year_ = newVal;
        this.edition += newVal - 2017;
      }
    }
  }
});
```

这段代码和上一段示例是一样的

### 读取属性的特性

Object.getOwnPropertyDescriptor()

接上面的代码：

```
let descriptor = Object.getOwnPropertyDescriptor(book, "year_");
alert(descriptor.value);    // 2017
alert(typeof descriptor.get);     // undefined
alert(descriptor.configurable);   // false

let descriptor = Object.getOwnPropertyDescriptor(book, "year");
alert(typeof descriptor.get);    // function
```

Object.getOwnPropertyDescriptors()

```
let descriptor = Object.getOwnPropertyDescriptors(book);
console.log(descriptor);

/** 
返回值：
{
  edition: {
    configurable: false,
    enumerable: false,
    value: 1,
    writable: false
  },
  year: {
    configurable: false,
    enumerable: false,
    get: f(),
    set: f(newVal)
  },
  year_: {
    configurable: false,
    enumerable: false,
    value: 2017,
    writable: false
  }
}
 */
```

### 合并对象（ES6）

合并（merge）操作有时也被称为混入（mixin）

Object.assign()，第一个参数是目标对象，之后可以有一个或多个对象参数，作为要合并的源对象。会将每个源对象中的所有 ***可枚举***（可以 for-in 遍历） 和 ***自有***（非继承属性） 属性复制到目标对象。这个方法会使用源对象的 [[Get]] 获取属性的值，使用目标对象的 [[Set]] 设置属性的值

```
let dest, src, result;

dest = {};
src = { id: 'src'};

result = Object.assign(dest, src);

alert(dest === result);   // true
alert(dest !== src);      // true
```

特点：

- 如果多个源对象有重复的属性，那么会使用最后一个对象的属性值
- Object.assign() 采用的是浅拷贝，即拷贝的属性值如果是引用值（对象），那么源对象和目标对象的这个属性会同时共用这个属性值
- 两个对象之间不能转移 [[Get]] 和 [[Set]] 函数
- 对于多个源对象合并，如果合并期间某一个对象的某个属性报错，会终止赋值，并且不会回滚，即已经合并的内容会保留

### is()（ES6）

ES6 之前，特殊情况下，=== 的结果很混乱：比如，`+0 === -0` 的结果是 true，或者判断 `NaN === NaN` 的结果是 false

因此 ES6 新增 Object.is()，这个方法解决了上述的问题：

```
Object.is(-0, +0);  // false
Object.is(0, +0);   // true
Object.is(-0, 0);   // false

Object.is(NaN, NaN);  // true
```

检查多个值是否相等（递归）：

```
function checkEqual(x, ...rest) {
  return Object.is(x, rest[0]) && (rest.length < 2 || checkEqual(...rest))
}
```

### 语法糖（ES6）

#### 属性值简写

```
function a(name) {
  return {
    name: name
  };
}
```

语法糖：

```
function a(name) {
  return {
    name
  };
}
```

#### 可计算属性

以下代码尝试将变量作为属性的名称，然后给这个属性赋值：

```
const nameKey = 'name';
let person = {};
person[nameKey] = 'lin';
```

语法糖：

```
const nameKey = 'name';
let person = {
  [nameKey]: 'lin'
};
```

值得注意的是，如果在变量赋值过程中报错（由于属性名是变量，导致这种情况可能会发生），无法回滚

#### 简写方法名

给对象添加一个属性，并且它的值是一个匿名函数：

```
let person = {
  printName: function(name) {
    console.log(name);
  }
}
```

语法糖：

```
let person = {
  printName(name) {
    console.log(name);
  }
}
```

### 对象解构（ES6）

```
let person = {
  name: 'lin',
  age: 23
}
let pName = person.name;
let pAge = person.age;
```

使用结构：

```
let person = {
  name: 'lin',
  age: 23
}
let { name: pName, age: pAge } = person;
```

简写：

```
let { name, age } = person;
console.log(name);  // lin
console.log(age);   // 23
```

如果解构时某个属性不存在，那么其值为 undefined，当然，也可以给可能不存在的属性设置一个默认值：

```
let {name, job='Student'} = person;
console.log(job);  // Student
```

解构时，会使用内部函数 ToObject() （不能再运行时环境访问）把源数据转换为对象，因此 null 和 undefined 不能被解构，会报错

```
// ToObject() 会将字符串字面量转换成 String 对象类型
let { length } = 'lin';
console.log(length);    // 3

// ToObject() 会将数值转换成 Number 对象类型
let { constructor } = 5;
console.log(constructor === Number); // true
```

如果解构的变量已经事先定义了，那么要用括号包裹表达式：

```
let name,age;
let person = {
  name: 'lin',
  age: 23
};

({ name, age } = person);
```

#### 复制对象

```
let person = {
  name: 'lin',
  job: {
    title: 'Student'
  }
};
let copy = {};
({ name: copy.name, job: copy.job } = person);
```

以上代码通过解构对对象进行复制，但是这种复制属于浅拷贝，即如果修改 person.job.title，那么 copy.job.title 会同时被修改，因为它们指向同一个引用值

#### 嵌套解构

```
let person = {
  name: 'lin',
  job: {
    title: 'Student'
  }
};
// 先对 person 解构，然后再对 job 解构，最终获取 title 的值
let { job: { title } } = person;
// 等价于：
let { job: { title: title } } = person;

console.log(title);   // Student
```

#### 部分解构

如果解构的属性没有定义，那么不能在这个属性上使用嵌套解构，会报错

当报错时，终止解构，并且不会回滚，所以只会有部分解构成功

#### 参数解构

在函数的参数中也可以进行解构，并且不会影响 arguments 对象

```
let person = {
  name: 'lin',
  age: 23
};

function print(a, { name, age }, b) {
  console.log(arguments);
  console.log(name, age);
}

print(1, person, 2);
// [1, { name: lin, age: 23 }, 2]
// lin 23
```

## 创建对象

### 工厂模式

一种设计模式，是用于抽象创建特定对象的过程

```
function createPerson(name, age, job) {
  let o = new Object();
  o.name = name;
  o.age = age;
  o.job = job;
  return o;
}

let person = createPerson("lin", 23, "Student");
```

这种模式解决了创建多个类似对象的问题，但是无法判断创建的对象是什么类型，因为所有的对象都是 Object 类型

### 构造函数模式

几种用构造函数创建对象的方式：

```
function Person(name, age, job) {
  this.name = name;
  this.age = age;
  this.job = job;
}

let person = new Person("lin", 23, "Student");
```

等价于：

```
let Person = function (name, age, job) {
  this.name = name;
  this.age = age;
  this.job = job;
}

let person = new Person("lin", 23, "Student");
```

无参构造函数：

```
function Person() {
  this.name = "lin";
  this.age = 23;
  this.job = "Student";
}

let person = new Person();
```

#### 构造函数模式与工厂模式的区别

- 没有显示创建对象
- 属性和方法赋值给 this（this 是方法的调用者，即 person 实例）
- 没有 return

#### 使用 new 操作符调用构造函数流程

1. 在内存中创建一个新对象
2. 将构造函数的 prototype 属性赋值给这个新对象的 [[prototype]] 特性
3. 构造函数中的 this 被值为这个新对象
4. 执行构造函数中的代码
5. 如果构造函数返回非空对象，则返回该对象，否则返回这个新对象

#### 构造函数可以区别对象类型

如果再执行 `console.log(person.constructor)` 可以发现 person 继承了 Object 的 constructor 属性，并且打印的内容正是 Person 的构造函数，并且无论创建多少个 Person 实例，它们的 constructor 都指向同一个构造函数

```
alert(person instanceof Object);  // true
alert(person instanceof Person);  // true
```

根据以上代码可以看出，person 既是 Object 的实例，又是 Person 的实例，因为自定义对象都继承自 Object

#### 构造函数也是函数

构造函数和普通函数的区别仅在于调用方式：构造函数通过 new 操作符创建，普通函数直接创建

```
function Person() {
  this.name = "lin";
  this.age = 23;
  this.job = "Student";
  this.sayName = function(){
    alert(this.name);
  }
}

let person = new Person("lin", 23, "Student");
person.sayName()

Person("lin", 23, "Student");
window.sayName()

let o = new Object();
Person.call(o, "lin", 23, "Student");
o.sayName();
```

以上代码有三种调用方式：

- new 操作符调用构造函数，这时的调用者（this 指向）是 person 实例
- 直接调用构造函数，并且没有指定 this，这时 this 始终指向 Global（window）对象实例
- 使用 call 指定 this 的值为实例 o

#### 构造函数的问题

构造函数中的 function 会重复创建，即不同的实例虽然都有构造函数中定义的方法（如上文中的 sayName()），但是这些 function 不属于同一个 Function 实例

上文的 Person 构造函数等价于：

```
function Person() {
  this.name = "lin";
  this.age = 23;
  this.job = "Student";
  // 这里相当于创建一个新的 Function 实例
  this.sayName = new Function("alert(this.name)");
}

let person1 = new Person("lin", 23, "Student");
let person2 = new Person("wang", 22, "Student");

alert(person1.sayName == person2.sayName);  // false
```

没有必要为每一个 Person 实例定义不同的 Function 实例，因此可以把函数转移到构造函数外：

```
function Person() {
  this.name = "lin";
  this.age = 23;
  this.job = "Student";
  // 这里的 sayName 是一个指向外部方法的指针
  this.sayName = sayName;
}

function sayName(){
  alert(this.name);
}
```

这样，可以让每个 Person 实例都公用一个方法，因为这个方法是定义咋 window 上的，但这样会导致自定义类型引用的函数不能很好的聚集再一起，所有自定义类型的方法都会创建在 window 对象上，十分混乱，这个问题可以通过原型模式解决

### 原型模式

每个函数都会创建一个 prototype 属性，这个属性是一个对象，包含当前引用类型的实例共享的属性和方法，可以将属性和方法赋值到 构造函数的 prototype 上：

```
function Person() {}

Person.prototype.name = "lin";
Person.prototype.age = 23;
Person.prototype.job = "Student";
Person.prototype.sayName = function(){
  alert(this.name);
}

let person1 = new Person("lin", 23, "Student");
let person2 = new Person("wang", 22, "Student");

alert(person1.sayName == person2.sayName);  // true
```

可以看出，person1 和 person2 的 sayName 函数是同一个实例

#### 理解原型

定义构造函数时，会自动创建一个 prototype 属性，指向这个函数的原型对象，原型对象有一个 constructor 属性，又指向构造函数，在之前的例子中，Person.prototype.constructor 指回 Person，即构造函数和原型对象是循环调用的关系：

```
alert(Person.prototype.constructor);   // Person
```

原型对象：自定义构造函数时自动创建，只默认获取 constructor 属性，其他属性继承自 Object

实例创建时，实例内部特性 [[Prototype]] 指针指向构造函数的原型对象，但是内部特性开发者无法访问，可以通过浏览器供应商实现的 `__proto__` 属性访问原型对象：

```
// Person 的原型对象的原型对象就是 Object 的原型对象
alert(Person.prototype.__proto__ === Object.prototype);   // true
```

`__proto__` 和 prototype 区别：

- 构造函数通过 prototype 链接到原型对象
- 实例通过 `__proto__` （ [[Prototype]] ）链接到原型对象

Object 的原型对象为 null，因为 Object 位于原型链的最顶层：

```
// Person 的原型链最后终止于 Object 的原型对象
alert(Person.prototype.__proto__.__proto__ === null);   // true
```

关键：构造函数、原型对象、实例是 3 个完全不同的对象，实例和其构造函数中都有相应的属性（ `__proto__` 和 prototype ）指向构造函数的原型对象，而实例和构造函数之间没有关系，但是实例仍然可以以  `person1.sayName()` 的方式调用构造函数原型对象的函数，这是由于对象属性查找机制的原因

#### 原型方法

##### isPrototypeOf()

判断对象的原型类型（如果参数对象的原型对象是调用者时返回 true）：

```
console.log(Person.prototype.isPrototypeOf(person1));   // true
```

##### Object.getPrototypeOf()

返回参数内部特性 [[Prototype]] 的值，即原型对象

##### Object.setPrototypeOf()

给参数对象的原型对象增加属性

```
// 给 Person 的原型对象新增一个 numLeges: 2 属性
Object.setPrototype(person, {numLegs: 2});
```

这种方式有很大的隐患，因为这样会修改所有访问这个对象的代码，十分影响性能，可以通过 Object.create() 创建新对象，同时指定其原型对象：

```
let person = Object.create({numLegs: 2});
```

#### 原型层级

通过对象访问属性时，会先从实例本身开始搜索这个属性，如果没有，再从对象的原型对象中搜索这个属性

```
function Person() {}

Person.prototype.name = "lin";
Person.prototype.age = 23;
Person.prototype.job = "Student";
Person.prototype.sayName = function(){
  alert(this.name);
}

let person1 = new Person();
let person2 = new Person();

person1.name = "li";
alert(person1.name);  // li 属性值来自实例
alert(person1.name);  // lin 属性值来自于原型
```

属性遮蔽（shadow）：给对象添加一个属性，这个属性会覆盖原型对象中的同名属性，注意不会修改原型的属性，只是屏蔽对它的访问

如何解除属性遮蔽？即使将对象属性的值设为 null，原型属性也会被遮蔽，可以使用 delete 删除对象属性，这样便可以解除对原型属性的屏蔽

接上文代码：

```
delete person1.name;
alert(person1.name);  // lin
```

##### hasOwnProperty()

用于确定属性是在实例上还是在原型对象上，如果参数中的属性在调用它的实例上，返回 true

接上文代码：

```
alert(person1.hasOwnProperty("name"));  // false

person1.name = "wang";
alert(person1.hasOwnProperty("name"));  // true
```

可以看出，只有实例属性遮蔽原型属性时会返回 true

#### 原型和 in

单独使用 in 操作符可以判断某个属性是否在对象上，无论在实例上还是在原型对象上都返回 true

接上文代码：

```
alert("name" in person1);   // true
```

如果要判断某个属性是否是原型对象的属性，可以将 in 和 hasOwnProperty() 配合使用：

接上文代码：

```
// 如果属性不是实例属性且这个属性存在，那么它就是原型对象的属性
alert(!person1.hasOwnProperty("name") && ("name" in person1));  // false
```

#### 属性枚举

for-in 循环可以返回可枚举的所有属性，包括实例属性和原型属性

```
function Person() {}

Person.prototype.name = "lin";
Person.prototype.age = 23;
Person.prototype.job = "Student";
Person.prototype.sayName = function(){
  alert(this.name);
}

let person1 = new Person();
person1.gender = "male";
person1.name = "wang";
for(let prop in person1){
  console.log(prop);
}
// gender
// name
// age
// job
// sayName
```

Object.keys() 可以返回所有可枚举的实例属性

```
console.log(Object.keys(person1));  // ['gender', 'name']
```

Object.getOwnPropertyNames() 可以返回所有实例属性，无论是否可以枚举

```
console.log(Object.getOwnPropertyNames(person1.__proto__));
// ['constructor', 'name', 'age', 'job', 'sayName']
```

Object.getOwnPropertySymbols() 可以返回所有以 Symbol 类型为属性名的属性

```
let k1 = Symbol('k1');
let k2 = Symbol('k2');

let obj = {
  [k1]: 'k1',
  [k2]: 'k2'
}

console.log(Object.getOwnPropertySymbols(obj));
// [Symbol(k1), Symbol(k2)]
```

##### 属性枚举顺序

for-in 和 Object.keys() 枚举顺序不确定，取决于浏览器

Object.getOwnPropertyNames() 和 Object.getOwnPropertySymbols() 以及 Object.assign() 的枚举顺序确定：先升序枚举所有 Number 类型的属性名，再以插入顺序枚举 String 和 Symbol 属性名

### 对象迭代

#### Object.entries()

参数是一个对象，方法会以键值对的形式返回所有的属性和属性值，不包括 Symbol 属性，执行的是浅拷贝

```
let o = {
  name: "lin",
  gender: "male"
}

console.log(Object.entries(o));
// [['name', 'lin'], ['gender', 'male']]
```

#### Object.values()

和 Object.keys() 是兄弟方法，返回所有的属性值，不包括 Symbol 属性，执行的是浅拷贝

```
console.log(Object.values(o));
// ['lin', 'male']
```

### 补充

#### 创建原型对象

在之前的方式中，定义原型是这样的：

```
function Person() {}

Person.prototype.name = "lin";
Person.prototype.age = 23;
Person.prototype.job = "Student";
Person.prototype.sayName = function(){
  alert(this.name);
}
```

可以进行简化：

```
function Person() {}

Person.prototype = {
  name = "lin",
  age = 23,
  job = "Student",
  sayName = function(){
    alert(this.name);
  }
}
```

这样重写之后，Person.prototype.constructor 不再指向 Person，而是指向 Object 构造函数，虽然仍然可以通过 instanceof 判断实例是否属于 Person 对象，但是无法使用 constructor 判断实例的对象类型了，如果 constructor 很重要可以这样重写：

```
function Person() {}

Person.prototype = {
  constructor: Person,
  name = "lin",
  age = 23,
  job = "Student",
  sayName = function(){
    alert(this.name);
  }
}
```

但是，这样还有缺陷，由于开发者创建的属性默认是可枚举的，这个手动添加 constructor 会被认为是可枚举类型的属性，为了让这个 constructor 是默认的不可枚举类型属性，可以这样重写：

```
function Person() {}

Person.prototype = {
  name = "lin",
  age = 23,
  job = "Student",
  sayName = function(){
    alert(this.name);
  }
}

Object.defineProperty(Person.prototype, 'constructor', {
  enumerable: false,
  value: Person
})
```

#### 原型的动态性

即使修改原型对象时，实例已经存在，这时对原型对象的修改也会反映在实例上：

```
let man = new Person();

Person.prototype.sayHi = function () {
  console.log("hi");
}

man.sayHi();  // hi
```

这是因为实例与原型之间的联系：实例中的 [[Prototype]] (即 `__proto__`) 的值是一个指针，指向原型对象，因此，当尝试通过实例调用 sayHi() 方法时，实例会先尝试在实例中搜寻 sayHi()，没有找到，会按照 [[Prototype]] 的指针值找到原型对象，再从原型对象中搜索 sayHi()，找到之后进行调用

但是，如果重写整个原型对象，会切断实例与原型对象的联系，这样无法通过实例调用新创建的方法：

```
let man = new Person();

Person.prototype = {
  constructor: Person,
  sayHi() {
    console.log("hi");
}
}

man.sayHi();  // Error
```

这是因为当给 Person.prototype 赋一个新值后，Person 构造函数会的 prototype 属性会指向新原型对象，但是已经创建的实例 man 的 `__proto__` 仍然指向旧原型对象，因此实例搜索不到要调用的 sayHi() 方法

要想调用 sayHi() 方法，需要再重写原型对象后新建一个实例，再通过这个实例调用方法

#### 原生对象原型

原生对象的构造函数（String、Array、Object 等）都在其原型对象上定义了方法，比如 String 对象的 substring()，所有字符串实例都可以调用这个方法，这也是采用原型模式的优势

开发者可以在原生对象的原型上添加新的方法，这种方式添加的方法可以在当前环境中所有的实例使用。但是不推荐这种做法，因为可能引发命名冲突，也有可能意外重写原生方法。推荐做法是创建一个自定义类，继承原生类型

#### 原型的问题

因为原型可以为属性设置默认值，它弱化了向构造函数传递初始化参数的能力

当原型对象属性的属性值是一个引用值时，如果一个实例对这个引用值进行修改，会导致其他所有实例的属性值也会被修改，一般来说，不同实例应该有属于自己的属性副本，所以实际开发中不单独使用原型模式

## 继承

其他面向对象语言支持两种继承：implements 和 extends，即接口继承和实施继承，前者是继承一个标签，后者是继承一个方法（类）

在 ECMAscript 中只有实施继承，通过原型链实现

### 原型链

