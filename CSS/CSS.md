- [0 资源链接](#0-资源链接)
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
      - [:nth-of-type](#nth-of-type)
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
- [3 CSS 优先权](#3-css-优先权)
  - [CSS 层叠（级联）](#css-层叠级联)
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
- [4 盒模型](#4-盒模型)
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
- [5 CSS 样式](#5-css-样式)
  - [样式前缀](#样式前缀)
    - [主流浏览器引擎前缀](#主流浏览器引擎前缀)
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
    - [背景裁切](#背景裁切)
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
      - [文本缩进](#文本缩进)
      - [文本对齐](#文本对齐)
      - [行高](#行高)
      - [字母和单词间距](#字母和单词间距)
    - [字体简写](#字体简写)
    - [网络字体](#网络字体)
      - [字体资源](#字体资源)
      - [使用网络字体](#使用网络字体)
      - [在线字体服务](#在线字体服务)
  - [列表](#列表)
    - [符号样式](#符号样式)
    - [符号位置](#符号位置)
    - [自定义符号图片](#自定义符号图片)
    - [简写属性](#简写属性-2)
    - [自定义计数规则](#自定义计数规则)
  - [链接](#链接)
    - [链接状态](#链接状态)
    - [默认样式](#默认样式)
    - [伪类顺序](#伪类顺序)
    - [轮廓](#轮廓)
    - [光标悬停样式](#光标悬停样式)
    - [应用：链接中加入图标](#应用链接中加入图标)
    - [应用：样式化链接为按钮（TODO）](#应用样式化链接为按钮todo)
  - [调整尺寸](#调整尺寸)
    - [固有尺寸](#固有尺寸)
    - [设置具体尺寸](#设置具体尺寸)
      - [基本属性](#基本属性)
      - [min- 和 max- 前缀的属性](#min--和-max--前缀的属性)
  - [溢出](#溢出)
    - [overflow 属性](#overflow-属性)
    - [溢出会建立区块格式化上下文](#溢出会建立区块格式化上下文)
  - [变换](#变换)
    - [设置原点](#设置原点)
    - [变换函数](#变换函数)
      - [缩放](#缩放)
      - [旋转](#旋转)
      - [平移](#平移)
  - [过渡](#过渡)
    - [过渡对象](#过渡对象)
    - [过渡时间](#过渡时间)
    - [速率曲线](#速率曲线)
      - [贝塞尔曲线函数](#贝塞尔曲线函数)
    - [延迟](#延迟)
    - [属性缩写](#属性缩写)
  - [动画](#动画)
    - [自定义动画](#自定义动画)
    - [引用动画](#引用动画)
    - [动画时长](#动画时长)
    - [动画播放次数](#动画播放次数)
    - [往复运动动画](#往复运动动画)
    - [填充模式](#填充模式)
    - [简写属性](#简写属性-3)
- [6 CSS 的值与单位](#6-css-的值与单位)
  - [继承](#继承)
    - [控制继承](#控制继承)
    - [重设所有属性值](#重设所有属性值)
  - [长度单位](#长度单位)
    - [绝对长度](#绝对长度)
    - [相对长度](#相对长度)
    - [百分比](#百分比)
  - [颜色值](#颜色值)
    - [RGB 和 RGBA](#rgb-和-rgba)
    - [十六进制](#十六进制)
    - [HSL 和 HSLA](#hsl-和-hsla)
  - [calc() 函数](#calc-函数)
  - [特殊单位](#特殊单位)
- [7 CSS 布局](#7-css-布局)
  - [介绍](#介绍)
  - [常规流](#常规流)
  - [浮动](#浮动)
    - [背景介绍](#背景介绍)
    - [表现](#表现)
    - [清除浮动](#清除浮动)
      - [clearfix 方法](#clearfix-方法)
      - [overflow 方法](#overflow-方法)
      - [display:flow-root 方法](#displayflow-root-方法)
    - [区块格式化上下文（BFC）](#区块格式化上下文bfc)
  - [定位](#定位)
    - [静态定位](#静态定位)
    - [相对定位](#相对定位)
    - [绝对定位](#绝对定位)
      - [子绝父相](#子绝父相)
      - [z-index](#z-index)
    - [固定定位](#固定定位)
    - [粘性定位](#粘性定位)
      - [应用：滚动索引](#应用滚动索引)
  - [弹性盒子 (flex布局)](#弹性盒子-flex布局)
    - [flex 模型](#flex-模型)
    - [指定主轴的方向](#指定主轴的方向)
    - [换行](#换行)
    - [简写属性 flex-flow](#简写属性-flex-flow)
    - [调整 flex 项尺寸](#调整-flex-项尺寸)
      - [flex-grow](#flex-grow)
      - [flex-shrink](#flex-shrink)
      - [flex-basis](#flex-basis)
    - [水平与垂直对齐](#水平与垂直对齐)
      - [垂直方向](#垂直方向)
      - [水平方向](#水平方向)
    - [flex 项排序](#flex-项排序)
    - [跨浏览器兼容性](#跨浏览器兼容性)
  - [网格布局（grid布局）](#网格布局grid布局)
    - [grid 模型](#grid-模型)
    - [定义一个网格布局](#定义一个网格布局)
      - [repeat() 函数](#repeat-函数)
    - [网格间隙](#网格间隙)
    - [显式网格与隐式网格](#显式网格与隐式网格)
      - [minmax() 函数](#minmax-函数)
      - [应用：真正的响应式布局网格](#应用真正的响应式布局网格)
    - [根据网格线放入元素](#根据网格线放入元素)
    - [根据区域放入元素](#根据区域放入元素)
  - [多列布局](#多列布局)
    - [定义一个多列布局](#定义一个多列布局)
    - [添加样式](#添加样式)
    - [打印页面时的内容折断](#打印页面时的内容折断)
  - [传统的布局方法](#传统的布局方法)
    - [响应式两列布局](#响应式两列布局)
    - [传统响应式网格](#传统响应式网格)
      - [浮动网格的限制](#浮动网格的限制)
    - [弹性盒实现网格？](#弹性盒实现网格)
    - [第三方网格系统](#第三方网格系统)
- [8 响应式设计](#8-响应式设计)
  - [媒体查询](#媒体查询)
    - [媒体查询基础](#媒体查询基础)
    - [媒体类型](#媒体类型)
    - [媒体特征规则](#媒体特征规则)
      - [宽](#宽)
      - [分辨率（dpi）](#分辨率dpi)
      - [朝向](#朝向)
      - [有光标的设备](#有光标的设备)
    - [媒体特征条件之间的逻辑](#媒体特征条件之间的逻辑)
      - [与](#与)
      - [或](#或)
      - [非](#非)
    - [断点](#断点)
    - [移动优先？桌面优先？](#移动优先桌面优先)
    - [真的需要媒体查询吗？](#真的需要媒体查询吗)
  - [响应式布局](#响应式布局)
  - [响应式图像](#响应式图像)
  - [响应式排版](#响应式排版)
  - [视口元标签](#视口元标签)
- [9 浏览器兼容](#9-浏览器兼容)
  - [分析网站浏览器生态](#分析网站浏览器生态)
  - [查询浏览器是否支持特性](#查询浏览器是否支持特性)
  - [构建回滚实现兼容](#构建回滚实现兼容)
  - [优雅的回滚：特征查询](#优雅的回滚特征查询)
  - [跨浏览器测试（TODO）](#跨浏览器测试todo)
# 0 资源链接

- [CSS Snapshot 2023](https://www.w3.org/TR/css-2023/)
- [MDN-官方教程](https://developer.mozilla.org/zh-CN/docs/Web/CSS)
- [cssgradient-渐变背景在线生成](https://cssgradient.io/)
- [codepen-在线编码playground](https://codepen.io/)
- 网络字体资源：
  - [fontsquirrel](https://www.fontsquirrel.com/)
  - [dafont](https://www.dafont.com/)
  - [everythingfonts](https://everythingfonts.com/)
  - [Google Font](https://www.google.com/fonts)
- [Bootstrap-CSS框架](https://getbootstrap.com/)
- [Foundation-CSS框架](https://get.foundation/)
- [Skeleton-CSS框架](http://getskeleton.com/)
- [Startcounter-查询站点用户数据、查询设备市占率](http://gs.statcounter.com/)
- [Can I Use-查询浏览器对特性的支持情况](https://caniuse.com/)
- [clippy-在线生成裁切背景代码](https://bennettfeely.com/clippy/)
- [linea-免费的icon](https://linea.io/)
- [sizzy-在线测试网页响应式效果](https://sizzy.co/)

# 1 CSS 介绍

CSS (Cascading Style Sheets)，层叠样式表，一种标记语言

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

#### :nth-of-type

将所有满足选择器要求的元素排序，按照这个排序，根据参数选取元素。

比如下面的第一个例子，找到所有的 p 元素，并选取它们中序号为 2n+1 的元素（序号从1开始，且n为从零开始递增的整数） 

```
/* 奇数段 */
p:nth-of-type(2n + 1) {}
p:nth-of-type(odd) {}

/* 偶数段 */
p:nth-of-type(2n) {}
p:nth-of-type(even) {}

/* 第一段 */
p:nth-of-type(1) {}
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

# 3 CSS 优先权

## CSS 层叠（级联）

当多个 css 规则同时运用在一个元素上时，会产生样式表的 ***层叠*** （Cascade），这是一个合并冲突样式的过程，如何判断哪个样式规则生效呢？主要从以下几个方面判断：

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

# 4 盒模型

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

# 5 CSS 样式

## 样式前缀

浏览器厂商们有时会给实验性的或者非标准的 CSS 属性和 JavaScript API 添加前缀，这样开发者就可以用这些新的特性进行试验，同时（理论上）防止他们的试验代码被依赖，从而在标准化过程中破坏 web 开发者的代码。开发者应该等到浏览器行为标准化之后再使用未加前缀的属性。

浏览器厂商们正在努力停止使用前缀来表示实验性质的代码的行为。Web 开发者一直在生产环境的网站上使用这些实验性代码，这使得浏览器厂商更难保证浏览器兼容性和处理新特性；这也伤害了更小众的浏览器，它们被迫添加其他浏览器前缀以加载热门网站。

现在的趋势是将实验性功能添加在需要用户自行设置偏好或标记（flag）的地方，同时编写一个更小规模的规范，以更快达到稳定状态。

### 主流浏览器引擎前缀

- -webkit- （谷歌，Safari，新版 Opera 浏览器，以及几乎所有 iOS 系统中的浏览器（包括 iOS 系统中的火狐浏览器）；基本上所有基于 WebKit 内核的浏览器）
- -moz- （火狐浏览器）
- -o- （旧版 Opera 浏览器）
- -ms- （IE 浏览器 和 Edge 浏览器）

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

### 背景裁切

- 剪切路径：clip-path
- polygon() 多边形函数，选择 n 个点，这 n 个点按顺序相连，得到裁切的背景
- [clip工具](https://bennettfeely.com/clippy/)

```
clip-path: polygon(0 0, 100% 0, 100% 80%, 0 100%);
```

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

#### 文本缩进

text-indent，段落首行缩进

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

### 网络字体

#### 字体资源

- [fontsquirrel](https://www.fontsquirrel.com/)
- [dafont](https://www.dafont.com/)
- [everythingfonts](https://everythingfonts.com/)

#### 使用网络字体

下载ttf字体文件，通过[网络字体生成器](https://www.fontsquirrel.com/tools/webfont-generator)生成工具包，将工具包内的 stylesheet.css 文件（ @font-face 代码块 ）导入 html，或者复制到 css 内，便可以通过 font-family 属性在 css 中使用网络字体（字体名称在 stylesheet.css 中）

关于 @font-face 的细节：

```
@font-face {
  font-family: "ciclefina";
  src: url("fonts/cicle_fina-webfont.eot");
  src:
    url("fonts/cicle_fina-webfont.eot?#iefix") format("embedded-opentype"),
    url("fonts/cicle_fina-webfont.woff2") format("woff2"),
    url("fonts/cicle_fina-webfont.woff") format("woff"),
    url("fonts/cicle_fina-webfont.ttf") format("truetype"),
    url("fonts/cicle_fina-webfont.svg#ciclefina") format("svg");
  font-weight: normal;
  font-style: normal;
}
```

- font-family：这一行指定了你想要引用的字体的名称。
- src：这些行指定要导入到你的 CSS(url部分) 的字体文件的路径，以及每种字体文件的格式 (format部分)。后面的部分不是必要的，但是声明它是很有用的，因为它允许浏览器更快地找到可以使用的字体。可以列出多个声明，用逗号分隔——浏览器会搜索并使用它能找到的第一个——因此，最好是把新的、更好的格式比如 WOFF2 放在前面，把偏老的，不是那么好的格式像 TTF 这样的放在后面。
- font-weight/font-style: 这些行指定字体的粗细，以及它是否斜体。如果你正在导入相同字体的多个粗细，你可以指定它们的粗细/样式，然后使用不同的font-weight/font-style来选择它们之间的不同值，而不必调用字体种类不同名称的所有不同成员。

#### 在线字体服务

[Google Font](https://www.google.com/fonts)

## 列表

### 符号样式

用于 ul 或 ol，如下例子，设置列表项前的符号为大写罗马数字

```
ol {
  list-style-type: upper-roman;
}
```

### 符号位置

用于 ul 或 ol，如下例子，默认值为 outside，这使项目符号位于列表项之外，设置列表项前的符号在行内。

```
ol {
  list-style-position: inside;
}
```

### 自定义符号图片

用于 ul 或 ol，可以自定义符号为指定的图片

```
ul {
  list-style-image: url(star.svg);
}
```

此属性无法控制图片的位置、大小，建议使用 background 属性设置符号图片:

```
ul li {
  padding-left: 2rem;
  background-image: url(star.svg);
  background-position: 0 0;
  background-size: 1.6rem 1.6rem;
  background-repeat: no-repeat;
}
```

### 简写属性

```
ul {
  list-style-type: square;
  list-style-image: url(example.png);
  list-style-position: inside;
}
```

简写为

```
ul {
  list-style: square url(example.png) inside;
}
```

### 自定义计数规则

CSS 提供了自定义编号的方法，参考以下关键词：

- @counter-style
- counter-increment
- counter-reset

## 链接

### 链接状态

每个链接状态对应一个伪类，因此可以通过伪类为某个状态设定特殊的样式

- Link：有目的地的链接（即不只是一个具名锚点），使用 :link 伪类来应用样式。
- Visited：已访问过（存在于浏览器历史记录中）的链接，使用 :visited 伪类来应用样式。
- Hover：被用户鼠标指针悬停的链接，使用 :hover 伪类来应用样式。
- Focus：被选中的链接（比如通过键盘的 Tab 移动到这个链接，或者使用像 HTMLElement.focus() 这样的方法编程地聚焦链接），使用 :focus 伪类来应用样式。
- Active：激活（如点击）的链接，使用 :active 伪类来应用样式。

### 默认样式

- 链接以下划线表示。
- 未访问链接为蓝色。
- 已访问链接为紫色。
- 悬停链接时，鼠标指针会变成一个小手图标。
- 聚焦链接的周围有一个轮廓——按下键盘上的制表符键，就能聚焦本页面上的链接。（在 Mac 上，需要使用 option + tab，或通过按下 Ctrl + F7 启用全键盘控制选项。
- 活动链接为红色。尝试在点击链接时按住鼠标键。

### 伪类顺序

对同一个链接，设置多个伪类时，第一个规则的样式也会在后面的规则中生效，比如一个链接被激活的时候，它也是处于悬停状态的。如果你搞错了顺序，那么就可能不会产生正确的效果。

顺序口诀：LoVe Fears HAte

即 :link :visited :focus :hover :active

### 轮廓

outline 属性可以设置元素的轮廓，元素轮廓是绘制于元素周围的一条线，位于 border 的外围，使元素突出

border 和 outline 很类似，但有如下区别：

- outline 不占据空间，绘制于元素内容周围。
- 根据规范，outline 通常是矩形，但也可以是非矩形的。
- outline-offset: 3px; 可以设置轮廓与内容的间隙

```
outline: 1px dashed red;
```

可以看出，outline 是下面三个样式的简写：

- outline-style，轮廓样式
- outline-width，轮廓宽度
- outline-color，轮廓颜色

### 光标悬停样式

鼠标指针悬停在元素上时显示相应样式，如下例子将指针设为小手

```
cursor: pointer;
```

### 应用：链接中加入图标

如下，实现效果：在链接文字后紧跟着一个小图标

```
a[href^="http"] {
  background: url("external-link-52.png") no-repeat 100% 0;
  background-size: 16px 16px;
  padding-right: 19px;
}
```

选择拥有 href 属性且属性值以 http 开头的元素，设置一个背景，不重复，距离左边为父元素的 100%，距离顶部为 0

### 应用：样式化链接为按钮（TODO）

## 调整尺寸

### 固有尺寸

使用 \<img> 标签，且 CSS 中没有设置其尺寸，那么将使用其固有尺寸显示

块级元素的固有尺寸（内部没有内容时），高度为 0，宽度为父元素的 100%

### 设置具体尺寸

#### 基本属性

使用 width, height 属性设置宽高

#### min- 和 max- 前缀的属性

例如设置一个 min-height 属性。盒子就会一直保持大于这个最小高度，但是如果有比这个盒子在最小高度状态下所能容纳的更多内容，那么盒子就会变大。

对 \<img> 使用 max-width: 100%，图像可以变得比固有尺寸更小，但是不会大于固有尺寸的 100%。这样做的目的是，在没有足够空间以原有宽度展示图像时，让图像缩小，同时确保它们不会比 max-width 的宽度大。

## 溢出

元素内的内容过多时会产生溢出。

现代网页布局的方式可以很好地处理溢出。但是在以往，开发者会更多地使用固定高度，尽力让毫无关联的盒子的底部对齐。这是很脆弱的，一些盒子，它们的内容遮到了页面上的其他内容。这就是溢出，理论上你应该能重新排布这些布局，使得它不必依赖于盒子尺寸的调整。

在开发网站的时候，你应该一直把溢出的问题挂在心头，你应该用或多或少的内容测试设计，增加文本的字号，确保你的 CSS 可以正常地协调。改变溢出属性的值，来隐藏内容或者增加滚动条，会是你仅仅在少数特别情况下需要的，例如在你确实需要一个可滚动盒子的时候。

### overflow 属性

overflow 属性是你控制一个元素溢出的方式，可以取以下值：

- visible，默认值，溢出内容可见
- hidden，隐藏溢出内容
- scroll，溢出内容滚动可见，`overflow-y: scroll` 仅在 y 轴滚动
- auto，浏览器自动控制，一般是内容溢出时再显示滚动条

属性的简写：overflow: scroll hidden 会把 overflow-x 设置成 scroll，而 overflow-y 则为 hidden

如果需要在小盒子里面和长英文词打交道，可以了解一下 word-break 或者 overflow-wrap 属性

### 溢出会建立区块格式化上下文

在你使用诸如 scroll 或者 auto 的时候，你就建立了一个区块格式化上下文（Block Formatting Context）。结果就是，你改变了 overflow 的值的话，对应的盒子就变成了更加小巧的状态。在容器之外的东西没法混进容器内，也没有东西可以突出盒子，进入周围的版面。

## 变换

CSS 变换（CSS transform）可以在 ***不影响正常文档流*** 的情况下改变作用内容的位置

***只有使用盒模型的元素可以被变换***

两个主要属性：

- transform-origin。指定原点的位置。默认值为元素的中心，可以被移动。很多变换需要用到这个属性，比如旋转、缩放和倾斜，它们都需要一个指定的点作为参数。
- transform。指定作用在元素上的变换。取值为空格分隔的一系列变换的列表，它们会像被组合操作请求一样被分别执行。复合变换按从右到左的顺序高效地应用。

### 设置原点

原点在中心：

```
transform-origin: center;
```

原点在左上角：

```
transform-origin: top left;
```

原点距离左边50px，距离上边50px：

```
transform-origin: 50px 50px;
```

### 变换函数

transform的属性是各种变换函数

```
transform: scale(2, 0.5);
```

可以省略 transform，以上代码等价于：

```
scale: 2 0.5;
```

#### 缩放

x,y方向同时放大两倍（等比例缩放）：

```
scale: 2;
```

x轴方向放大2倍，y轴缩小到0.5：

```
scale: 2 0.5;
```

#### 旋转

顺时针旋转 90 度（默认以 z 轴为旋转轴）：

```
rotate: 90deg;
```

#### 平移

沿着x轴向右移动自身宽度的50%:

```
translate: 50%;
```

沿着x轴向右移动 20px，沿着y轴向下平移 20px:

```
translate: 20px 20px;
```

沿着z轴移动30px（等比缩放的效果）:

```
translate: 0 0 30px;
```

## 过渡

CSS 过渡提供了一种在更改 CSS 属性时控制动画速度的方法

通常将两个状态之间的过渡称为隐式过渡，因为开始与结束之间的状态由浏览器决定

### 过渡对象

如下，指定 margin-right 为过渡对象，只有此属性值变化时会有动画效果

```
transition-property: margin-right;
```

可以使用属性值 all 指定所有属性

### 过渡时间

指定过渡动画的时长为 1s

```
transition-duration: 1s
```

### 速率曲线

可以为过渡设置动画速率曲线：

```
transition-timing-function: ease
```

- ease - 规定过渡效果，先缓慢地开始，中间加速，然后缓慢地结束（默认）
- linear - 规定从开始到结束具有相同速度的过渡效果
- ease-in -规定缓慢开始的过渡效果
- ease-out - 规定缓慢结束的过渡效果
- ease-in-out - 规定开始和结束较慢的过渡效果（中间不会变快，中间是一段匀速）
- cubic-bezier(p0,p1,p2,p3) - 允许您在三次贝塞尔函数中定义自己的值

#### 贝塞尔曲线函数

```
cubic-bezier(p0,p1,p2,p3)
```

[图解贝塞尔曲线](https://www.runoob.com/wp-content/uploads/2019/10/cubic-bezier-02.jpg)

p0默认是(0,0)，p3默认是(1,1)

我们需要关注的是 P1 和 P2 两点的取值，而其中 X 轴的取值范围是 0 到 1，当取值超出范围时 cubic-bezier 将失效；Y 轴的取值没有规定，当然也毋须过大。

最直接的理解是，将以一条直线放在范围只有 1 的坐标轴中，并从中间拿出两个点来拉扯（X 轴的取值区间是 [0, 1]，Y 轴任意），最后形成的曲线就是动画的速度曲线。

### 延迟

等待 3s 后再执行过渡动画：

```
transition-delay: 3s
```

### 属性缩写

```
transition: <property> <duration> <timing-function> <delay> <iteration-count> <direction> <fill-mode> <play-state> <name>;
```

## 动画

CSS animations 使得可以将从一个 CSS 样式配置转换到另一个 CSS 样式配置。动画包括两个部分：描述动画的样式规则和用于指定动画开始、结束以及中间点样式的关键帧。

CSS 动画主要优点：

- 能够非常容易地创建简单动画，你甚至不需要了解 JavaScript 就能创建动画。
- 动画运行效果良好，甚至在低性能的系统上。渲染引擎会使用跳帧或者其他技术以保证动画表现尽可能的流畅。而使用 JavaScript 实现的动画通常表现不佳（除非经过很好的设计）。
- 让浏览器控制动画序列，允许浏览器优化性能和效果，如降低位于隐藏选项卡中的动画更新频率。

### 自定义动画

如下定义了一个名为 slidein 的动画，从自身原本位置开始移动，终点位于距离原本位置 100% 的右方：

```
@keyframes slidein {
  from {
    transform: translateX(0%);
  }

  to {
    transform: translateX(100%);
  }
}
```

和 转换 transition 相比，关键帧 keyframes 可以控制动画序列的中间步骤：

```
@keyframes identifier {
  0% {
    top: 0;
    left: 0;
  }
  30% {
    top: 50px;
  }
  68%,
  72% {
    left: 50px;
  }
  100% {
    top: 100px;
    left: 100%;
  }
}
```

- 可以自由定义任何数量的关键帧，例子中，top 属性分别出现在关键帧 0%、30% 和 100% 的中，而 left 属性分别出现在关键帧 0%、68%、72% 和 100% 中。
- 如果关键帧被重复定义（有两个50%），那么只会应用后边的关键帧

### 引用动画

```
animation-name: slidein
```

### 动画时长

```
animation-duration: 3s;
```

### 动画播放次数

无限循环播放：

```
animation-iteration-count: infinite;
```

### 往复运动动画

从终点回到起点的过程中也应用动画：

```
animation-direction: alternate;
```

### 填充模式

animation-fill-mode，决定动画开始前或结束后应用的样式

- none。当动画未执行时，动画将不会将任何样式应用于目标，而是已经赋予给该元素的 CSS 规则来显示该元素。这是默认值。
- forwards，动画结束时，保留动画最后一个关键帧的样式。
- backwards，在animation-delay期间，动画将使用第一个关键帧中定义的样式
- both，动画将同时使用 forwards 和 backwards 的规则

### 简写属性

```
animation: 时长 | 速率曲线 | 延迟 | 循环次数 | direction | fill-mode | play-state | 动画名称
```

[详细介绍](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation)

# 6 CSS 的值与单位

## 继承

有些 css 属性会被子元素继承（color），有些则不会（width）

### 控制继承

通过 *继承通用属性* 值来控制继承，每个属性都可以接收这些值：

1. inherit：继承父元素的属性值
2. initial：设置为初始值，比如 color 的初始值是黑色
3. revert：设置为浏览器默认样式，比如 \<a> 的 color 浏览器默认值为蓝色
4. revert-layer：设置为上一个级联层（ @layer ）中的属性值
5. unset：重置为自然值，如果属性是自然继承那么就是 inherit，否则和 initial 一样

### 重设所有属性值

将所有属性的值设为某一种继承属性值

```
.fix-this {
  all: unset;
}
```

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

- 可以使用 + - * / 运算符
- 如下例子，宽度设置为父元素的 30% 加上 100px
- 注意运算符左右要有空格

```
.box {
  width: calc(30% + 100px);
}
```

## 特殊单位

某些单位只在特定属性中使用

- 网格布局中的 fr
- 旋转函数中的 deg

# 7 CSS 布局

## 介绍

正常布局流（normal flow）是指在不对页面进行任何布局控制时，浏览器默认的 HTML 布局方式。

HTML 元素完全按照源码中出现的先后次序显示

块元素内容的布局方向被描述为 ***块方向***，***内联方向*** 是内联内容（如句子）的运行方向，块方向默认是垂直，内联方向默认是水平，通过书写模式属性可以改变

设置某些 CSS 会覆盖默认的布局行为：

- display 属性
- float 属性
- position 属性
- 表格布局。表格的布局方式可以用在非表格内容上，可以使用 display: table 和相关属性在非表元素上使用。
- 多列布局。Multi-column layout 属性可以让块按列布局，比如报纸的内容就是一列一列排布的。

## 常规流

块元素特性：

- 块元素默认会填满父元素 100% 宽度
- 块元素的默认 总宽/高 = 内容宽/高 + 内边距宽/高 + 边框宽/高
- 块元素默认内容区高度（height）是子元素的总高度（包括 height padding border margin）
- 块元素会在上个元素下面另起一行
- 块元素之间会有外边距折叠现象，即大的外边距会覆盖小的外边距 

行元素特性：

- 行元素会与相邻的行元素在同一行上，如果溢出会自动换行
- 行元素的宽高属性失效，宽高依赖于文字内容大小
- 行元素垂直方向的内边距、边框会生效，但是不占位
- 行元素垂直方向的外边距不生效
- 行元素水平方向的内边距、外边距、边框会生效，且占位

## 浮动

### 背景介绍

最初，浮动用于在文本中插入图片，使文本环绕在图片周围，也可以实现首字下沉的效果（drop-cap），[首字下沉例子](https://css-tricks.com/snippets/css/drop-caps/)，使用 :first-letter 选择器选取第一个字母

后来，浮动被应用于界面的布局，它可以使得元素横向排列

### 表现

以文本环绕块元素为例，看看浮动发生了什么？

```
<div class="out">
  <div class="box">Float</div>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam
    dolor
  </p>
</div>
```

- 给 box 块元素设置 `float:left` 属性，浮动会使元素脱离常规流（normal flow），并吸附到父容器（ out 元素）的左边，常规流布局的元素（p 元素）如果之前在其下面，那么文字会上移并填满其右侧空间
- p 元素行内盒子已被缩短，故文字会排布在浮动元素周围，但是浮动元素从正常文档流移出，故p 元素行内盒子仍然保持全部宽度
- 因为浮动，无论 box 元素有多高，也不会再撑大其父元素（out 元素），out 元素的高度仅由 p 元素决定
- 如果以电脑屏幕为 x y 轴平面，那么 z 轴方向就是眼睛和屏幕相连的方向，浮动的元素就好像沿着 z 轴移动，离屏幕越远了，并且离眼睛更近了，因此浮动元素之后的块元素会被浮动元素覆盖。

### 清除浮动

浮动的影响：

- 浮动元素的父元素高度不会被撑大，高度为 0，会影响下方的常规流布局（下方块元素会向上塌陷）


#### clearfix 方法

设置 clear 属性的元素会移除它受到的浮动影响，并且之后的元素也不会再受到浮动影响

```
.cleared {
  clear: left;
}
```

clear 属性接受下列值：

- left：停止任何活动的左浮动
- right：停止任何活动的右浮动
- both：停止任何活动的左右浮动

clearfix 方法：向包含浮动内容及其本身的盒子后方插入一些生成的内容，并将生成的内容清除浮动。这与在浮动盒子后手动添加诸如 div 的 HTML 元素，并设置其样式为 clear:both 是等效的。这样，可以通过给浮动元素的父元素设置样式类，方便地清除浮动

```
.clearfix::after {
  content: "";
  clear: both;
  display: block;
}
```

更优的写法：

```
.clearfix::before,
.clearfix::after {
  content: '';
  clear: both;
  display: table;
}
```

添加 before 伪元素，并且使用 table 的原因：

> The use of `table` rather than `block` is only necessary if using `:before` to contain the top-margins of child elements.

案例：

[在线演示](https://codepen.io/allan1in/pen/OJemXoQ)

```
<div class="box-wrapper clearfix">
  <div class="box">float box</div>
  <div class="box">float box</div>
  <div class="normal-box">normal box</div>
</div>
```

```
.clearfix::before,
.clearfix::after {
  content: '';
  clear: both;
  display: table;
}

.box-wrapper {
  background-color: orange;
}

.box {
  float: left;
  height: 40px;
  background-color: grey;
  margin: 20px;
}

.normal-box {
  height: 40px;
  background-color: grey;
  width: 200px;
  margin-left: 300px;
  margin-top: 20px;
}
```

尝试着改变 clearfix 的写法，会发现如果缺少了 `::before`，或者使用 `display:block`，非浮动元素 normal-box 的上边距会塌陷

#### overflow 方法

一个替代的方案是将浮动元素父元素的 overflow 属性设置为除 visible 外的其他值，比如 `overflow:auto`

这个例子之所以能够生效，是因为创建了所谓的 块格式化上下文（BFC）。可以把它看作页面内部包含所需元素的一小块布局区域。如此设置可以让浮动元素包含在 BFC 及其背景之内。

缺点：

- 大部分情况下这种小技巧都可以奏效，但是可能会出现莫名其妙的滚动条或裁剪阴影，这是使用 overflow 带来的一些副作用
- 不利于代码的维护，难以理解

#### display:flow-root 方法

一个较为现代的方案是使用 display 属性的 flow-root 值（根元素流式布局）。它可以无需小技巧来创建块格式化上下文（BFC），在使用上没有副作用。

该元素生成一个块级元素盒，其会建立一个新的区块格式化上下文，定义格式化上下文的根元素

你可以从 flow-root 这个值的名字上看出来，它创建一个新的用于流式布局的上下文，行为如同  \<html> 元素。

### 区块格式化上下文（BFC）

区块格式化上下文（Block Formatting Context，BFC）是 Web 页面的可视 CSS 渲染的一部分，是块级盒子的布局过程发生的区域，也是浮动元素与其他元素交互的区域。

格式化上下文影响布局，通常，我们会为定位和清除浮动创建新的 BFC，而不是更改布局，因为它将：

- 包含内部浮动
- 排除外部浮动
- 阻止外边距重叠

[详细介绍](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_display/Block_formatting_context)

## 定位

定位会覆盖默认的常规流

### 静态定位

静态定位是每个元素的默认值，它只是意味着“将元素放入它在文档布局流中的正常位置

```
position: static;
```

### 相对定位

相对元素本来的位置，使用 top，bottom，left 和 right 属性移动元素位置

```
position: relative;
```

### 绝对定位

绝对定位的元素不再存在于正常文档布局流中。相反，它坐在它自己的层独立于一切。这是非常有用的：这意味着我们可以创建不干扰页面上其他元素的位置的隔离的 UI 功能。例如，弹出信息框和控制菜单；翻转面板；可以在页面上的任何地方拖放的 UI 功能

```
position: absolute;
```

#### 子绝父相

如果所有的父元素都没有显式地定义 position 属性，那么所有的父元素默认情况下 position 属性都是 static，这样，绝对定位元素会被包含在 **初始块容器** 中。这个初始块容器有着和浏览器视口一样的尺寸，并且 \<html> 元素也被包含在这个容器里面

给父元素设置 `position: relative;` 属性，可以给子元素设置 `position: absolute;` ，改变 **定位上下文** ，这样，子元素会以父元素为基准进行定位

#### z-index

当有多个元素设置了绝对定位，它们会产生重叠现象，可以通过设置 z-index 属性决定元素的覆盖关系

默认情况下，定位的元素都具有 z-index 为 auto，实际上为 0，其属性值只能接受整数值，z-index 值大的覆盖值小的元素

### 固定定位

元素会保持在窗口的固定位置上，无论如何滚动页面

```
position: fixed;
```

### 粘性定位

相对定位 和 绝对定位的混合，它允许被定位的元素表现得像相对定位一样，直到它滚动到某个阈值点（例如，从视口顶部起 10 像素）为止，此后它就变得固定了。

top 属性设置距离视口顶部的阈值，left 属性设置距离视口左边的阈值

```
position: sticky;
```

#### 应用：滚动索引

在正常布局流中，\<dt>元素将随内容滚动。当我们在 \<dt> 元素上添加position: sticky，并将top的值设置为 0，当标题滚动到视口的顶部时，支持此属性的浏览器会将标题粘贴到那个位置。随后，每个后续标题将替换前一个标题，直到它向上滚动到该位置

```
<h1>Sticky positioning</h1>

<dl>
  <dt>A</dt>
  <dd>Apple</dd>
  <dd>Ant</dd>
  <dd>Altimeter</dd>
  <dd>Airplane</dd>
  <dt>B</dt>
  <dd>Bird</dd>
  <dd>Buzzard</dd>
  <dd>Bee</dd>
  <dd>Banana</dd>
  <dd>Beanstalk</dd>
  <dt>C</dt>
  <dd>Calculator</dd>
  <dd>Cane</dd>
  <dd>Camera</dd>
  <dd>Camel</dd>
</dl>
```

```
dt {
  background-color: black;
  color: white;
  padding: 10px;
  position: sticky;
  top: 0;
  left: 0;
  margin: 1em 0;
}
```

## 弹性盒子 (flex布局)

长久以来，CSS 布局中唯一可靠且跨浏览器兼容的创建工具只有 floats 和 positioning。这两个工具大部分情况下都很好使，但是在某些方面它们具有一定的局限性，让人难以完成任务

弹性盒子的真正价值可以体现在它的灵活性/响应性，如果你调整浏览器窗口的大小，或者增加一个 flex 项，这时的布局仍旧是好的。

### flex 模型

[flex 模型](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Flexbox/flex_terms.png)

- 主轴（main axis）是沿着 flex 元素放置的方向延伸的轴（比如页面上的横向的行、纵向的列）。该轴的开始和结束被称为 main start 和 main end。
- 交叉轴（cross axis）是垂直于 flex 元素放置方向的轴。该轴的开始和结束被称为 cross start 和 cross end。
- flex 容器（flex container）：设置了 display: flex 的父元素
- flex 项（flex item）：在 flex 容器中表现为弹性的盒子的元素

### 指定主轴的方向

它可以指定主轴的方向——它默认值是 row，这使得 flex 项 在按你浏览器的默认语言方向排成一行（在英语/中文浏览器中是从左到右）

```
flex-direction: column;
```

这会将 flex 项 设置为列布局：所有 flex 项 竖着排成一列

还可以使用 row-reverse 和 column-reverse 值反向排列 flex 项

### 换行

给 flex 容器设置：

```
flex-wrap: wrap;
```

给 flex 项设置（意味着每个声明将至少为 200px 宽）：

```
flex: 200px;
```

这样当 flex 项 过多时不会溢出，会自动换到下一行

### 简写属性 flex-flow

```
flex-flow: row wrap;
```

等价于：

```
flex-direction: row;
flex-wrap: wrap;
```

### 调整 flex 项尺寸

此属性是以下 CSS 属性的简写：

- flex-grow
- flex-shrink
- flex-basis

#### flex-grow

给每个 flex 项添加以下属性（相当于 flex-grow），它们会等分排布：

```
flex: 1;
```

这是一个无单位的比例值，表示每个 flex 项沿主轴的可用空间大小。它是一个比例，这意味着将每个 flex 项的设置为 400000 的效果和 1 的时候是完全一样的

#### flex-shrink

指定了 flex 元素的收缩规则。flex 元素仅在默认宽度之和大于容器的时候才会发生收缩，其收缩的大小是依据 flex-shrink 的值（整数比例值，默认为 1 ），值越大收缩的越多

#### flex-basis

你还可以指定 flex 的最小值：

```
flex: 1 200px;
```

这表示，每个 flex 项将首先给出 200px 的可用空间（flex-basis），然后，剩余的可用空间将根据分配的比例共享

### 水平与垂直对齐

#### 垂直方向

给 flex 容器设置 align-items 控制所有 flex 项在交叉轴（垂直方向）上的对齐方式。

- 默认值是 stretch，其会使所有 flex 项沿着交叉轴的方向拉伸以填充父容器。如果父容器在交叉轴方向上没有固定宽度（即高度），则所有 flex 项将变得与最长的 flex 项一样长（即高度保持一致）
- center 值会使这些项保持其原有的高度，但是会在交叉轴（垂直方向）居中。
- flex-start 或 flex-end 使 flex 项在交叉轴的开始或结束处对齐所有的值。查看 [align-items](https://developer.mozilla.org/zh-CN/docs/Web/CSS/align-items) 了解更多。

你可以给某一个 flex 项设置 align-self 属性，以覆盖 align-items 的行为，这样使能够某一个 flex 项应用其他的对齐方式

#### 水平方向

justify-content 控制 flex 项在主轴上的位置。

- 默认值是 flex-start，这会使所有 flex 项都位于主轴的开始处
- 你也可以用 flex-end 来让 flex 项到结尾处
- center，可以让 flex 项在主轴居中。
- space-around，会使所有 flex 项沿着主轴均匀地分布，在任意一端都会留有一点空间。
- space-between，它和 space-around 非常相似，只是它不会在两端留下任何空间。

### flex 项排序

弹性盒子也有可以改变 flex 项的布局位置的功能，而不会影响到源顺序（即 dom 树里元素的顺序）。这也是传统布局方式很难做到的一点。

给某个 flex 项设置：

```
order: 1;
```

- 所有 flex 项默认的 order 值是 0。
- order 值大的 flex 项比 order 值小的在显示顺序中更靠后。
- 相同 order 值的 flex 项按源顺序显示（位置越靠前顺序越靠前）。所以假如你有四个元素，其 order 值分别是 2，1，1 和 0，那么它们的显示顺序就分别是第四，第二，第三，和第一。第三个元素显示在第二个后面是因为它们的 order 值一样，且第三个元素在源顺序中排在第二个后面。
- 可以给 order 设置负值使它们比值为 0 的元素排得更前面

### 跨浏览器兼容性

大多数浏览器都支持弹性盒子，诸如 Firefox、Chrome、Opera、Microsoft Edge 和 IE 11，较新版本的 Android/iOS 等等。但是你应该要意识到仍旧有被人使用的老浏览器不支持弹性盒子（或者支持，但是只是支持非常非常老版本的弹性盒子）。

弹性盒子相较其他一些 CSS 特性可能更为棘手。例如，如果浏览器缺少 CSS 阴影，则该网站可能仍然可用。但是假如不支持弹性盒子功能就会完全打破布局，使其不可用。

## 网格布局（grid布局）

### grid 模型

[grid 模型](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Grids/grid.png)

- 列（column）
- 行（row）
- 沟槽（gutter）：行与行、列与列之间的间隙

### 定义一个网格布局

如下，定义了网格布局，并且添加了三个宽度为200px的列

```
display: grid;
grid-template-columns: 200px 200px 200px;
```

使用 fr 单位响应式定义布局列，如下，会生成等分的三列：

```
grid-template-columns: 1fr 1fr 1fr;
```

#### repeat() 函数

第一个参数是重复次数，第二个参数是重复的值，可以使用 repeat() 简写以上的属性：

```
grid-template-columns: repeat(3, 1fr);
```

```
grid-template-columns: repeat(2, 2fr 1fr);

/* 相当于以下属性 */

grid-template-columns: 2fr 1fr 2fr 1fr；
```

关于第一个参数的特殊属性值：

- auto-fill，浏览器会根据每个

### 网格间隙

可以使用 grid-column-gap 属性来定义列间隙；使用 grid-row-gap 来定义行间隙，设置 grid-gap 可以同时定义列间隙和行间隙属性，如下：

```
grid-gap: 20px;
```

gap属性曾经有一个grid-前缀，不过后来的标准进行了修改，目的是让他们能够在不同的布局方法中都能起作用。尽管现在这个前缀不会影响语义，但为了代码的健壮性，你可以把两个属性都写上：

```
grid-gap: 20px;
gap: 20px;
```

### 显式网格与隐式网格

显式网格是我们用 grid-template-columns 或 grid-template-rows 属性创建的。而隐式网格则是当有内容被放到网格外时才会生成的（可以理解为每一行的高度/每一列的宽度）。显式网格与隐式网格的关系与弹性盒子的 main 和 cross 轴的关系有些类似。

隐式网格中生成的 行/列 大小是参数默认是 auto ，大小会根据放入的内容自动调整。比如，你只设置 grid-template-columns 而不设置 grid-template-rows，浏览器会自动按照内容高度设置每一行的高度。当然，你也可以使用 grid-auto-rows 和 grid-auto-columns 属性手动设定隐式网格轨道的高度。

#### minmax() 函数

可以设置行/列隐式网格的最小高/宽度，如下，行尺寸就至少为 100 像素，并且如果内容尺寸大于 100 像素则会根据内容自动调整

```
grid-auto-rows: minmax(100px, auto);
```

特殊取值：

- max-content，表示网格的轨道长度自适应内容最大的那个单元格。
- min-content，表示网格的轨道长度自适应内容最小的那个单元格。
- auto，作为最大值时，等价于 max-content。作为最小值时，它表示轨道中单元格最小长宽 (由min-width/min-height) 的最大值。

如果 最大值 < 最小值，则最大值被忽略并且 minmax(最小值, 最大值) 被看成最小值。\<flex>（fr值） 作为最大值时设置网格轨道的弹性系数；作为最小值时无效。

#### 应用：真正的响应式布局网格

```
grid-template-columns: repeat(auto-fill, minmax(min(200px, 100%), 1fr));
```

代码逻辑：

- 代码做了什么？为容器设置了 n 列网格
- n 如何确定？通过 repeat() 函数决定列数
- 列数如何确定？auto-fill 属性值会根据第二个参数（网格项的宽度），尽可能在每一行内放入更多的网格项
- 网格项的宽度如何确定？minmax() 函数定义了网格项宽度的最小值和最大值，\<flex>（fr值）作为最大值时设置网格轨道的弹性系数，而最小值由 min() 函数决定
- min() 函数如何确定网格项的最小值？如果网格项的宽度大于父容器的 100%，min() 函数会选取较小的值：100%，如果网格项的宽度小于父容器的 100%，min() 函数会选取较小的值：200px。这样避免了当网格项太宽时的溢出问题

效果：

- body 中放置了许多 div
- 每个 div 的宽度必须至少为 200px。如果右侧有额外空间（小于 200 像素），div 会展开以填充空间。
- 如果我们拓宽窗口宽度，一旦又有 200 像素的空间，就会在行中添加另一个 div。
- 当我们缩小窗口宽度时，一旦没有至少 200px 的空间可以容纳，行中的最后一个 div 就会进入下一行。一旦该 div 掉下去，其余的 div 就会展开以填满该行。
- 当我们继续缩小窗口宽度，直到小于 200px，这时 min() 函数起到作用，列的宽度会继续缩小，不会产生溢出

### 根据网格线放入元素

在定义完了网格之后，我们要把元素放入网格中。我们的网格中有许多分隔线，第一条线的起始点与文档书写模式相关。

在英文中，第一条列分隔线在网格的最左边而第一条行分隔线在网格的最上面。而对于阿拉伯语，第一条列分隔线在网格的最右边，因为阿拉伯文是从右往左书写的。

我们根据这些分隔线来放置元素，通过以下属性来指定从那条线开始到哪条线结束。

- grid-column-start
- grid-column-end
- grid-row-start
- grid-row-end

这些属性的值均为分隔线序号，你也可以用以下缩写形式来同时指定开始与结束的线。

- grid-column
- grid-row

元素从第一条网格线开始，到第三条网格线结束：

```
grid-column: 1 / 3;
```

元素在第二个网格项上（等同于 `grid-column: 2 / 3;` ）：

```
grid-column: 2;
```

元素从第一条网格线开始，跨越 2 个网格项：
```
grid-column: 1 / span 2;
```

### 根据区域放入元素

给父容器设置属性：

```
grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
```

给元素添加属性，放到定义的 header 区域：

```
header {
  grid-area: header;
}
```

grid-template-areas 属性的使用规则如下：

- 你需要填满网格的每个格子
- 对于某个横跨多个格子的元素，重复写上那个元素grid-area属性定义的区域名字
- 所有名字只能出现在一个连续的区域，不能在不同的位置出现
- 一个连续的区域必须是一个矩形
- 使用.符号，让一个格子留空

## 多列布局

多列布局声明提供了一种多列组织内容的方式，正如你在一些报纸中看到的那样

### 定义一个多列布局

如下，定义了一个三列布局，创建的这些列具有弹性的宽度，由浏览器计算出每一列分配多少空间

```
.container {
  column-count: 3;
}
```

如下，设置列宽方式创建多列，浏览器将按照你指定的宽度尽可能多的创建列；任何剩余的空间之后会被现有的列平分。这意味着你可能无法期望得到你指定宽度，除非容器的宽度刚好可以被你指定的宽度除尽

```
.container {
  column-width: 200px;
}
```

### 添加样式

使用 column-gap 改变列间间隙

```
.container {
  column-gap: 20px;
}
```

用 column-rule 在列间加入一条分割线，这条分割线本身并不占用宽度，它置于用 column-gap 创建的间隙内

```
.container {
  column-rule: 4px dotted rgb(79, 185, 227);
}
```

### 打印页面时的内容折断

当你 ctrl+p 打印页面时，由于打印分页，可能会折断一列上的内容，可以给列中的某一项设置以下属性：

```
break-inside: avoid;
page-break-inside: avoid;
```

这样如果此元素在一页上显示不全（会被页面分割），会自动移动到下一页上

旧属性 page-break-inside: avoid 能够获得更好的浏览器支持

## 传统的布局方法

### 响应式两列布局

html 结构：

```
html - body - div
            - div
```

css 代码：

```
body {
  width: 90%;
  max-width: 900px;
  margin: 0 auto;
}

div:nth-of-type(1) {
  width: 48%;
  float: left;
}

div:nth-of-type(2) {
  width: 48%;
  float: right;
}
```

在上面的代码中，实现了响应式的两列布局：

- 我们给 body 设置了最大宽度 900px，并且宽度为其父元素 html 的 90%，这样，无论怎么缩小窗口范围，body 的宽度一直是窗口的 90%，且无论窗口有多大，宽度不会超过 900px。
- 两个 div 的宽度也是百分数，所以也实现了响应式，并且为两列之间留下了 4% 的间隙

### 传统响应式网格

我们会使用浮动，构建一个有 12 列的表格，且有 13 个列间间隙（flex 中的 space-around 布局）。我们选择了 12 这个常见的数字，来看它对不同情景的适应情况，因为 12 可以被 6，4，3，和 2 完全整除

html 代码：

```
<div class="wrapper">
  <div class="row">
    <div class="col">1</div>
    <div class="col">2</div>
    <div class="col">3</div>
    <div class="col">4</div>
    <div class="col">5</div>
    <div class="col">6</div>
    <div class="col">7</div>
    <div class="col">8</div>
    <div class="col">9</div>
    <div class="col">10</div>
    <div class="col">11</div>
    <div class="col">12</div>
  </div>
  <div class="row">
    <div class="col span1">13</div>
    <div class="col span6">14</div>
    <div class="col span3">15</div>
    <div class="col span2">16</div>
  </div>
</div>
```

以上代码构建2行12列的网格，第一行中有12个元素，每个元素占1列格子，第二行中有4个元素，分别占：1、6、3、2列格子（总共占满12列格子）

css 代码：

```
* {
  box-sizing: border-box;
}

body {
  width: 90%;
  max-width: 980px;
  margin: 0 auto;
}

.wrapper {
  padding-right: 2.08333333%;
}

.row {
  clear: both;
}

.col {
  float: left;
  margin-left: 2.08333333%;
  width: 6.25%;
  background: rgb(255, 150, 150);
}
```

代码分析：

- 这里使用替代盒子模型（box-sizing: border-box;），使元素的宽度包含边框、内外边距，这样为的是可以通过设置边距，挤压内容区域的宽度
- body 设置了响应式的宽度，并且最大宽度为 980 px，为什么是 980px ？将每列的最大宽度设置为 60（共有 12 列），且将最大列间间隙设置为 20（共有 13 个间隙），加起来正好为 980，即 980 = 12 * 60 + 13 * 20，这样做是使用整数，方便计算
- 给父容器 wrapper 设置右边的内边距，这样做是为了补上最后的间隙，并且，每个列元素都有一个左外边距（共 12 个），这样一共有 13 个间隙。为什么是 2.08333333% ？为了响应式，需要计算每个间隙在上下文宽度中的占比，即 20 / 960 = 0.02083333333，960 是上下文宽度（980 的总宽度减去 20 的右内边距）
- 给每一行设置了清除浮动，这样我们不用在每行上都填充 12 列元素。行与行之间不会互相干扰，并保持分隔（哪怕上一行有空间，下一行的内容也不会移动到上一行）
- 给每一列设置浮动、间隙、宽度、背景。宽度如何计算的？60 / 960 = 0.0625

到此为止，已经完成了网格的初步搭建，如何将元素放置到网格中呢？

```
.col.span2 {
  width: calc((6.25% * 2) + 2.08333333%);
}
.col.span3 {
  width: calc((6.25% * 3) + (2.08333333% * 2));
}
.col.span4 {
  width: calc((6.25% * 4) + (2.08333333% * 3));
}
.col.span5 {
  width: calc((6.25% * 5) + (2.08333333% * 4));
}
.col.span6 {
  width: calc((6.25% * 6) + (2.08333333% * 5));
}
.col.span7 {
  width: calc((6.25% * 7) + (2.08333333% * 6));
}
.col.span8 {
  width: calc((6.25% * 8) + (2.08333333% * 7));
}
.col.span9 {
  width: calc((6.25% * 9) + (2.08333333% * 8));
}
.col.span10 {
  width: calc((6.25% * 10) + (2.08333333% * 9));
}
.col.span11 {
  width: calc((6.25% * 11) + (2.08333333% * 10));
}
.col.span12 {
  width: calc((6.25% * 12) + (2.08333333% * 11));
}
```

这里通过给元素设置以上定义的样式类（span2、span3......），实现元素的跨列。可以根据跨越的列数，计算得到元素宽度：(列宽度 * n) + (间隙宽度 * (n-1))

在标记中添加类以定义布局，意味着你的内容和标记与你的可视化表示相关联。你将会偶尔听到，这种使用 CSS 类的方式，被描绘成“无语义”：***描述了内容的外观，而不是描述内容的语义性的类的使用。*** 这是我们的span2、span3等类所面临的情况。

如何让元素向右偏移一列？

```
.offset-by-one {
  margin-left: calc(6.25% + (2.08333333% * 2));
}
```

通过给元素设置以上定义的样式类实现，当一个元素设置了这个类，此元素会向右偏移 1 列

#### 浮动网格的限制

- 使用时需要注意，元素跨越的列数不能超过网格定义的列数，如果一行中跨越的总列数大于定义的列数，那么后面的元素会被挤到下一行
- 如果元素内容比行宽，它会溢出
- 如果不设置一个确定的高度，很难自动控制元素高。这个方法很不灵活，它只有在你确定你的内容有个明确的高的情况下有用。

### 弹性盒实现网格？

弹性盒设计上是一维。它处理单个维度，行的或者列的。我们不能创建一个对行列严格要求的网格，意即如果我们要在我们的网格上使用弹性盒的话，我们仍然需要计算浮动布局的百分比。

在你的工程中，由于弹性盒相比浮动能提供附加的对齐和空间分布能力，你可能仍然选择使用弹性盒“网格”。但是你应该清楚，你仍然是在使用一个被设计用来做其他事情的工具。所以你可能觉得，这就像是在你抵达你想要的结果之前，让你跳过额外的坑。

### 第三方网格系统

- [Bootstrap](https://getbootstrap.com/)
- [Foundation](https://get.foundation/)
- [Skeleton](http://getskeleton.com/)

# 8 响应式设计

响应式网页设计（responsive web design，RWD），RWD 指的是允许 Web 页面适应不同屏幕宽度因素等，进行布局和外观的调整的一系列实践。

响应式 Web 设计不是单独的技术，它是描述 Web 设计的一种方式、或者是一组最佳实践的一个词，它是用来建立可以响应查看内容的设备的样式的一个词。

## 媒体查询


### 媒体查询基础

```
@media 媒体类型 and (媒体特征规则) {
  /* CSS rules go here */
}
```

它由以下部分组成：

- 一个媒体类型，告诉浏览器这段代码是用在什么类型的媒体上的（例如印刷品或者屏幕）；
- 一个媒体特征规则，是一个被包含的 CSS 生效所需的规则或者测试；
- 一组 CSS 规则，会在测试通过且媒体类型正确的时候应用。

### 媒体类型

你可以指定的媒体类型为：

- all，所有设备
- print，打印机设备
- screen，屏幕设备
- speech，语音识别设备

媒体类型是可选的，如果你没有在媒体查询中指示一个媒体类型的话，那么媒体查询默认会设为用于全部媒体类型。

### 媒体特征规则

#### 宽

当屏幕宽度正好等于 600px 时触发

```
@media screen and (width: 600px) {
  body {
    color: red;
  }
}
```

当屏幕宽度至少有 800px 时触发（大于等于 800px）

```
@media screen and (min-width: 800px) {
  .container {
    margin: 1em 2em;
  }
}
```

当屏幕宽度最大为 400px 时触发（小于等于 400px）

```
@media screen and (max-width: 400px) {
  body {
    color: blue;
  }
}
```

#### 分辨率（dpi）

当屏幕的分辨率大于 192dpi（dpi 表示一英寸192个点，192dpi 是苹果视网膜屏幕的 dpi，以此当作一个参考值） 时触发：

```
@media (min-resolution: 192dpi) {
  body {
    color: blue;
  }
}
```

#### 朝向

设备处于横放时触发

```
@media (orientation: landscape) {
  body {
    color: rebeccapurple;
  }
}
```

设备处于竖放时触发

```
@media (orientation: portrait) {
  body {
    color: rebeccapurple;
  }
}
```

#### 有光标的设备

用户使用有光标的设备时触发：

```
@media (hover: hover) {
  body {
    color: rebeccapurple;
  }
}
```

### 媒体特征条件之间的逻辑

#### 与

使用 and 表示与

```
@media screen and (min-width: 400px) and (orientation: landscape) {
  body {
    color: blue;
  }
}
```

#### 或

使用逗号表示或

```
@media screen and (min-width: 400px), screen and (orientation: landscape) {
  body {
    color: blue;
  }
}
```

#### 非

使用 not 表示非，直接反转了整个媒体查询的含义。因而在下面的例子中，文本只会在朝向为竖着的时候变成蓝色。

```
@media not all and (orientation: landscape) {
  body {
    color: blue;
  }
}
```

### 断点

引入媒体查询的点就叫做断点。

```
@media screen (min-width: 400px) {}
```

比如这个媒体查询的断点为 400px

如何确定断点？

- （不推荐）根据某些具体的设备决定，如：iphone\ipad 竖屏\ipad 横屏\macbook
- （较推荐）将类似的设备分类而决定，如：手机\平板横屏\平板竖屏\笔记本
- （推荐）根据你的页面布局决定断点，如：对于桌面优先开发，逐渐缩小屏幕宽度，直到布局出现问题，此处便是断点的位置

### 移动优先？桌面优先？

泛泛地说，你可以采用两种方式实现响应式设计。你可以从桌面或者最宽的视图开始，然后随着视口变得越来越小，加上断点，把物件挪开；你也可以从最小的视图开始，随着视口变得越来越大，增添布局内容。第二种方式被叫做移动优先的响应式设计，很多时候是最值得仿效的做法。

用在最小的那个设备上的视图很多时候都是一个简单的单列内容，很像正常文本流显示的那样。这意味着，你很可能不需要为小设备做多少布局设计，合适地安排下你的源代码，默认情况下你就可以得到可读的布局。

主要考虑以下几点：

- 用户主要在移动端还是桌面端
- 客户一般更喜欢桌面端的网页原型
- 移动端布局简单，开发迅速

### 真的需要媒体查询吗？

弹性盒、网格和多栏布局都给了你建立可伸缩的甚至是响应式组件的方式，而不需要媒体查询。这些布局方式能否在不加入媒体查询的时候实现你想要的设计，总是值得考虑的一件事。

例如，你可能想要一组卡片，至少为二百像素宽，并在主文章里尽可能多地放下这些二百像素的卡片。这可以用网格布局实现，而完全不使用媒体查询。

```
grid-template-columns: repeat(auto-fill, minmax(min(200px, 100%), 1fr));
```

## 响应式布局

最初，只能通过浮动实现网格，解决响应式布局问题：

- 浮动网格（早期时候使用）

后来出现了现代布局技术：

- 多列布局
- 弹性盒子
- 网格布局

## 响应式图像

最简单的响应式图像处理：

```
img {
  max-width: 100%;
}
```

max-width 可以限制图像的最大宽度，结合百分比属性值可以实现响应式图像，但这种方法有以下弊端：

- 图像有可能会显示得比它的原始尺寸小很多，以至于浪费带宽
- 有时候，你可能不想在移动端和桌面端有相同的图像宽高比例

后来的响应式图像，使用 \<picture> 元素和 \<img> 的 srcset 和 sizes 特性，很好地解决了这两个问题。HTML 中的响应式图像分为以下三种：

- DRP（设备像素比）越大，分辨率越大
- 图像尺寸越大，分辨率越大
- 美术风格：对于小屏设备，图像需要进行裁剪，从而突出图像内容主体

CSS 中也可以通过媒体查询实现响应式图像

## 响应式排版

响应式排版，是指实现响应式的字体。

例如，你可以通过媒体查询，在大屏幕上显示字体更大的标题，在小屏幕上显示较小的标题

或者，可以通过视口单位（vw）实现响应式排版：

```
h1 {
  font-size: 6vw;
}
```

但是这样会产生问题，因为文本总是随着视口的大小改变大小，用户失去了缩放任何使用 vw 单位的文本的能力。当视口过窄时，会出现标题比正文小的情况。***永远都不要只用 viewport 单位设定文本***

```
h1 {
  font-size: calc(1.5rem + 3vw);
}
```

以上是解决办法。使用了calc()，如果你将vw单位加到了使用固定大小（例如em或者rem）的值，那么文本仍然是可放缩的。

## 视口元标签
 
```
<meta name="viewport" content="width=device-width,initial-scale=1" />
```

这个元标签告诉移动端浏览器：

- width:可视区域的宽度为设备的宽度。
- intial-scale:页面首次被显示是可视区域的缩放级别，取值 1.0 则页面按实际尺寸显示，无任何缩放

元标签还可以设置以下值：

- minimum-scale：设定最小缩放级别。
- maximum-scale：设定最大缩放级别。
- user-scalable：如果设为 no 的话阻止缩放。

你应该避免使用minimum-scale、maximum-scale，尤其是将user-scalable设为no。用户应该有权力尽可能大或小地进行缩放，阻止这种做法会引起访问性问题。

为何需要 width=device-width？因为移动端浏览器倾向于在它们的视口宽度上说谎。原来 iPhone 发布以后，人们开始在小的手机屏幕上阅览网页，而大多数站点未对移动端做优化的缘故。移动端浏览器因此会把视口宽度设为 960 像素。通过设定 width=device-width，你用设备的实际宽度覆写了苹果默认的width=960px，然后你的媒介查询也会像预期那样生效。

# 9 浏览器兼容

## 分析网站浏览器生态

每个网站论目标用户都是不同的，在决定采用哪种优化方式之前，你需要查明使用旧浏览器浏览你的站点的用户的数量。可以在 [Startcounter](http://gs.statcounter.com/) 网站，查询用户访问数据

你应该考虑设备的类型和人们使用你的网站的方式。譬如，你的网站可能有超出平均数量的移动设备访问。或者，对于一些站点，无障碍和使用辅助性技术可能更加重要。开发者经常担心 1% 的使用旧版 IE 的用户的体验，而不去照顾多得多的有无障碍需求的用户。

## 查询浏览器是否支持特性

[Can I Use](https://caniuse.com/) 网站

了解你的用户浏览器支持的技术，这样你就可以很好地作出你的所有决定，知道最多能多好地支持所有用户。

## 构建回滚实现兼容

这是兼容旧浏览器最简单的方式，通过对 CSS 的覆写实现回滚

例如，浮动三个 \<div>，它们显示在了一行中，并同时对其父容器设置网格布局。任何使用不支持 CSS 网格布局的浏览器的人将会看到以浮动布局实现的一列盒子。一个成为了网格物件的浮动物件失去了浮动的动作，就是说通过把 wrapper 变成网格容器，浮动物件变成了网格物件。如果浏览器器支持网格布局，它会显示网格视图，否则它会忽略 display: grid 相关的属性，使用浮动布局。

## 优雅的回滚：特征查询

可以通过特征查询，判断一个属性在浏览器可不可以使用。如下，如果浏览器支持网格布局，那么会给每个网格项设置自动宽度

```
@supports (display: grid) {
  .item {
    width: auto;
  }
}
```

对于那些既不支持某些属性，也不支持特征查询的浏览器，只能通过构建回滚的方式实现兼容

## 跨浏览器测试（TODO）

详见[跨浏览器测试](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Cross_browser_testing)