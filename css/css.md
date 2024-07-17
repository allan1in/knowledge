# 目录

- [目录](#目录)
- [资源链接](#资源链接)
- [1 CSS介绍](#1-css介绍)
  - [引入方式](#引入方式)
  - [运行流程](#运行流程)
  - [CSS兼容](#css兼容)
  - [注释](#注释)
- [2 CSS选择器](#2-css选择器)
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
- [4 CSS层叠](#4-css层叠)
  - [层叠](#层叠)
  - [来源](#来源)
  - [层叠层（级联层）](#层叠层级联层)
    - [创建层叠层](#创建层叠层)
      - [@layer 声明方式](#layer-声明方式)
      - [@layer 块方式](#layer-块方式)
  - [选择器优先级](#选择器优先级)
- [5 CSS继承](#5-css继承)
  - [控制继承](#控制继承)
  - [重设所有属性值](#重设所有属性值)
# 资源链接

- [MDN 官方教程](https://developer.mozilla.org/zh-CN/docs/Web/CSS)

# 1 CSS介绍

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

## CSS兼容

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

# 2 CSS选择器

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

# 4 CSS层叠

## 层叠

当多个 css 规则同时运用在一个元素上时，会产生样式表的 ***层叠*** ，如何判断哪个规则生效呢？主要从以下几个方面判断：

判断顺序：从上到下，上一级一样则判断下一级，直到某一个规则优先级胜出

1. 重要程度：属性值后有 !important ，属性优先级最高
2. 引入方式：内联样式 > 内部样式 > 外部样式
3. 来源
4. 层叠层
5. 选择器优先级
6. 出现顺序：后面的规则会覆盖前面的规则

## 来源

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

通常，你需要在 CSS 的第一行声明这个 @layer，以便完全控制层的顺序。如果上述声明是站点 CSS 的第一行，那么层的顺序将是 theme、layout 和 utilities。如果在上述语句之前已经创建了一些层，那么便会创建之前还没创建的层，并按 从左到右的先后顺序 将 新创建的层 添加到 层列表的末尾

#### @layer 块方式

```
/* 创建第一个层：具名层 `layout` */
@layer layout {
  main {
    display: grid;
  }
}

/* 创建第二个层：一个未命名的匿名层 */
@layer {
  body {
    margin: 0;
  }
}
```

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

# 5 CSS继承

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
