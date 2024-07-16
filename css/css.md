# 1 CSS介绍

CSS (Cascading Style Sheets)，层叠样式表

```
h1 {
  color: red;
  font-size: 5em;
}
```

包含四部分：选择器、大括号、属性名、属性值

注释

```
/* 注释 */
```

## 1.1 引入方式

1. 外部样式表

    `<link rel="stylesheet" href="styles.css" />`

    \<head> 标签中使用 \<link> 标签，推荐使用

2. 内部样式表

    \<head> 标签中使用 \<style> 标签

3. 内联样式表

    `<h1 style="color: blue;background-color: yellow;border: 1px solid black;">Hello World!</h1>`
    
    尽可能避免使用

## 1.2 运行流程

加载 HTML ==> 解析 HTML ==> 生成 DOM 树 ==> 根据 HTML 加载解析 CSS 并渲染到 DOM ==> 着色

图解[css运行流程](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/First_steps/How_CSS_works/rendering.svg)

DOM（Document Object Model），文件对象模型，DOM 是文件在计算机内存中的表现形式

## 1.3 CSS兼容

CSS 由 W3C (万维网联盟) 中的一个名叫 CSS Working Group 团体发展起来的，浏览器并不会同时实现所有的新 CSS，当浏览器遇到无法解析的 CSS 选择器或声明的时候，会选择什么也不会做，继续解析下一个 CSS 样式

```
.box {
  width: 500px;
  width: calc(100% - 50px);
}
```

如上代码，兼容了不支持 calc() 函数的浏览器

# 2 CSS选择器

## 2.1 选择器列表

```
h1,
.special {
  color: blue;
}
```

1. 多个选择器用逗号分隔，为多个标签赋予相同的属性

2. 如果其中任何一个选择器无效 (存在语法错误)，那么整条规则都会被忽略

## 2.2 基础选择器

### 1. 类型选择器

也叫做标签名选择器或者是元素选择器，根据标签名称选择

```
span {
  background-color: yellow;
}
```

### 2. 全局选择器

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

### 3. class 选择器

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

### 4. id 选择器

根据标签的 id 属性值选择标签

```
#one {
  background-color: yellow;
}
```

ID 所指特定，会优先于大多数其他选择器，所以很难处理它们。大多数情况下，给一个元素加个 class，而不是使用 ID，会更好

## 2.3 属性选择器

### 1. 根据存在和值选择

匹配带有指定属性（方括号中的值）的元素，如下，表示选择类型为 li 且带有 class 属性的元素

```
<li class="anyvalue">Item 2</li>

li[class] {
  font-size: 200%;
}
```

= ，匹配带有指定属性（方括号中的值）的元素，且属性值为指定值（引号中的值），如下，表示选择类型为 li 、有 class 属性、属性值为 a 的元素

```
<li class="a">Item 2</li>

li[class="a"] {
  background-color: yellow;
}
```

匹配带有指定属性（方括号中的值）的元素，且属性值中 ***至少有一个*** 为指定值（引号中的值），如下，表示选择类型为 li 、有 class 属性、属性值中 ***至少有一个*** 为 a 的元素

```
<li class="bc a d">Item 2</li>

li[class~="a"] {
  color: red;
}
```

|= ，匹配带有指定属性（方括号中的值）的元素，且属性值中 ***第一个值*** 为指定值（引号中的值），如下，表示选择类型为 li 、有 class 属性、属性值中 ***第一个值*** 为 a 的元素 ***（第一个值后必须紧接着一个连字符 - ，或者只有这一个值）***

```
<li class="a-b-c">Item 2</li>
<li class="a">Item 2</li>

li[class|="a"] {
  color: red;
}
```

### 2. 根据子字符串匹配选择

^= ，匹配带有指定属性（方括号中的值）的元素，且属性值的 ***开头*** 为指定值（引号中的值），如下，表示选择类型为 li 、有 class 属性、属性值的 ***开头*** 为 a 的元素 

```
<li class="abc">Item 1</li>

li[class^="a"] {
  font-size: 200%;
}
```

$= ，匹配带有指定属性（方括号中的值）的元素，且属性值的 ***结尾*** 为指定值（引号中的值），如下，表示选择类型为 li 、有 class 属性、属性值的 ***结尾*** 为 a 的元素 

```
<li class="cba">Item 1</li>

li[class$="a"] {
  background-color: yellow;
}
```

*= ，匹配带有指定属性（方括号中的值）的元素，且属性值中 ***至少有一处*** 为指定值（引号中的值），如下，表示选择类型为 li 、有 class 属性、属性值中 ***至少有一处*** 为 a 的元素 

```
<li class="bac">Item 1</li>

li[class*="a"] {
  color: red;
}
```

^= ，设置要匹配的属性值大小写不敏感，i 标记

```
<li class="Abc">Item 1</li>

li[class^="a" i] {
  color: red;
}
```

## 2.4 伪类和伪元素

伪类是选择器的一种，它用于选择处于特定状态的元素

伪元素表现得像往标记文本中加入全新的 HTML 元素一样，而不是向现有的元素上应用类

### 1. 简单伪类

:first-child ，选择一组兄弟元素中的第一个，如下，选择类型为 article 元素之下、既是父元素的第一个子元素也是 p 类型的元素

```
article p:first-child {
  font-size: 120%;
  font-weight: bold;
}
```

:last-child ，选择一组兄弟元素中的最后一个，如下，选择类型为 article 元素之下、既是父元素的最后一个元素也是 p 类型的元素

```
article p:last-child {
  font-size: 120%;
  font-weight: bold;
}
```

:nth-child() ，根据元素在父元素的子元素列表中的索引 ***（从1开始）*** 来选择元素

1. 关键字值：even（偶数）或 odd（奇数）

```
li:nth-child(even) {
  background-color: lightyellow;
}
```

2. 函数符号：An+B ，其中 A B 为自定义的常数值，n 是从 0 开始不断递增的整数

```
/* 选取前 3个 class 为 important 且类型为 li 的元素 */

li.important:nth-child(-n + 3)

/* 兄弟元素列表中的第 8 到第 15 个，且为 p 元素的元素 */

p:nth-child(n+8):nth-child(-n+15)
```

3. of \<selector> 语法

```
/* 匹配前三个设置了 class="important" 的列表项 */

:nth-child(-n + 3 of li.important) {
}
```

:only-child ，没有兄弟元素

```
<ol>
  <li>Robert Downey, Jr.</li>
</ol>

li:only-child {
  color: fuchsia;
}
```

:invalid ，选择未通过验证的表单元素（\<form>、\<fieldset>、\<input> 等）

```
<input id="secret" name="secret" type="text" value="test" pattern="[a-z]+" />

input:invalid {
  background-color: ivory;
  border: none;
  outline: 2px solid red;
  border-radius: 5px;
}
```

### 2. 用户行为伪类

一些伪类只会在用户以某种方式和文档交互的时候应用，也叫动态伪类

:hover，鼠标悬浮时触发

:focus，鼠标获取焦点时触发

### 3. 伪元素

::first-line，只选中元素中文字的第一行

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

::before 和 ::after，在元素的前方或后方插入伪元素，必须有 content 属性

content 中不建议输入内容，因为屏幕阅读器无法识别

```
<!-- 应用：在文字后插入图标 -->

<p class="box">Content in the box in my HTML page.</p>

.box::after {
  content: " ➥";
}
```

应用：利用CSS实现三角形，伪元素，[带箭头的盒子](https://cssarrowplease.com/)

## 2.5 关系选择器

### 1. 后代选择器

空格，选择所有的后代元素，包括儿子、孙子。。。

```
.box p {
  color: red;
}
```

### 2. 子代选择器

>，选择儿子元素

```
ul > li {
  border-top: 5px solid red;
}
```

### 3. 临接兄弟选择器

+，选择同一级的兄弟元素（必须紧邻在其之后）

```
<!-- 选择和 \<h1> 同级且紧邻的 \<p> 标签（同级、紧邻之后必须都要满足，缺一不可） -->

h1 + p {
  font-weight: bold;
}

<h1>A heading</h1>
<p>Gumbo beet greens corn soko endive gumbo gourd. </p>
```

### 4. 通用兄弟选择器

~，选择元素之后的所有兄弟元素，即使不相邻

```
h1 ~ p {
  font-weight: bold;
}
```

## 2.6 层叠、优先级与继承

### 1. 层叠

当多个 css 规则同时运用在一个元素上时，会产生样式表的层叠，如何判断哪个规则生效呢？

判断顺序：先看重要程度，重要程度一样再看优先级，优先级一样再看资源顺序

1. 重要程度：!important （写在属性值后），尽量避免使用。覆盖 !important 唯一的办法就是另一个 !important 具有相同优先级而且顺序靠后，或者更高优先级。!important 一样则判断内联样式，内联样式高于其他样式

2. 优先级：选择器越具体，css 优先级越高

3. 资源顺序：后面的规则会覆盖前面的规则

### 2. 优先级

1. 巧妙利用优先级，通过样式的覆盖，可以减少代码量

2. 浏览器如何计算优先级呢？计算方法：ID-类（属性选择器、伪类选择器）-元素（伪元素），分别对应，百位-十位-个位

   如下例，有0个ID选择器，有2个类选择器，有2个元素选择器，因此优先级为 0-2-2

   `li > a[href*="en-US"] > .inline-warning`

3. 如何比较优先级？先比较ID，ID如果一样则比较类，类如果一样则比较标签
4. 特殊伪类的优先级：:where() 的优先级永远为0，:is() :not() 的优先级由括号中优先级最高的选择器决定
5. 通用选择器（*）、组合符（+、>、~、' '）优先级都为0

### 3. 继承

有些 css 属性会被子元素继承（color），有些则不会（width）

***控制继承***

通过 *继承通用属性* 值来控制继承，每个属性都可以接收这些值：

1. inherit：继承父元素的属性值

2. initial：设置为初始值，比如 color 的初始值是黑色

3. revert：设置为浏览器默认样式，比如 \<a> 的 color 浏览器默认值为蓝色

4. revert-layer：设置为上一个级联层（ @layer ）中的属性值

5. unset：重置为自然值，如果属性是自然继承那么就是 inherit，否则和 initial 一样

***重设所有属性值***

将所有属性的值设为某一种继承属性值

```
.fix-this {
  all: unset;
}
```

### 4. CSS来源的影响

CSS 可根据来源分为 3 种类型：用户代理样式表（浏览器默认的）、用户样式表（用户写的）、作者样式表（开发人员写的）

优先级由低到高如下：

1. 用户代理样式表中的声明（例如，浏览器的默认样式，在没有设置其他样式时使用）

2. 用户样式表中的常规声明（由用户设置的自定义样式）

3. 作者样式表中的常规声明（这些是我们 web 开发人员设置的样式）

4. 作者样式表中的 !important 声明

5. 用户样式表中的 !important 声明

6. 用户代理样式表中的 !important 声明

为什么 !important 的优先级相反？为了保证用户样式表能够有足够的优先级去覆盖其他样式表

用户样式表有什么用？假如用户有视力障碍，需要将文字放大 200%，这时候可以通过设置用户样式表覆盖原有的 CSS

## 2.7 级联层（层叠层）