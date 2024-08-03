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
      - [数值转换（TODO）](#数值转换todo)
    - [string](#string)
      - [字符串字面量](#字符串字面量)
      - [不可变](#不可变)
      - [字符串转换](#字符串转换)
      - [模板-字面量](#模板-字面量)
      - [模板-插值](#模板-插值)
      - [模板-标签函数](#模板-标签函数)
      - [模板-原始字符串](#模板-原始字符串)
    - [symbol](#symbol)

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
console.log(a + b == 0.3); //结果为 false
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

#### 数值转换（TODO）

Number()，转换任何类型，规则复杂

parseInt()，只能转换整数，可以接受两个参数：转换对象，进制

parseFloat()，只能解析十进制数，如果参数为整数，则会返回整数

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

#### 模板-字面量

模板字面量会保存反引号之间的所有空格、换行

```
//以下两个字符串是等价的
let string = 'first line\nsecond line';
//使用字符串模板
let template = `first line
second line`;
```

#### 模板-插值

可以在模板字面量中通过插值的方式，使用变量，变量会被 toString() 转换为字符串

- 插值中，可以使用变量对象的函数
- 插值中，可以对多个变量进行运算

```
let val = 5;
let template = `value is ${val}`
```

#### 模板-标签函数

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
//["", " + ", " = ", ""]
//6
//9
//15

console.log(result); //"result"
```

函数参数 strings 接受的是原始字符串数组，...expressions（数组）接受了其他插值的结果

可以自定义插值的行为

#### 模板-原始字符串

可以获取模板字面量的原始内容：

```
String.raw`first line\nsecond line`;
//first line\nsecond line
```

### symbol

