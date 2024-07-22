- [资源链接](#资源链接)
- [1 CSS 介绍](#1-css-介绍)
  - [引入方式](#引入方式)
  - [运行流程](#运行流程)
  - [CSS 兼容](#css-兼容)
  - [注释](#注释)
- [2 CSS 选择器](#2-css-选择器)
  - [选择器列表（选择器并集）](#选择器列表选择器并集)
  - [选择器交集](#选择器交集)
  - [基础选择器](#基础选择器)
    - [类型选择器](#类型选择器)
    - [全局选择器](#全局选择器)
    - [class 选择器](#class-选择器)
    - [id 选择器](#id-选择器)
  - [属性选择器](#属性选择器)
    - [根据存在和值选择](#根据存在和值选择)
      - [\[attr\]](#attr)
      - [\[attr=value\]](#attrvalue)
      - [\[attr~=value\]](#attrvalue-1)
      - [\[attr|=value\]](#attrvalue-2)
    - [根据子字符串匹配选择](#根据子字符串匹配选择)
      - [\[attr^=value\]](#attrvalue-3)
      - [\[attr$=value\]](#attrvalue-4)
      - [\[attr\*=value\]](#attrvalue-5)
      - [属性值大小写敏感](#属性值大小写敏感)
  - [伪类和伪元素](#伪类和伪元素)
    - [简单伪类](#简单伪类)
      - [:first-child](#first-child)
      - [:last-child](#last-child)
      - [:nth-child()](#nth-child)
      - [:only-child](#only-child)
      - [:is()](#is)
      - [:where()](#where)
      - [:not()](#not)
    - [用户行为伪类](#用户行为伪类)
      - [:hover](#hover)
      - [:focus](#focus)
      - [:invalid](#invalid)
    - [伪元素](#伪元素)
      - [::first-line](#first-line)
      - [::before](#before)
      - [::after](#after)
  - [关系选择器](#关系选择器)
    - [后代选择器](#后代选择器)
    - [子代选择器](#子代选择器)
    - [临接兄弟选择器](#临接兄弟选择器)
    - [通用兄弟选择器](#通用兄弟选择器)
- [4 CSS 优先权](#4-css-优先权)
  - [CSS 层叠](#css-层叠)
  - [样式来源](#样式来源)
  - [层叠层（级联层）](#层叠层级联层)
    - [创建层叠层](#创建层叠层)
      - [@layer 声明方式](#layer-声明方式)
      - [@layer 块方式](#layer-块方式)
      - [使用 @import 将样式表导入层](#使用-import-将样式表导入层)
    - [嵌套层](#嵌套层)
      - [创建嵌套层](#创建嵌套层)
    - [如何确定优先权](#如何确定优先权)
      - [常规层叠层的优先权顺序](#常规层叠层的优先权顺序)
      - [嵌套层叠层的优先权顺序](#嵌套层叠层的优先权顺序)
  - [选择器优先级](#选择器优先级)
- [5 CSS 继承](#5-css-继承)
  - [控制继承](#控制继承)
  - [重设所有属性值](#重设所有属性值)
- [6 盒模型](#6-盒模型)
  - [外部显示类型](#外部显示类型)
    - [区块盒子 (block)](#区块盒子-block)
    - [行内盒子 (inline)](#行内盒子-inline)
    - [行内块 (inline-block)](#行内块-inline-block)
  - [内部显示类型](#内部显示类型)
  - [盒模型](#盒模型)
    - [标准盒模型](#标准盒模型)
    - [替代盒模型](#替代盒模型)
    - [外边距](#外边距)
      - [相关属性](#相关属性)
      - [外边距折叠](#外边距折叠)
    - [边框](#边框)
    - [内边距](#内边距)
- [7 CSS 样式](#7-css-样式)
  - [背景](#背景)
    - [背景颜色](#背景颜色)
    - [背景图像](#背景图像)
    - [控制背景平铺行为](#控制背景平铺行为)
    - [背景图像大小](#背景图像大小)
    - [背景图像定位](#背景图像定位)
    - [渐变背景](#渐变背景)
    - [多个背景图像](#多个背景图像)
    - [背景滚动方式](#背景滚动方式)
    - [简写属性](#简写属性)
    - [无障碍考虑](#无障碍考虑)
  - [边框](#边框-1)
    - [简写属性](#简写属性-1)
    - [边框圆角](#边框圆角)
  - [不同方向的文本](#不同方向的文本)
    - [书写模式](#书写模式)
    - [逻辑属性和逻辑值](#逻辑属性和逻辑值)
      - [内联尺寸和块级尺寸](#内联尺寸和块级尺寸)
      - [其他逻辑属性](#其他逻辑属性)
      - [逻辑值](#逻辑值)
      - [物理属性还是逻辑属性？](#物理属性还是逻辑属性)
  - [图像和视频](#图像和视频)
    - [可替换元素](#可替换元素)
    - [调整大小](#调整大小)
    - [布局中的替换元素](#布局中的替换元素)
  - [表单](#表单)
    - [表单元素默认不继承](#表单元素默认不继承)
    - [重置表单样式](#重置表单样式)
  - [表格](#表格)
    - [固定列宽](#固定列宽)
    - [消除单元格边框之间的空隙](#消除单元格边框之间的空隙)
    - [单元格条纹效果](#单元格条纹效果)
    - [标题位置](#标题位置)
  - [盒子阴影](#盒子阴影)
    - [简单阴影](#简单阴影)
    - [多个阴影](#多个阴影)
    - [内部阴影](#内部阴影)
  - [滤镜](#滤镜)
  - [混合模式](#混合模式)
    - [background-blend-mode](#background-blend-mode)
    - [mix-blend-mode](#mix-blend-mode)
    - [text-clip](#text-clip)
  - [字体](#字体)
    - [字体样式](#字体样式)
      - [字体颜色](#字体颜色)
      - [字体种类](#字体种类)
        - [网页安全字体](#网页安全字体)
        - [默认字体](#默认字体)
        - [字体栈](#字体栈)
      - [字体大小](#字体大小)
      - [字体样式](#字体样式-1)
      - [字体粗细](#字体粗细)
      - [文本转换](#文本转换)
      - [文本装饰](#文本装饰)
      - [文字阴影](#文字阴影)
    - [文本布局](#文本布局)
      - [文本对齐](#文本对齐)
      - [行高](#行高)
      - [字母和单词间距](#字母和单词间距)
    - [字体简写](#字体简写)
  - [列表](#列表)
- [8 CSS 溢出](#8-css-溢出)
  - [overflow 属性](#overflow-属性)
  - [溢出会建立区块格式化上下文](#溢出会建立区块格式化上下文)
- [9 CSS 的值与单位](#9-css-的值与单位)
  - [长度单位](#长度单位)
    - [绝对长度](#绝对长度)
    - [相对长度](#相对长度)
    - [百分比](#百分比)
  - [颜色值](#颜色值)
    - [RGB 和 RGBA](#rgb-和-rgba)
    - [十六进制](#十六进制)
    - [HSL 和 HSLA](#hsl-和-hsla)
  - [calc() 函数](#calc-函数)
- [10 CSS 调整元素尺寸](#10-css-调整元素尺寸)
  - [固有尺寸](#固有尺寸)
  - [设置具体的尺寸](#设置具体的尺寸)
    - [min- 和 max- 前缀的属性](#min--和-max--前缀的属性)
- [11 CSS 前缀](#11-css-前缀)
# 资源链接

- [MDN 官方教程](https://developer.mozilla.org/zh-CN/docs/Web/CSS)
- [渐变背景在线生成](https://cssgradient.io/)
- [codepen 在线编码](https://codepen.io/)
# 1 CSS 介绍

CSS (Cascading Style Sheets)，层叠样式表

```
h1 {
  color: red;
  font-size: 5em;
}
```

包含四部分：选择器、大括号、属性名、属性值

## 引入方式

1. 外部样式表，通过 \<head> 标签中的 \<link> 标签引入，推荐使用
2. 内部样式表，通过 \<head> 标签中的 \<style> 标签引入
3. 内联样式表，写在 html 元素的属性中，尽可能避免使用
```
<h1 style="color: blue;background-color: yellow;border: 1px solid black;">
Hello World!
</h1>
```
    
## 运行流程

加载 HTML ==> 解析 HTML ==> 生成 DOM 树 ==> 根据 HTML 加载解析 CSS 并渲染到 DOM ==> 着色

图解[css运行流程](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/First_steps/How_CSS_works/rendering.svg)

DOM（Document Object Model），文件对象模型，DOM 是文件在计算机内存中的表现形式

## CSS 兼容

CSS 由 W3C (万维网联盟) 中的一个名叫 CSS Working Group 团体发展起来的，浏览器并不会同时实现所有的新 CSS，当浏览器遇到无法解析的 CSS 选择器或声明的时候，会选择什么也不会做，继续解析下一个 CSS 样式

```
.box {
  width: 500px;
  width: calc(100% - 50px);
}
```

如上代码，兼容了不支持 calc() 函数的浏览器

## 注释

```
/* 注释 */
```

# 2 CSS 选择器

## 选择器列表（选择器并集）

```
h1,
.special {
  color: blue;
}
```

- 多个选择器用逗号分隔，为多个标签赋予相同的属性
- 如果其中任何一个选择器无效 (存在语法错误)，那么整条规则都会被忽略

## 选择器交集

```
/* 选择元素类型为 a，class 为 title 的元素 */

a.title { color:red }
```

## 基础选择器

### 类型选择器

也叫做标签名选择器或者是元素选择器，根据标签名称选择

```
span {
  background-color: yellow;
}
```

### 全局选择器

选中了文档中的所有内容（或者是父元素中的所有内容，比如，它紧随在其他元素以及邻代运算符之后的时候）

```
* {
  margin: 0;
}
```

使用全局选择器，让选择器更易读，如下面的例子，选取 \<article> 下所有标签中的第一个元素（其实 * 是可以省略掉的，为了可读性最好写上）

```
article *:first-child {
  ......
}
```

### class 选择器

根据标签的 class 属性值选择标签

```
.highlight {
  background-color: yellow;
}
```

多个 class 指向同一个元素时，两个选择器直接相连（不需要空格），如下面的例子，表示选择同时有 notebox 和 warning 两个 class 的元素

```
.notebox.warning {
  border-color: orange;
  font-weight: bold;
}
```

### id 选择器

根据标签的 id 属性值选择标签

```
#one {
  background-color: yellow;
}
```

ID 所指特定，会优先于大多数其他选择器，所以很难处理它们。大多数情况下，给一个元素加个 class，而不是使用 ID，会更好

## 属性选择器

### 根据存在和值选择

#### [attr]

匹配带有指定属性（方括号中的值）的元素，如下，表示选择类型为 li 且带有 class 属性的元素

```
<li class="anyvalue">Item 2</li>

li[class] {
  font-size: 200%;
}
```

#### [attr=value]

匹配带有指定属性（方括号中的值）的元素，且属性值为指定值（引号中的值），如下，表示选择类型为 li 、有 class 属性、属性值为 a 的元素

```
<li class="a">Item 2</li>

li[class="a"] {
  background-color: yellow;
}
```

#### [attr~=value]

匹配带有指定属性（方括号中的值）的元素，且属性值中 ***至少有一个*** 为指定值（引号中的不同属性值用空格分隔），如下，表示选择类型为 li 、有 class 属性、属性值中 ***至少有一个*** 为 a 的元素

```
<li class="bc a d">Item 2</li>

li[class~="a"] {
  color: red;
}
```

#### [attr|=value]

匹配带有指定属性（方括号中的值）的元素，且属性值中 ***第一个值*** 为指定值（引号中的不同值用连字符分隔），如下，表示选择类型为 li 、有 class 属性、属性值中 ***第一个值*** 为 a 的元素 ***（第一个值后必须紧接着一个连字符 - ，或者只有这一个值）***

```
<li class="a-b-c">Item 2</li>
<li class="a">Item 2</li>

li[class|="a"] {
  color: red;
}
```

### 根据子字符串匹配选择

#### [attr^=value]

匹配带有指定属性（方括号中的值）的元素，且属性值的 ***开头*** 为指定值（引号中的值），如下，表示选择类型为 li 、有 class 属性、属性值的 ***开头*** 为 a 的元素 

```
<li class="abc">Item 1</li>

li[class^="a"] {
  font-size: 200%;
}
```

#### [attr$=value]

匹配带有指定属性（方括号中的值）的元素，且属性值的 ***结尾*** 为指定值（引号中的值），如下，表示选择类型为 li 、有 class 属性、属性值的 ***结尾*** 为 a 的元素 

```
<li class="cba">Item 1</li>

li[class$="a"] {
  background-color: yellow;
}
```

#### [attr*=value]

匹配带有指定属性（方括号中的值）的元素，且属性值中 ***至少有一处*** 为指定值（引号中的值），如下，表示选择类型为 li 、有 class 属性、属性值中 ***至少有一处*** 为 a 的元素 

```
<li class="bac">Item 1</li>

li[class*="a"] {
  color: red;
}
```

#### 属性值大小写敏感

设置要匹配的属性值大小写不敏感，i 标记

```
<li class="Abc">Item 1</li>

li[class^="a" i] {
  color: red;
}
```

## 伪类和伪元素

伪类是选择器的一种，它用于选择处于特定状态的元素

伪元素表现得像往标记文本中加入全新的 HTML 元素一样，而不是向现有的元素上应用类

### 简单伪类

#### :first-child

选择一组兄弟元素中的第一个，如下，选择类型为 article 元素之下、既是父元素的第一个子元素也是 p 类型的元素

```
article p:first-child {
  font-size: 120%;
  font-weight: bold;
}
```

#### :last-child

选择一组兄弟元素中的最后一个，如下，选择类型为 article 元素之下、既是父元素的最后一个元素也是 p 类型的元素

```
article p:last-child {
  font-size: 120%;
  font-weight: bold;
}
```

#### :nth-child()

根据元素在父元素的子元素列表中的索引 ***（从1开始）*** 来选择元素

- 关键字值：even（偶数）或 odd（奇数）

```
li:nth-child(even) {
  background-color: lightyellow;
}
```

- 函数符号：An+B ，其中 A B 为自定义的常数值，n 是从 0 开始不断递增的整数

```
/* 选取前 3个 class 为 important 且类型为 li 的元素 */

li.important:nth-child(-n + 3)

/* 兄弟元素列表中的第 8 到第 15 个，且为 p 元素的元素 */

p:nth-child(n+8):nth-child(-n+15)
```

- of \<selector> 语法

```
/* 匹配前三个设置了 class="important" 的列表项 */

:nth-child(-n + 3 of li.important) {
}
```

#### :only-child

没有兄弟元素

```
<ol>
  <li>Robert Downey, Jr.</li>
</ol>

li:only-child {
  color: fuchsia;
}
```

#### :is()

以容错选择器列表作为参数，选择参数中的所有选择器

***容错选择器列表*** 意味着哪怕选择器列表中有一个选择器是无效的，其他选择器仍然可以正常执行。而对于使用逗号分隔的选择器列表来说，只要有一个选择器无效，其他选择器也会失效

```
section h1,
article h1,
aside h1,
nav h1 {
  font-size: 25px;
}

/* 下面是使用 :is() 伪类简化后的选择器 */

:is(section, article, aside, nav) h1 {
  font-size: 25px;
}
```

#### :where()

和 :is() 的用法一样，唯一不同之处在于，:is() 的选择器优先级 由 选择器列表中 优先级最高的选择器 决定，而 :where() 的优先级始终为 0

#### :not()

反选伪类（negation pseudo-class），参数是选择器列表（没有容错了），表示除了这些选择器，其他元素都会被选中

- 可以使用此伪类编写无用的选择器。例如，:not(*) 匹配任何不是元素的元素，这显然是荒谬的，所以这个附加的规则将永远不被应用。
- 可以利用这个伪类提高规则的优先级。例如，#foo:not(#bar) 和 #foo 都将匹配相同的元素，但是具有两个 id 的选择器具有更高的优先级。
- :not() 伪类的优先级将由其逗号分割的参数中优先级最高的选择器指定；提供与 :not(:is(argument)) 相同的优先级。
- :not(.foo) 将匹配任何非 .foo 的元素，包括 \<html> 和 \<body>，因此，最好和关系选择器搭配使用。
- 这个选择器将匹配任意“不是一个 X”的元素。当与后代选择器一起使用，这可能令人惊讶，因为有多种路径可以选择一个目标元素。
- 你可以同时否定多个选择器。例如：:not(.foo, .bar) 等同于 :not(.foo):not(.bar)。
- 如果传递给 :not() 伪类的选择器无效或者浏览器不支持，则整个规则都将是无效的。克服这种行为的有效方式是使用 :is 伪类（例如 :not(:is()) ），它接受一个可容错选择器列表。

### 用户行为伪类

一些伪类只会在用户以某种方式和文档交互的时候应用，也叫动态伪类

#### :hover

鼠标悬浮时触发

#### :focus

鼠标获取焦点时触发

#### :invalid

选择未通过验证的表单元素（\<form>、\<fieldset>、\<input> 等）

```
<input id="secret" name="secret" type="text" value="test" pattern="[a-z]+" />

input:invalid {
  background-color: ivory;
  border: none;
  outline: 2px solid red;
  border-radius: 5px;
}
```

### 伪元素

#### ::first-line

只选中元素中文字的第一行

```
<!-- 无论屏幕宽度或者字体大小如何改变，总是选中 p 元素中的第一行 -->

<article>
  <p>Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion daikon amaranth tatsoi tomatillo melon azuki bean garlic.</p>
  <p>Gumbo beet greens corn soko endive gumbo gourd. </p>
</article>

article p::first-line {
  font-size: 120%;
  font-weight: bold;
}

<!-- 伪类和伪元素的组合使用 -->

article p:first-child::first-line {
  font-size: 120%;
  font-weight: bold;
}
```

#### ::before

在元素的前方插入伪元素，必须有 content 属性

content 中不建议输入内容，因为屏幕阅读器无法识别

```
<!-- 应用：在文字后插入图标 -->

<p class="box">Content in the box in my HTML page.</p>

.box::after {
  content: " ➥";
}
```

应用：利用CSS实现三角形，伪元素，[带箭头的盒子](https://cssarrowplease.com/)

#### ::after

在元素的前方插入伪元素，和 ::before 用法一样

## 关系选择器

### 后代选择器

空格，选择所有的后代元素，包括儿子、孙子。。。

```
.box p {
  color: red;
}
```

### 子代选择器

>，选择儿子元素

```
ul > li {
  border-top: 5px solid red;
}
```

### 临接兄弟选择器

+，选择同一级的兄弟元素（必须紧邻在其之后）

```
<!-- 选择和 \<h1> 同级且紧邻的 \<p> 标签（同级、紧邻之后必须都要满足，缺一不可） -->

h1 + p {
  font-weight: bold;
}

<h1>A heading</h1>
<p>Gumbo beet greens corn soko endive gumbo gourd. </p>
```

### 通用兄弟选择器

~，选择元素之后的所有兄弟元素，即使不相邻

```
h1 ~ p {
  font-weight: bold;
}
```

# 4 CSS 优先权

## CSS 层叠

当多个 css 规则同时运用在一个元素上时，会产生样式表的 ***层叠*** ，如何判断哪个规则生效呢？主要从以下几个方面判断：

判断顺序：从上到下，上一级一样则判断下一级，直到某一个规则优先级胜出

1. 重要程度：属性值后有 !important ，属性优先级最高
2. 样式来源
3. 层叠层
4. 选择器优先级
5. 出现顺序：后面的规则会覆盖前面的规则

## 样式来源

CSS 可根据来源分为 3 种类型：用户代理样式表（浏览器默认的）、用户样式表（用户写的）、作者样式表（开发人员写的）

用户样式表有什么用？假如用户有视力障碍，需要将文字放大 200%，这时候可以通过设置用户样式表覆盖原有的 CSS

优先级 ***由低到高*** 如下：

1. 用户代理样式表中的声明（例如，浏览器的默认样式，在没有设置其他样式时使用）
2. 用户样式表中的常规声明（由用户设置的自定义样式）
3. 作者样式表中的常规声明（这些是我们 web 开发人员设置的样式）
4. 正在动画的样式
5. 作者样式表中的 !important 声明
6. 用户样式表中的 !important 声明
7. 用户代理样式表中的 !important 声明
8. 正在过渡的样式

为什么 !important 的优先级相反？为了保证用户样式表能够有足够的优先级去覆盖其他样式表

## 层叠层（级联层）

### 创建层叠层

#### @layer 声明方式

使用 @layer 声明规则，这将创建一个或多个没有分配任何样式的具名层

```
@layer theme，layout，utilities;
```

- 越靠后声明的层优先级越高
- 通常，你需要在 CSS 的第一行声明这个 @layer，以便完全控制层的顺序。
- 如果上述声明是站点 CSS 的第一行，那么层的顺序将是 theme、layout 和 utilities。
- 如果在上述语句之前已经创建了一些层，例如，如果 layout 已经存在，只会创建 theme 和 utilities，层顺序将是 layout、theme 和 utilities

#### @layer 块方式

可以使用块 @layer 来创建匿名层或具名层

```
/* 创建第一个层：具名层 `layout` */
@layer layout {
  main {
    display: grid;
  }
}

/* 创建第二个层：匿名层 */
@layer {
  body {
    margin: 0;
  }
}
```

- 越靠后创建的层优先级越高
- 没有办法重新排序已声明的层。如果在创建层之后，使用 @layout 声明，并且声明的是已经创建的层，声明将无法改变优先级顺序，仍然是 @layout 块的创建顺序决定优先级顺序
- 未命名的层，没有办法引用它们或向它们添加额外的样式
- 在层之外声明的所有样式都会加入到一个隐含的层中，这个隐含层会被排到声明列表的最后面，即拥有最高的优先级

关于层创建与媒体或特性查询

如果你使用媒体或特性查询来定义层，且媒体不匹配或特征不被支持，则不会创建该层（这有些反直觉，通常哪怕没有声明，使用 @layout 块仍可创建层）

```
/* 表示最小宽度不小于 50em 时创建 site 层，否则不建立 site 层 */

@media (min-width: 50em) {
  @layer site;
}

@layer page {
  h1 {
    text-decoration: overline;
    color: red;
  }
}

@layer site {
  h1 {
    text-decoration: underline;
    color: green;
  }
}
```

#### 使用 @import 将样式表导入层

导入时，@import 语句必须出现在 \<style> 代码块的最前面

以下层分别将样式表导入 components 层、components 层中的嵌套 dialog 层和一个未命名层

```
@import url("components-lib.css") layer(components);
@import url("dialog.css") layer(components.dialog);
@import url("marketing.css") layer();
```

将多个 CSS 文件导入到单个层中

```
@import url(comments.css) layer(social);
@import url(sm-icons.css) layer(social);
```

使用媒体查询和特性查询根据特定条件导入样式并创建层，以下将样式表导入到 international 层，但前提是浏览器支持 display: ruby，而且被导入的文件取决于屏幕的宽度

```
@import url("ruby-narrow.css") layer(international) supports(display: ruby) and
  (width < 32rem);
@import url("ruby-wide.css") layer(international) supports(display: ruby) and
  (width >= 32rem);
```

### 嵌套层

嵌套层是具名层或匿名层中的子层。每个层叠层（即使是匿名的）都可以包含嵌套层。导入到另一个层中的层会成为该层中的嵌套层。

#### 创建嵌套层

嵌套层和普通层叠层一样，也可以通过三种方式创建：声明、块、@import，只不过声明、@import用点表示法（ dad-layer.son-layer ）表示嵌套关系，块使用块中嵌套块的方式表示

```
@import url("components-lib.css") layer(components);
@import url("narrowtheme.css") layer(components.narrow);
```

- 在第一行中，我们将 components-lib.css 导入 components 层。如果该文件包含任何层，无论命名与否，这些层都会成为 components 层中的嵌套层。
- 第二行将 narrowtheme.css 导入 narrow 层，narrow 是 components 的子层。嵌套的 components.narrow 会作为 components 层中的最后一个层创建，除非 components-lib.css 已经包含一个 narrow 层，在这种情况下，narrowtheme.css 的内容会被附加到 components.narrow 嵌套层。

```
/* 向 components.narrow 嵌套层添加样式 */

@layer components.narrow {
  main {
    width: 50vw;
  }
}
```

### 如何确定优先权

#### 常规层叠层的优先权顺序

```
@import url(A.css) layer(firstLayer);
@import url(B.css) layer(secondLayer);
@import url(C.css);
```

上面的例子优先权如下（从低到高）：

1. firstLayer 普通样式（A.css）
2. secondLayer 普通样式（B.css）
3. 未分层普通样式（C.css）
4. 内联普通样式
5. 动画样式
6. 未分层重要样式（C.css）
7. secondLayer 重要样式（B.css）
8. firstLayer 重要样式（A.css）
9. 内联重要样式
10. 过渡样式

如果样式有冲突，后面的样式会覆盖前面的样式

#### 嵌套层叠层的优先权顺序

- 非嵌套样式优先于普通嵌套样式
- 晚创建或声明的嵌套层样式优先于先创建的
- 对于重要样式，前面规则的优先级反转

## 选择器优先级

- 基本思想：选择器越具体，css 优先级越高
- 巧妙利用优先级，通过样式的覆盖，可以减少代码量
- 浏览器如何计算优先级呢？计算方法：ID-类（属性选择器、伪类选择器）-元素（伪元素），分别对应，百位-十位-个位

```
/* 有0个ID选择器，有2个类选择器，有2个元素选择器，因此优先级为 0-2-2 */
li > a[href*="en-US"] > .inline-warning
```

- 如何比较优先级？先比较ID，ID如果一样则比较类，类如果一样则比较标签
- 特殊伪类的优先级：:where() 的优先级永远为0，:is() :not() 的优先级由括号中优先级最高的选择器决定
- 通用选择器（*）、组合符（+、>、~、' '）优先级都为0

# 5 CSS 继承

有些 css 属性会被子元素继承（color），有些则不会（width）

## 控制继承

通过 *继承通用属性* 值来控制继承，每个属性都可以接收这些值：

1. inherit：继承父元素的属性值
2. initial：设置为初始值，比如 color 的初始值是黑色
3. revert：设置为浏览器默认样式，比如 \<a> 的 color 浏览器默认值为蓝色
4. revert-layer：设置为上一个级联层（ @layer ）中的属性值
5. unset：重置为自然值，如果属性是自然继承那么就是 inherit，否则和 initial 一样

## 重设所有属性值

将所有属性的值设为某一种继承属性值

```
.fix-this {
  all: unset;
}
```

# 6 盒模型

内部显示（inner display type）和外部显示（outer display type）

## 外部显示类型

### 区块盒子 (block)

决定了当前盒子和盒子外其他元素的布局方式

- 盒子会产生换行。
- width 和 height 属性可以发挥作用。
- 内边距、外边距和边框会将其他元素从当前盒子周围“推开”。
- 如果未指定 width，方框将沿行向扩展，以填充其容器中的可用空间。在大多数情况下，盒子会变得与其容器一样宽，占据可用空间的 100%。

元素：\<h1> 、\<p>

### 行内盒子 (inline)

- 盒子不会产生换行。
- width 和 height 属性将不起作用。
- 垂直方向的内边距、外边距以及边框会被应用但是不会把其他处于 inline 状态的盒子推开。
- 水平方向的内边距、外边距以及边框会被应用且会把其他处于 inline 状态的盒子推开。

元素：\<a>、\<span>、\<em>、\<strong>

### 行内块 (inline-block)

通过以下属性可以设置行内块盒子，结合了块盒子和行内盒子

```
display: inline-block
```

它可以设置高度、宽度、内边距和外边距，但是周围的内容（文字）不会换行

## 内部显示类型

决定了盒子内元素的布局方式

例如，可以通过设置 display: flex; 来更改内部显示类型。该元素仍将使用外部显示类型 block 但内部显示类型将变为 flex

## 盒模型

CSS 盒模型整体上适用于区块盒子，它定义了盒子的不同部分（外边距、边框、内边距和内容）如何协同工作，以创建一个在页面上可以看到的盒子。行内盒子使用的只是盒模型中定义的部分行为。

盒模型组成部分：

- 内容盒子(Content)：显示内容的区域；使用 inline-size 和 block-size 或 width 和 height 等属性确定其大小。
- 内边距盒子(Padding)：填充位于内容周围的空白处；使用 padding 和相关属性确定其大小。
- 边框盒子(Border)：边框盒子包住内容和任何填充；使用 border 和相关属性确定其大小。
- 外边距盒子(Margin)：外边距是最外层，其包裹内容、内边距和边框，作为该盒子与其他元素之间的空白；使用 margin 和相关属性确定其大小。

### 标准盒模型

假设一个盒子的 CSS 如下：

```
.box {
  width: 350px;
  height: 150px;
  margin: 10px;
  padding: 25px;
  border: 5px solid black;
}
```

- 方框实际占用的空间宽为 410px（350 + 25 + 25 + 5 + 5）
- 高为 210px（150 + 25 + 25 + 5 + 5）
- 外边距不计入盒子的实际大小——当然，它影响盒子在页面上所占的总空间，但只影响盒子外的空间

### 替代盒模型

要为某个元素使用替代模型，可添加以下属性

```
.box {
  box-sizing: border-box;
}
```

这时，内边距和边框不会计入宽度或高度的计算，刚刚的示例中宽度会变为 350px，高度变为 150px

要在所有元素中使用替代盒模型（***这是开发人员的常见选择***），请在 \<html> 元素上设置 box-sizing 属性，并将所有其他元素设置为继承该值：

```
html {
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: inherit;
}
```

### 外边距

#### 相关属性

- margin-top，上外边距
- margin-right，右外边距
- margin-bottom，下外边距
- margin-left，左外边距
- margin，分为四种情况：
  - 指定一个值时，（上下左右）
  - 指定两个值时，（上下）（左右）
  - 指定三个值时，（上）（左右）（下）
  - 指定四个值时，（上）（右）（下）（左）

#### 外边距折叠

- 两个正外边距将合并为一个外边距。其大小等于最大的单个外边距。
- 两个负外边距会折叠，并使用最小（离零最远）的值。
- 如果其中一个外边距为负值，其值将从总值中减去。

### 边框

- border-top，上边框
- border-right，右边框
- border-bottom，下边框
- border-left，左边框
- border-width，边框宽度
- border-style，边框样式
- border-color，边框颜色
- border，可同时设置宽度、样式、颜色，例如：1px solid #000
- 细粒度属性：border-（方位）-（宽度样式或颜色），例如 border-top-width，表示设置上边框的宽度

### 内边距

内边距的值不能为负数，元素的背景会显示在内边距区域

- padding-top，上外边距
- padding-right，右外边距
- padding-bottom，下外边距
- padding-left，左外边距

# 7 CSS 样式

## 背景

### 背景颜色

```
.box {
  background-color: #567895;
}
```

### 背景图像

```
.a {
  background-image: url(balloons.jpg);
}
```

### 控制背景平铺行为

background-repeat，可用的值是：

- no-repeat，阻止背景重复平铺。
- repeat-x，仅水平方向上重复平铺。
- repeat-y，仅垂直方向上重复平铺。
- repeat，默认值，在水平和垂直两个方向重复平铺。

### 背景图像大小

background-size，可用值为：

- cover：浏览器将使图像足够大，使它完全覆盖了盒子区域，同时仍然保持其宽高比。在这种情况下，图像的部分区域可能会跳出盒子外。
- contain：浏览器会将图像调整到适合框内的尺寸。在这种情况下，如果图像的长宽比与盒子的长宽比不同，你可能会在图像的两边或顶部和底部出现空隙。
- 数值：`background-size: 100px 10em;`，第一个参数为宽，第二个参数为高

### 背景图像定位

background-position，可用值为：

- `background-position: 10cpx 8px;`，距离左边框 10px，距离上边框 8px
- `background-position: top;`，顶部居中
- `background-position: left;`，左部居中
- `background-position: right;`，右部居中
- `background-position: bottom;`，底部居中
- `background-position: center;`，水平垂直居中
- `background-position: bottom 10px right 20px;`，距离底部 10px，距离右边 20px

### 渐变背景

- linear-gradient，线性渐变
- radial-gradient，辐射渐变

[渐变背景在线生成](https://cssgradient.io/)

### 多个背景图像

```
background-image: url(image1.png), url(image2.png), url(image3.png), url(image4.png);

background-repeat: no-repeat, repeat-x, repeat;

background-position: 10px 20px, top right;
```

background-image 中先出现的图片背景会覆盖后出现的图片背景

当不同的属性具有不同数量的值时，属性值较少的会循环。在上面的例子中有四个背景图像，但是只有两个背景位置值。前两个位置值将应用于前两个图像，然后它们将再次循环——image3 将被赋予第一个位置值，image4 将被赋予第二个位置值。

### 背景滚动方式

background-attachment 属性，只有在有内容要滚动时（出现 scroll bar）才会有效果，可以取以下值：

- scroll：背景在页面滚动时滚动，如果滚动元素内部的内容，背景不会移动。
- fixed：当页面或元素内容滚动时，它都不会滚动。
- local：当页面或元素内容滚动时，它都会滚动。

[在线示例](https://mdn.github.io/learning-area/css/styling-boxes/backgrounds/background-attachment.html)

### 简写属性

background 属性被指定多个背景层时，使用逗号分隔每个背景层

每一层的语法如下：

- 在每一层中，下列的值可以出现 0 次或 1 次：
  - \<attachment>
  - \<bg-image>
  - \<position>
  - \<bg-size>
  - \<repeat-style>
  - \<bg-size> 只能紧接着 <position> 出现，以"/"分割，如： "center/80%".
- \<box> 可能出现 0 次、1 次或 2 次。如果出现 1 次，它同时设定 background-origin（背景位置参考范围）和 background-clip（背景覆盖范围）。如果出现 2 次，第一次的出现设置 background-origin，第二次的出现设置 background-clip。
- \<background-color> 只能被包含在最后一层。

### 无障碍考虑

- 把文字放在背景图片或颜色上面时，要保证有足够的对比度让文字清晰易读。
- 如果设置了一个背景图像，并且文本将被放置在该图像的顶部，还应该指定一个 background-color，以便在图像未加载时文本也足够清晰。
- 屏幕阅读器不能解析背景图像，因此背景图片应该只是纯粹的装饰；任何重要的内容都应该是 HTML 页面的一部分，而不是包含在背景中。

## 边框

### 简写属性

```
.box {
  border: 1px solid black;
}

/* 上方简写等价于下面： */

.box {
  border-width: 1px;
  border-style: solid;
  border-color: black;
}

.box {
  border-top: 1px solid black;
}

/* 上方简写等价于下面： */

.box {
  border-top-width: 1px;
  border-top-style: solid;
  border-top-color: black;
}
```

### 边框圆角

即使元素没有边框，圆角也可以用到 background 上面，具体效果受 background-clip 影响。

```
/* 四个角都有 10px 的圆角半径 */

.box {
  border-radius: 10px;
}

/* 右上角的水平半径为 1em，垂直半径为 10％ */

.box {
  border-top-right-radius: 1em 10%;
}
```

属性的简写：

- 一个参数，所有圆角
- 两个参数，(左上右下) (左下右上)
- 三个参数，(左上) (右上左下) (右下)
- 四个参数，(左上) (右上) (右下) (左上)
- 斜线左边是水平半径，右边是垂直半径

```
border-radius: 4px 3px 6px / 2px 4px;

/* 左上水平半径为 4px，右上左下水平半径为 3px，右下水平半径为 6px，左上右下垂直半径为 2px，右上左下垂直半径为 4px ，等价于： */

border-top-left-radius: 4px 2px;
border-top-right-radius: 3px 4px;
border-bottom-right-radius: 6px 2px;
border-bottom-left-radius: 3px 4px;
```

## 不同方向的文本

### 书写模式

writing-mode，三个值分别是：

- horizontal-tb: 块流向从上至下。对应的文本方向是横向的。
- vertical-rl: 块流向从右向左。对应的文本方向是纵向的。
- vertical-lr: 块流向从左向右。对应的文本方向是纵向的。

书写模式会改变元素内的块元素和行内元素的方向，例如，默认情况下，块元素是从上到下排列，行内元素从左到右排列，但如果设置了 vertical-rl，会使块元素的排列方向变为水平从左到右，行内元素方向变为从上到下

根据某些语言的书写习惯，文字会自动改变方向

### 逻辑属性和逻辑值

逻辑属性，可以根据书写模式灵活改变属性作用的方向（水平或垂直）

#### 内联尺寸和块级尺寸

width，height 可以设置宽度和高度，但不会随书写模式改变，为了使元素的宽高和书写模式联动，可以使用 内联尺寸（inline-size）或 块级尺寸（block-size）代替 width，height 

- 内联尺寸，表示行内元素方向的尺寸，如果 writing-mode: horizontal-tb，inline-size 等同于 width。如果 writing-mode: vertical-rl，inline-size 等同于 height。
- 块级尺寸，表示块元素方向的尺寸，如果 writing-mode: horizontal-tb，block-size 等同于 height。如果 writing-mode: vertical-rl，block-size 等同于 width。

#### 其他逻辑属性

- margin-top 属性映射是 margin-block-start
- padding-left 属性映射是 padding-inline-start
- border-bottom 属性映射是 border-block-end

更多参考[此处](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_logical_properties_and_values)

#### 逻辑值

有一些属性的取值是一些物理值（如top、right、bottom、left）。

这些值同样拥有逻辑值映射（block-start、inline-end、block-end、inline-start）

#### 物理属性还是逻辑属性？

逻辑属性是在物理属性之后出现的，因而最近才开始在浏览器中应用。你可以通过查看 MDN 的属性页面来了解浏览器对逻辑属性的支持情况。如果你并没有应用多种书写模式，那么现在你可能更倾向于使用物理属性，因为这些在你使用弹性布局和网格布局时非常有用。

## 图像和视频

### 可替换元素

图像和视频（\<iframe>、\<video>、\<embed>、\<img>）被描述为 **替换元素**。这意味着 CSS 不能影响它们的内部布局，仅影响它们在页面上相对于其他元素的位置。

某些替换元素（例如图像和视频）也具有宽高比。这意味着它在水平（x）和垂直（y）方向上均具有大小，并且默认情况下将使用文件的固有尺寸进行显示。

### 调整大小

如何处理溢出？

- max-width 设为 100%
- 或者设置 `object-fit: cover;`，表示替换元素完全覆盖盒子，且比例不变，但是可能有一部分被盒子裁切掉
- 或者设置 `object-fit: contain;`，表示替换元素完整的放到盒子中，且比例不变，但是可能有一部分盒子产生空白
- 或者设置 `object-fit: fill;`，表示替换元素完全覆盖盒子，但是比例会会变化

### 布局中的替换元素

在对替换元素使用各种 CSS 布局时，你可能会发现他们的表现方式与其他元素有一些细节上的差异。例如，flex 或者 grid 布局中，默认情况下元素会被拉伸到充满整块区域。但是图像不会被拉伸，而会对齐到网格区域或者弹性容器的起始处。

为了强制图像拉伸，以充满其所在的网格单元：

```
img {
  width: 100%;
  height: 100%;
}
```

这将会无条件地拉伸图像，所以很可能不会是你想要的。

## 表单

### 表单元素默认不继承

在一些浏览器中，表单元素默认不会继承字体样式，需要通过 inherit 属性值实现样式继承

### 重置表单样式

```
button,
input,
select,
textarea {
  font-family: inherit;
  font-size: 100%;
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

textarea {
  overflow: auto;
}
```

## 表格

### 固定列宽

```
table {
  border-collapse: collapse;
}
```

通常情况下，表列的尺寸会根据所包含的内容大小而变化，通过 `table-layout: fixed`，你可以根据列标题的宽度来规定列的宽度

### 消除单元格边框之间的空隙

```
table {
  border-collapse: collapse;
}
```

collapse，倒塌，消除单元格边框之间的空隙

### 单元格条纹效果

```
tbody tr:nth-child(odd) {
  background-color: #ff33cc;
}

tbody tr:nth-child(even) {
  background-color: #e495e4;
}
```

### 标题位置

```
caption {
  caption-side: bottom;
}
```

## 盒子阴影

### 简单阴影

```
.simple {
  box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.7);
}
```

- 第一个长度值是水平偏移量（horizontal offset）——即向右的距离，阴影被从原始的框中偏移 (如果值为负的话则为左)。
- 第二个长度值是垂直偏移量（vertical offset）——即阴影从原始盒子中向下偏移的距离 (或向上，如果值为负)。
- 第三个长度的值是模糊半径（blur radius）——在阴影中应用的模糊度。
- 颜色值是阴影的基本颜色（base color）。

### 多个阴影

一个盒子可以有多个阴影，可以实现多个光源的复杂效果

```
.multiple {
  box-shadow:
    1px 1px 1px black,
    2px 2px 1px black,
    3px 3px 1px red,
    4px 4px 1px red,
    5px 5px 1px black,
    6px 6px 1px black;
}
```

### 内部阴影

```
button {
  box-shadow:
    inset 2px 2px 1px black,
    inset 2px 3px 5px rgba(0, 0, 0, 0.3),
    inset -2px -3px 5px rgba(255, 255, 255, 0.5);
}
```

## 滤镜

滤镜可以应用在任何元素上，包括块元素和行内元素

```
.filter {
  -webkit-filter: drop-shadow(5px 5px 1px rgba(0, 0, 0, 0.7));
  filter: drop-shadow(5px 5px 1px rgba(0, 0, 0, 0.7));
}
```

上面的例子根据边框轮廓产生阴影，括号内参数和 box-shadow() 一样，和他不同的是，使用滤镜，边框阴影会随边框样式（dot、dash）改变

[更多滤镜](https://developer.mozilla.org/zh-CN/docs/Web/CSS/filter)

## 混合模式

### background-blend-mode

将一个元素的两个背景混合

[更多属性](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-blend-mode)

### mix-blend-mode

将一个元素的两个背景，以及下方元素的背景混合

[更多属性](https://developer.mozilla.org/zh-CN/docs/Web/CSS/mix-blend-mode)

### text-clip

将背景图像剪贴到元素文本的形状

```
.text-clip {
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
```

## 字体

### 字体样式

#### 字体颜色

```
p {
  color: red;
}
```

#### 字体种类

```
p {
  font-family: arial;
}
```

##### 网页安全字体

网络安全字体在几乎所有最常用的操作系统（Windows，Mac，最常见的 Linux 发行版，Android 和 iOS 版本）中都可用

- Arial（sans-serif）通常认为最佳做法还是添加 Helvetica 作为 Arial 的首选替代品，尽管它们的字体面几乎相同，但 Helvetica 被认为具有更好的形状，即使 Arial 更广泛地可用。
- Courier New（monospace）使用 Courier New 作为 Courier 的首选替代方案，被认为是最佳做法。
- Georgia（serif）
- Times New Roman	serif	使用 Times 作为 Times New Roman 的首选替代方案，被认为是最佳做法。
- Trebuchet MS（sans-serif）在移动操作系统上并不广泛。
- Verdana（sans-serif）

[查看主流字体在操作系统中的覆盖率](https://www.cssfontstack.com/)

##### 默认字体

CSS 定义了 5 个常用的字体名称：serif, sans-serif, monospace, cursive, 和 fantasy. 这些都是非常通用的，当使用这些通用名称时，使用的字体完全取决于每个浏览器，而且它们所运行的每个操作系统也会有所不同。

- serif，衬线字体，即有衬线的字体（衬线是指字体笔画尾端的小装饰，存在于某些印刷体字体中）。
- sans-serif，无衬线字体。
- monospace，等宽字体，指包含的全部字符的宽度相同的字体，通常在编辑代码时使用。
- cursive，手写字体，对于英文字符而言通常具有顺滑的连接笔画以模拟手写效果。
- fantasy，装饰字体。

##### 字体栈

```
p {
  font-family: "Trebuchet MS", Verdana, sans-serif;
}
```

当字体名称有多个单词时，需要用引号包裹

#### 字体大小

浏览器的根元素 font-size 标准设置的值为 16px

```
html {
  font-size: 10px;
}
```

#### 字体样式

font-style: 用来打开和关闭文本 italic (斜体)。可能的值如下 (你很少会用到这个属性，除非你因为一些理由想将斜体文字关闭斜体状态)：

- normal: 将文本设置为普通字体 (将存在的斜体关闭)
- italic: 如果当前字体的斜体版本可用，那么文本设置为斜体版本；如果不可用，那么会利用 oblique 状态来模拟 italics。
- oblique: 将文本设置为斜体字体的模拟版本，也就是将普通文本倾斜的样式应用到文本中。

#### 字体粗细

font-weight: 设置文字的粗体大小。这里有很多值可选 (比如 -light, -normal, -bold, -extrabold, -black, 等等), 不过事实上你很少会用到 normal 和 bold 以外的值：

- normal, bold: 普通或者加粗的字体粗细
- lighter, bolder: 将当前元素的粗体设置为比其父元素粗体更细或更粗一步。100–900: 数值粗体值，如果需要，可提供比上述关键字更精细的粒度控制。

#### 文本转换

text-transform: 允许你设置要转换的字体。值包括：

- none: 防止任何转型。
- uppercase: 将所有文本转为大写。
- lowercase: 将所有文本转为小写。
- capitalize: 转换所有单词让其首字母大写。
- full-width: 将所有字形转换成全角，即固定宽度的正方形，类似于等宽字体，允许拉丁字符和亚洲语言字形（如中文，日文，韩文）对齐。

#### 文本装饰

text-decoration: 设置/取消字体上的文本装饰 (你将主要使用此方法在设置链接时取消设置链接上的默认下划线。) 可用值为：

- none: 取消已经存在的任何文本装饰。
- underline: 文本下划线。
- overline: 文本上划线。
- line-through: 穿过文本的线。

注意 text-decoration 是一个缩写形式，它由 text-decoration-line, text-decoration-style 和 text-decoration-color 构成。你可以使用这些属性值的组合来创建有趣的效果，比如 text-decoration: line-through red wavy，表示设置穿过文本的线，颜色为红色，样式为波浪线

#### 文字阴影

```
text-shadow: 4px 4px 5px red;
```

四个属性值：水平偏移量，垂直偏移量，模糊距离，颜色

可以同时设置多个文字阴影，[这里是一些有趣的实践](https://www.sitepoint.com/moonlighting-css-text-shadow/)

### 文本布局

#### 文本对齐

text-align 属性用来控制文本如何和它所在的内容盒子对齐。可用值如下，并且在与常规文字处理器应用程序中的工作方式几乎相同：

- left: 左对齐文本。
- right: 右对齐文本。
- center: 居中文字。
- justify: 使文本展开，改变单词之间的差距，使所有文本行的宽度相同。特别是当应用于其中有很多长单词的段落时。可以和 `hyphens:manual`（连字符换行）搭配使用，打破一些更长的词语。

#### 行高

可以设置一个无单位的值，作为乘数，通常这种是比较好的做法。无单位的值乘以 font-size 来获得 line-height。推荐的行高大约是 1.5–2 

```
line-height: 1.5;
```

文字如何在盒子内垂直居中？

- 将行高（line-height）设置为盒子的内容高度（height）

#### 字母和单词间距

```
p {
  letter-spacing: 2px;
  word-spacing: 4px;
}
```

### 字体简写

- 只有 font-size 和 font-family 是一定要指定的
- font-size 和 line-height 属性之间必须以斜杠分隔。
- font-family 必须最后指定。
- font-style、font-variant 和 font-weight 必须在 font-size 之前。

```
font:
  italic normal bold normal 3em/1.5 Helvetica,
  Arial,
  sans-serif;
```

## 列表



# 8 CSS 溢出

元素内的内容过多时会产生溢出。

现代网页布局的方式可以很好地处理溢出。但是在以往，开发者会更多地使用固定高度，尽力让毫无关联的盒子的底部对齐。这是很脆弱的，一些盒子，它们的内容遮到了页面上的其他内容。这就是溢出，理论上你应该能重新排布这些布局，使得它不必依赖于盒子尺寸的调整。

在开发网站的时候，你应该一直把溢出的问题挂在心头，你应该用或多或少的内容测试设计，增加文本的字号，确保你的 CSS 可以正常地协调。改变溢出属性的值，来隐藏内容或者增加滚动条，会是你仅仅在少数特别情况下需要的，例如在你确实需要一个可滚动盒子的时候。

## overflow 属性

overflow 属性是你控制一个元素溢出的方式，可以取以下值：

- visible，默认值，溢出内容可见
- hidden，隐藏溢出内容
- scroll，溢出内容滚动可见，`overflow-y: scroll` 仅在 y 轴滚动
- auto，浏览器自动控制，一般是内容溢出时再显示滚动条

属性的简写：overflow: scroll hidden 会把 overflow-x 设置成 scroll，而 overflow-y 则为 hidden

如果需要在小盒子里面和长英文词打交道，可以了解一下 word-break 或者 overflow-wrap 属性

## 溢出会建立区块格式化上下文

在你使用诸如 scroll 或者 auto 的时候，你就建立了一个区块格式化上下文（Block Formatting Context）。结果就是，你改变了 overflow 的值的话，对应的盒子就变成了更加小巧的状态。在容器之外的东西没法混进容器内，也没有东西可以突出盒子，进入周围的版面。

# 9 CSS 的值与单位

## 长度单位

### 绝对长度

- cm，厘米，1cm = 37.8px = 25.2/64in
- mm，毫米，1mm = 1/10th of 1cm
- Q，四分之一毫米，1Q = 1/40th of 1cm
- in，英寸，1in = 2.54cm = 96px
- pc，派卡，1pc = 1/6th of 1in
- pt，点，1pt = 1/72th of 1in
- px，像素，1px = 1/96th of 1in

### 相对长度

- em，相对于父元素的字体大小，1em 表示浏览器字体默认宽度，2em 表示 2 倍大小。em 可以实现字体大小随列表嵌套深度增大的效果
- rem，相对于根元素（html）的字体大小，即 1rem 是固定的大小，它不会随着父元素变化
- vh 和 vw 分别相对于视口（浏览器显示网页的区域）的高度和宽度，100vh 表示整个视口高度，10wh 表示 10% 的视口宽度

### 百分比

- 如果将元素的字体大小设置为百分比，那么它将是元素父元素字体大小的百分比。
- 如果使用百分比作为宽度值，那么它将是父值宽度的百分比
- 把百分数作为内外边距，值是以包含块的内联尺寸（通常为宽度）进行计算的，例如 `margin: 10%;`，即所有边的内外边距都为元素宽度的 10%

## 颜色值

### RGB 和 RGBA

接收红、绿、蓝、（透明度）值

```
.one {
  background-color: rgb(2 121 139);
}

/* 添加了透明度参数，1表示完全不透明，下面例子表示有 30% 不透明，旧版 CSS 需要使用 rgba() 函数实现透明值 */

.one {
  background-color: rgb(2 121 139 / .3);
}
```

### 十六进制

```
.one {
  background-color: #02798b;
}
```

### HSL 和 HSLA

接收色相、饱和度、亮度、（透明度）值

- 色调：颜色的底色。这个值在 0 和 360 之间，表示 color wheel 周围的角度。
- 饱和度：颜色有多饱和？它的值为 0–100%，其中 0 为无颜色（它将显示为灰色阴影），100% 为全色饱和度
- 亮度：颜色有多亮？它从 0–100% 中获取一个值，其中 0 表示没有光（它将完全显示为黑色），100% 表示完全亮（它将完全显示为白色）

```
.one {
  background-color: hsl(188 97% 28%);
}

/* 添加了透明度参数，旧版 CSS 需要使用 hsla() 函数实现透明值 */

.one {
  background-color: hsl(188 97% 28% / .3);
}
```

## calc() 函数

如下例子，宽度设置为父元素的 30% 加上 100px，注意运算符左右要有空格

```
.box {
  width: calc(30% + 100px);
}
```

# 10 CSS 调整元素尺寸

## 固有尺寸

使用 \<img> 标签，且 CSS 中没有设置其尺寸，那么将使用其固有尺寸显示

块级元素的固有尺寸（内部没有内容时），高度为 0，宽度为父元素的 100%

## 设置具体的尺寸

### min- 和 max- 前缀的属性

例如设置一个 min-height 属性。盒子就会一直保持大于这个最小高度，但是如果有比这个盒子在最小高度状态下所能容纳的更多内容，那么盒子就会变大。

对 \<img> 使用 max-width: 100%，图像可以变得比固有尺寸更小，但是不会大于固有尺寸的 100%。这样做的目的是，在没有足够空间以原有宽度展示图像时，让图像缩小，同时确保它们不会比 max-width 的宽度大。

# 11 CSS 前缀

浏览器厂商们有时会给实验性的或者非标准的 CSS 属性和 JavaScript API 添加前缀，这样开发者就可以用这些新的特性进行试验，同时（理论上）防止他们的试验代码被依赖，从而在标准化过程中破坏 web 开发者的代码。开发者应该等到浏览器行为标准化之后再使用未加前缀的属性。

浏览器厂商们正在努力停止使用前缀来表示实验性质的代码的行为。Web 开发者一直在生产环境的网站上使用这些实验性代码，这使得浏览器厂商更难保证浏览器兼容性和处理新特性；这也伤害了更小众的浏览器，它们被迫添加其他浏览器前缀以加载热门网站。

现在的趋势是将实验性功能添加在需要用户自行设置偏好或标记（flag）的地方，同时编写一个更小规模的规范，以更快达到稳定状态。

主流浏览器引擎前缀：

- -webkit- （谷歌，Safari，新版 Opera 浏览器，以及几乎所有 iOS 系统中的浏览器（包括 iOS 系统中的火狐浏览器）；基本上所有基于 WebKit 内核的浏览器）
- -moz- （火狐浏览器）
- -o- （旧版 Opera 浏览器）
- -ms- （IE 浏览器 和 Edge 浏览器）