
- [0 资源链接](#0-资源链接)
- [1 html介绍](#1-html介绍)
  - [文档结构](#文档结构)
  - [注释](#注释)
  - [\<!DOCTYPE html\>](#doctype-html)
  - [\<html\>](#html)
- [2 文档元数据标签](#2-文档元数据标签)
  - [\<title\>](#title)
  - [\<meta\>](#meta)
  - [\<link\>](#link)
    - [网站图标](#网站图标)
    - [引入CSS](#引入css)
  - [\<script\>](#script)
- [3 文本标签](#3-文本标签)
  - [\<h1\>](#h1)
  - [\<p\>](#p)
  - [\<span\>](#span)
  - [\<ul\>](#ul)
  - [\<ol\>](#ol)
  - [\<em\>](#em)
  - [\<strong\>](#strong)
  - [\<mark\>](#mark)
  - [\<b\>](#b)
  - [\<i\>](#i)
  - [\<u\>](#u)
  - [\<a\>](#a)
  - [\<dl\>](#dl)
  - [\<blockquote\>](#blockquote)
  - [\<q\>](#q)
  - [\<cite\>](#cite)
  - [\<abbr\>](#abbr)
  - [\<sup\>](#sup)
  - [\<sub\>](#sub)
  - [\<code\>](#code)
  - [\<pre\>](#pre)
  - [\<var\>](#var)
  - [\<kbd\>](#kbd)
  - [\<samp\>](#samp)
  - [\<time\>](#time)
- [4 结构布局标签](#4-结构布局标签)
  - [\<header\>](#header)
  - [\<nav\>](#nav)
  - [\<main\>](#main)
  - [\<aside\>](#aside)
  - [\<footer\>](#footer)
  - [\<article\>](#article)
  - [\<section\>](#section)
  - [\<address\>](#address)
  - [\<div\>](#div)
  - [\<br\>](#br)
  - [\<hr\>](#hr)
- [5 多媒体标签](#5-多媒体标签)
  - [\<img\>](#img)
    - [响应式图片](#响应式图片)
      - [不同尺寸](#不同尺寸)
      - [相同尺寸不同分辨率](#相同尺寸不同分辨率)
  - [\<picture\>](#picture)
    - [响应式加载图片（不同美术风格）](#响应式加载图片不同美术风格)
  - [\<figure\>](#figure)
  - [\<figcaption\>](#figcaption)
  - [\<video\>](#video)
  - [\<audio\>](#audio)
  - [\<source\>](#source)
  - [\<track\>](#track)
  - [\<iframe\>](#iframe)
  - [\<object\>](#object)
  - [\<embed\>](#embed)
  - [\<svg\>](#svg)
- [6 表格标签](#6-表格标签)
  - [\<table\>](#table)
  - [\<tr\>](#tr)
  - [\<td\>](#td)
  - [\<th\>](#th)
  - [\<colgroup\>](#colgroup)
  - [\<caption\>](#caption)
  - [\<thead\>](#thead)
  - [\<tbody\>](#tbody)
  - [\<tfoot\>](#tfoot)

# 0 资源链接

- [HTML Living Standard](https://html.spec.whatwg.org/)
- [html 转义字符速查表](https://css-tricks.com/snippets/html/glyphs/)
- [pixabay-免费图片](https://pixabay.com/)
- [unsplash-免费图片](https://unsplash.com/)
- [coverr-免费视频](https://coverr.co/)
- [easings-贝塞尔曲线代码](https://easings.net/)
- [cubic-bezier-自定义贝塞尔曲线](https://cubic-bezier.com/)

# 1 html介绍

html (HyperText Markup Language) 超文本标记语言

## 文档结构

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

## 注释

```
<!-- <p>我在注释内！</p> -->
```


## \<!DOCTYPE html>

历史遗留问题，用于声明文档类型

## \<html>

根元素，lang 属性设置语言，zh 或 en

# 2 文档元数据标签

元数据（Metadata）即保存文档相关信息的数据

## \<title>

HTML 文档的标题，收藏时的默认名称

`<title>Document</title>`

## \<meta>

元数据

1. 字符集

    `<meta charset="utf-8"/>`

2. 作者

    `<meta name="author" content="Chris Mills" />`

3. 描述
   
    网站描述信息，用于搜索引擎优化（ SEO ）

   `<meta name="description" content="The MDN Web Docs site" />`

4. 关键词
   
   关键词，用于SEO，由于开发者滥用，已被搜索引擎忽略

   `<meta name="keywords" content="fill, in, your, keywords, here">`

5. 元数据协议
   
   比如 Facebook 的 [Open Graph Data](https://ogp.me/) ，Twitter 的 [Twitter Cards](https://developer.x.com/en/docs/twitter-for-websites/cards/overview/abouts-cards) ，当使用协议的网址被分享在一些社交平台上时，社交平台可以抓取元数据的信息（此网页的图片、标题、介绍等）并展示，下面的例子使用了 Open Graph Data 协议，提供了网址的图片、介绍、标题信息。

    `<meta property="og:image" content="https://developer.mozilla.org/mdn-social-share.png" />`

    `<meta property="og:description" content="The Mozilla Developer Network (MDN) provides information about Open Web technologies including HTML, CSS, and APIs for both Web sites and HTML Apps." />`

    `<meta property="og:title" content="Mozilla Developer Network" />`

## \<link>

### 网站图标
   
图标一般为 .ico .png .gif 格式

动态图片作为图标：

`<link rel="icon" href="favicon.ico" type="image/x-icon" />`

`<link rel="icon" href="1.gif" type="image/gif" >`

静态图片做为图标：

`<link rel="shortcut icon" href="1.png" type="image/png" />`

关于 type 属性：

- 这个属性被用于定义链接的内容类型。属性值应该是类似于 text/html、text/css 这样的 MIME 类型
- MIME（多用途互联网邮件扩展）是一种用于描述除 ASCII 文本以外的其他格式文档的标准，例如音频、视频和图像。最初用于电子邮件附件，现已成为用于在任何地方定义文档类型的事实标准。
- [MIME列表](https://www.iana.org/assignments/media-types/media-types.xhtml)

### 引入CSS
   
`<link rel="stylesheet" href="my-css-file.css" />`

## \<script>

引入JS，defer以告诉浏览器在解析完成 HTML 后再加载 JavaScript

`<script src="my-js-file.js" defer></script>`

# 3 文本标签

标签的语义，有利于SEO，无障碍阅读（屏幕阅读器），便于理解维护。对于有语义的标签，不要为了其样式而滥用。

## \<h1>

headline，标题，块级内容，一共提供了 6 级，从高到低 h1 h2 h3 h4 h5 h6

## \<p>

paragraph，段落，块级内容

## \<span>

无语义，行级内容

## \<ul>

unorder list，无序列表，可嵌套 \<ul> \<ol> \<dl>

```
<ul>
  <li>豆汁</li>
  <li>焦圈</li>
</ul>
```

## \<ol>

order list，有序列表，可嵌套 \<ul> \<ol> \<dl>

```
<ol start="4" reversed>
  <li>豆汁</li>
  <li value="2">焦圈</li>
</ol>
```

- start 属性允许编号从指定数字开始计数，如例子中从 4 开始编号
- reversed 属性使编号顺序反转为降序，默认是升序
- value 属性使列表项可以自定义编号

## \<em>

emphasis，强调语气，用于表达字面以外的含义（阴阳怪气），行级内容，文字斜体

## \<strong>

强调内容的重要性，用于警告提醒的含义，文字加粗

## \<mark>

强调内容与上下文的相关性，例如搜索结果中的搜索关键词，文字高亮

## \<b>

bold，历史遗留，无语义，加粗，万不得已才使用

## \<i>

italics，历史遗留，无语义，斜体，万不得已才使用

## \<u>

underline，历史遗留，无语义，下划线，万不得已才使用

## \<a>

anchor，锚

`<a href="https://www.mozilla.org/zh-CN/">Mozilla 主页</a>`

- 标签内可嵌套块级内容，使其成为块级链接
- title属性，鼠标悬停在链接上时会显示补充信息
- href属性，相对路径或绝对路径，相对路径中 ../ 代表上一级目录
- target属性，_blank 链接在新页面打开，_self 链接在此页面打开
- 最佳实践
   
`<a href="https://www.mozilla.org/firefox/"> 下载 Firefox </a>`

标签内容不要出现链接的地址或“点击此处”、“链接”等字样

`<a href="https://www.example.com/large-report.pdf"> 下载销售报告（PDF，大小为 10 MB）</a>`

如果链接指向非html文件的资源，如视频、文档等，要留下清晰的提示

- download属性，设置下载内容的文件名，点击连接时会下载文件

- 电子邮件链接，可以配置收件人、抄送、主题、内容，点击后会打开邮件应用
   
`<a href="mailto:nowhere@mozilla.org?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&subject=The%20subject%20of%20the%20email&body=The%20body%20of%20the%20email"> 发送含有 cc、bcc、主题和主体的邮件</a>` 

%20表示空格，详见[URL编码](https://zh.wikipedia.org/wiki/%E7%99%BE%E5%88%86%E5%8F%B7%E7%BC%96%E7%A0%81)

## \<dl>

description list，描述列表，标记术语或定义

```
<dl>
  <dt>内心独白</dt>
  <dd>
    戏剧中，某个角色对自己的内心活动或感受进行念白表演，这些台词只面向观众，而其他角色不会听到。
  </dd>
</dl>
```

- \<dt> description term 描述的术语

- \<dd> description definition 描述的定义

- 一个 \<dt> 下可以有多个 \<dd>

## \<blockquote>

块引用，对标签里的内容进行段落缩进，cite属性表示引用源，但浏览器并不会展示其内容

```
<blockquote
  cite="https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/blockquote">
  <p>
    The <strong>HTML <code>&lt;blockquote&gt;</code> Element</strong> (or
    <em>HTML Block Quotation Element</em>) indicates that the enclosed text is
    an extended quotation.
  </p>
</blockquote>
```

## \<q>

quote，行内引用，将标签里的内容用引号包裹，cite属性表示引用源，但浏览器并不会展示其内容

```
<q cite="https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/q">
    intended for short quotations that don't require paragraph breaks.
</q>
```

## \<cite>

表示引用源，虽然有属性cite，但是浏览器、屏幕阅读器并没有对其充分利用，因此有了标签 \<cite> 用于显示引用源，一般习惯于和 \<a> 标签组合使用

`<a href="/zh-CN/docs/Web/HTML/Element/q"> <cite>MDN q page</cite></a>`

## \<abbr>

abbreviation，缩略语，文字有点下划线，在文字上悬浮会展示 title 属性（缩略语的全称）

`<abbr title="超文本标记语言（Hyper text Markup Language）">HTML</abbr>`

## \<sup>

superscript，上标

## \<sub>

subdcript，下标

## \<code>

代码，等宽字体（ monospace ）

## \<pre>

代码块

## \<var>

变量

## \<kbd>

keyboard，键盘输入，等宽字体（ monospace ）

## \<samp>

sample，程序输出，等宽字体（ monospace ）

## \<time>

时间，其 datetime 属性代表标签内时间的机器格式，方便搜索引擎抓取

```
<!-- 标准简单日期 -->
<time datetime="2016-01-20">20 January 2016</time>
<!-- 只包含年份和月份-->
<time datetime="2016-01">January 2016</time>
<!-- 只包含月份和日期 -->
<time datetime="01-20">20 January</time>
<!-- 只包含时间，小时和分钟数 -->
<time datetime="19:30">19:30</time>
<!-- 还可包含秒和毫秒 -->
<time datetime="19:30:01.856">19:30:01.856</time>
<!-- 日期和时间 -->
<time datetime="2016-01-20T19:30">7.30pm, 20 January 2016</time>
<!-- 含有时区偏移值的日期时间 -->
<time datetime="2016-01-20T19:30+01:00">7.30pm, 20 January 2016 is 8.30pm in France</time>
<!-- 提及特定周 -->
<time datetime="2016-W04">The fourth week of 2016</time>
```

# 4 结构布局标签

```
<header>
    <h1>观鸟网</h1>
    <img src="dove.png" alt="一张鸽子剪影图片">
</header>
    <nav>
      <ul>
        <li><span>主页</span></li>
        <li><a href="#">开始</a></li>
        <li><a href="#">图片</a></li>
      </ul>
    </nav>
  
  <main>
    <section>
      <h2>欢迎</h2>
      <p>时不我待！赶快带齐装备，关上电脑，去拥抱美丽的大自然吧！</p>
    </section>
    <aside>
      <h2>收藏照片</h2>
      <a href="favorite-1.jpg"><img src="favorite-1_th.jpg" alt="一只体型小巧的鸟，羽毛蓝绿色，爪黑白相间，黑色的喙细且锋利。点击缩略图查看完整照片。"></a>
      <a href="favorite-2.jpg"><img src="favorite-2_th.jpg" alt="一只美丽的孔雀的上半身图片，它的颈上覆盖蓝色的羽毛，有浅色的喙和蓝色的冠。点击缩略图查看完整照片。"></a>
  </main>
  <footer>
    <p>本虚拟站点遵守 CC0 协议，所有内容均可任意修改和复用。原始版本由 Chris Mills 于 2016 年编写。Roy Tian 于 2019 年汉化。</p>
    <p><a href="http://game-icons.net/lorc/originals/dove.html">鸽子图标</a> 由 Lorc 绘制。</p>
  </footer>
```

## \<header>

页眉

## \<nav>

导航栏

## \<main>

主内容

## \<aside>

侧边栏

## \<footer>

页脚

## \<article>

文章，每个文章都是独立的，它们之间没有任何关系

## \<section>

章节，通常多个 \<section> 同时出现，共同组成一个页面的主要部分

```
<section>
    <article>
      <section class="title">标题1</section>
      <section class="content">内容1</section>
    </article>
    <article>
      <section class="title">标题2</section>
      <section class="content">内容2</section>
    </article>
</section>
```

区分：如果一块内容相对来说比较独立的、完整的 时候，应该使用 \<article>，但是如果你想将一块内容分成几段的时候，应该使用 \<section>

## \<address>

联系信息，在一个网站的页脚使用它来包括整个网站的联系信息，或者在一篇文章里面使用它来包括作者的联系信息，这都是正确的，但不能用来标记与该页面内容无关的地址列表。、

## \<div>

无语义，万不得已再用

## \<br>

换行，单标签

\<br>是HTML写法

\<br/>是XHTML1.1的写法，也是XML写法

\<br />是XHTML为兼容HTML的写法，也是XML写法

## \<hr>

水平分割线，单标签

# 5 多媒体标签

## \<img>

图片，属于替换元素（replaced elements），即元素的内容和大小由外部资源（如图像或视频文件）定义，而不是由元素本身的内容定义。

`<img src="https://www.example.com/images/dinosaur.jpg" alt="恐龙" width="300" height="270"/>`

- 文件名要有意义，这样有利于SEO
- 最好不要把链接指向别人的网站资源（热链接），这样不道德，不稳定
- 属性alt，备选文字，图片加载失败时的显示文字，可用于无障碍，内容一般是对图片内容的描述。如果只是为了装饰，或者文字内容已经介绍了图片内容，写 alt="" 即可
- width 和 height 属性，设置图片宽高。由于图片资源和html文档分别由相互独立的http请求获取，当图片加载较慢时，会只渲染html，等待图片传输完毕后在渲染图片，这样会导致布局的改变，因此可以通过设置宽高，先对图片区域进行占位，以固定布局。[图片渲染后布局的改变](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML/no-size.png)
- title 属性，鼠标悬停时显示文字，不利于无障碍，不推荐
- 图片资源网站，[https://pixabay.com/](https://pixabay.com/)
- 为什么不用 css 背景图片？css 没有备选文本，并且不支持无障碍阅读，更适合以装饰为目的的图片

### 响应式图片

#### 不同尺寸

`<img srcset="elva-fairy-480w.jpg 480w, elva-fairy-800w.jpg 800w" sizes="(max-width: 600px) 480px, 800px" src="elva-fairy-800w.jpg" alt="Elva dressed as a fairy" />`

- srcset 参数：文件名 图片的固有宽度w
- sizes 参数：(媒体查询条件) 条件为真时图片要填充的插槽宽度，默认宽度
- src 的作用：支持旧浏览器

浏览器的动作：识别视口宽度，依次检查 sizes 中的媒体条件是否为真（没有条件算真），如例子中的 max-width: 600px 表示视口宽度最大为 600px ，如果为真，加载 srcset 中第一个固有宽度等于插槽宽度的图片，若没有，则加载第一个固有宽度大于插槽宽度的图片

要指定在某个宽度下使用特定图像候选代表的图像资源，使用 w 宽度描述符，包含表示该宽度的数字（以像素为单位）+ 小写字母 w。例如，渲染一个 450 像素宽的图像对应的描述符字符串： 450w。指定的宽度必须是正数、非零整数，并且必须与引用图像的固有宽度相匹配。

#### 相同尺寸不同分辨率

`<img srcset="elva-fairy-320w.jpg, elva-fairy-480w.jpg 1.5x, elva-fairy-640w.jpg 2x" src="elva-fairy-640w.jpg" alt="Elva dressed as a fairy" />`

srcset 中 1.5x 代表设备像素比（DPR, device pixel ratio），计算方式：逻辑像素/物理像素，1.5x 表示 1 个逻辑像素用 1.5 个物理像素表示，DPR 越大，图像越细腻。此例中，浏览器会根据 DRP 选取合适的图片，不需要使用 sizes 属性，这样可以实现在高分辨率下的屏幕上，图片拥有更高的像素密度（它们的宽度都是一样的，因为宽度的单位 px 是固定的（1/96 英尺））。

可以使用像素密度描述符，它指定了在什么样的显示器像素密度下应用相应的图像资源。它是通过将像素密度声明为正的非零浮点值，后跟小写字母 x 来编写的。例如，要指定在像素密度是标准密度的两倍时使用相应的图像，你可以提供像素密度描述符 2x 或 2.0x

## \<picture>

### 响应式加载图片（不同美术风格）

下面的例子可以根据视口宽度的不同加载不同尺寸的图片，与 img 响应式的不同：img 侧重于不同分辨率，picture 侧重于图片尺寸的裁剪（美术风格），目的是让图片的主题内容在小屏设备上更加突出。

```
<picture>
  <source media="(max-width: 799px)" srcset="elva-480w-close-portrait.jpg" />
  <source media="(min-width: 800px)" srcset="elva-800w.jpg" />
  <img src="elva-800w.jpg" alt="Chris standing up holding his daughter Elva" />
</picture>
```

- media 属性，媒体查询条件，满足条件则使用此图片源

- srcset 属性，图片文件路径

- img 标签是必须的

- 为什么不用 js css 实现响应式？浏览器在执行 js css 之前，会根据 html 对图片进行预加载

## \<figure>

figure（数值），代表一段内容（图片、表达式、表格、音视频），一般和 \<figcaption> 配合使用

```
<figure>
  <img
    src="images/dinosaur.jpg"
    alt="The head and torso of a dinosaur skeleton; it has a large head with long sharp teeth" />
  <figcaption>
    A T-Rex on display in the Manchester University Museum.
  </figcaption>
</figure>
```

alt 的内容不要和 figcaption 的内容一样，因为它们有可能同时出现

## \<figcaption>

figure caption(标题)，一般在 \<figure> 标签内，用于描述 \<figure> 的内容

## \<video>

视频

```
<video
  controls
  width="400"
  height="400"
  autoplay
  loop
  muted
  preload="auto"
  poster="poster.png">
  <source src="rabbit320.mp4" type="video/mp4" />
  <source src="rabbit320.webm" type="video/webm" />
  <p>你的浏览器不支持此视频。可点击<a href="rabbit320.mp4">此链接</a>观看</p>
</video>
```

- controls 属性，视频控件，无具体值，属性出现就生效

- \<p> 标签中的内容，后备内容，\<video> 标签无法加载时出现

- 关于文件格式，mp4 和 webM 可覆盖绝大多数的浏览器

- width 和 height ，设置宽高，原视频尺寸不会随宽高改变，空白会填充背景的颜色（默认 #000）

- source 标签，之后单独介绍

- autoplay 属性，音频和视频内容立即播放，即使页面的其他部分还没有加载完全。建议不要轻易使用，用户可能会反感

- loop 属性，循环播放，不建议使用

- muted 属性，默认静音

- poster 属性，内容为视频预览图片的路径，在视频播放前展示

- preload 属性，有三个值可选，"none"：不缓冲文件，"auto"：页面加载后缓存媒体文件，"metadata"：仅缓冲文件的元数据，即视频的文件名、时长、音轨、视频轨等（详见[视频容器结构](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content/containersandtracks.png)）

## \<audio>

音频，主流格式 mp3 和 ogg

```
<audio controls>
  <source src="viper.mp3" type="audio/mp3" />
  <source src="viper.ogg" type="audio/ogg" />
  <p>你的浏览器不支持该音频，可点击<a href="viper.mp3">此链接</a>收听。</p>
</audio>
```

属性与 \<video> 的基本一致，除了不支持 width 和 height 属性，不支持 poster 属性

## \<source>

文件源，单标签，放在 \<video> 标签或 \<audio> 标签内。浏览器会根据其 type 属性，判断是否支持该文件格式，选取第一个支持的文件源进行播放

## \<track>

字幕，cc (Closed Caption) 可关闭字幕

```
<video controls>
  <source src="example.mp4" type="video/mp4" />
  <source src="example.webm" type="video/webm" />
  <track kind="subtitles" src="subtitles_es.vtt" srclang="es" label="Spanish" />
</video>
```

- kind 属性，有以下可选属性值，subtitles（字幕，包括翻译、额外信息，针对***听不懂***的人）、captions（字幕，包括音效文字，针对***听不见***的人）、~~descriptions（描述，视频内容的文本描述，针对***看不见***的人）~~

- src 属性，指向字幕文件，vtt格式，webVTT文件的一般格式如下，包含多个时间提示性内容（cue）

```
WEBVTT

1
00:00:22.230 --> 00:00:24.606
第一段字幕

2
00:00:30.739 --> 00:00:34.074
第二段
```

- srclang 属性，表示字幕语言类型，如果 kind="subtitles" ，则为必填项

- label 属性，给出的字幕标题，会展示给用户，以供用户选择适合自己的字幕

- 示例，对默认视频播放器的封装，[展示](https://iandevlin.github.io/mdn/video-player-with-captions/)，[源码](https://github.com/iandevlin/iandevlin.github.io/tree/master/mdn/video-player-with-captions)

## \<iframe>

嵌入其他网页

```
  <iframe
    src="https://developer.mozilla.org/zh-CN/docs/Glossary"
    width="100%"
    height="500"
    allowfullscreen
    sandbox>
    <p>
      <a href="/zh-CN/docs/Glossary">
        为不支持 iframe 的浏览器预留的后备链接
      </a>
    </p>
  </iframe>
```

- border 属性，默认附带边框，border: none 可去除边框

- allowfullscreen 属性，允许将 iframe 设置为全屏模式

- sandbox 属性，为嵌入内容设置严格的限制，若想开放权限，可添加参数，[详见](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/iframe#sandbox)

4. 内容安全策略（ Content-Security-Policy ），提供一组标头，以提高 iframe 的安全性，服务器添加标头 X-Frame-Options: DENY，可使得此页面被 frame 嵌入时会无法加载

## \<object>

嵌入外部资源，例如pdf

```
<object data="mypdf.pdf" type="application/pdf" width="800" height="1200">
  <p>
    You don't have a PDF plugin, but you can
    <a href="mypdf.pdf">download the PDF file. </a>
  </p>
</object>
```

## \<embed>

嵌入外部资源或插件，例如 flash，现已基本弃用

## \<svg>

SVG 是用于描述矢量图像的标记语言，它基于 XML。

```
<svg
  version="1.1"
  baseProfile="full"
  width="300"
  height="200"
  xmlns="http://www.w3.org/2000/svg">
  <rect width="100%" height="100%" fill="black" />
  <circle cx="150" cy="100" r="90" fill="blue" />
</svg>
```

- 优点：矢量图像中的文本仍然可访问（这也有利于 SEO）。SVG 图像的每个组件都可以通过 CSS 或通过 JavaScript 设置样式的元素。

- 缺点：SVG 容易变得复杂，复杂的 SVG 也会占用浏览器很长的处理时间。SVG 可能比位图更难创建。

- 位图制作软件：Adobe Illustrator、Inkscape

- img引入方式，无法使用 js 修改

`<img src="equilateral.svg" alt="等边三角形" height="87px" width="100px" />`

    对于不支持svg引入的浏览器兼容

`<img src="equilateral.png" alt="等边三角形" srcset="equilateral.svg" />`

- svg引入方式，方便 js 、 css 修改

`<svg width="300" height="200"><rect width="100%" height="100%" fill="green" /></svg>`

- iframe引入方式，不建议

`<iframe src="triangle.svg" width="500" height="500" sandbox><img src="triangle.png" alt="Triangle with three unequal sides" /></iframe>`

# 6 表格标签

不要使用表格布局，不利于无障碍，不利于理解和维护，不利于响应式布局（表格的大小默认与内容相关）

```
<table>
  <tr>
    <th>&nbsp;</th>
    <th>Knocky</th>
    <th>Flor</th>
    <th>Ella</th>
    <th>Juan</th>
  </tr>
  <tr>
    <th>Breed</th>
    <td>Jack Russell</td>
    <td>Poodle</td>
    <td>Streetdog</td>
    <td>Cocker Spaniel</td>
  </tr>
</table>
```

## \<table>

表格，一般和 \<tr> \<td> 组合使用，可以在 \<td> 中嵌套 \<table>

## \<tr>

table row，表格中的一行

## \<td>

table data，表格中的一列，colspan="n" 属性合并 n 列，rowspan="m" 属性合并 m 行

```
<tr>
  <th>Breed</td>
  <td rowspan="2">Jack Russell</td>
  <td>Poodle</td>
  <td colspan="2">Streetdog</td>
</tr>
<tr>
  <th>Age</td>
  <td>9</td>
  <td>10</td>
  <td>5</td>
</tr>
```

- rowspan="2" 合并了单元格 [1,2] 和 [2,2]

- colspan="2" 合并了单元格 [1,4] 和 [1,5]

## \<th>

- table head，标头，内容居中加粗，有利于无障碍阅读，屏幕阅读设备能一次读出一列或一行的数据

- 可使用 colspan rowspan 属性

- scope 属性，其值为 col 表示此单元格为一列的表头，其值为 row 表示此单元格为一行的表头，其值为 colgroup 表示此单元格为列表头且有多个具有 scope="col" 属性的子表头，值 rowgroup 同理

- 明确表头的另一种方式，id 和 headers 属性

```
<thead>
  <tr>
    <th id="purchase">Purchase</th>
    <th id="location">Location</th>
    <th id="date">Date</th>
    <th id="evaluation">Evaluation</th>
    <th id="cost">Cost (€)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <th id="haircut">Haircut</th>
    <td headers="location haircut">Hairdresser</td>
    <td headers="date haircut">12/09</td>
    <td headers="evaluation haircut">Great idea</td>
    <td headers="cost haircut">30</td>
  </tr>
  ......
</tbody>
```

## \<colgroup>

为表格中的某一列提供统一样式

```
<table>
  <colgroup>
    <col />
    <col style="background-color: yellow" />
  </colgroup>
  <tr>
    <th>Data 1</th>
    <th>Data 2</th>
  </tr>
  <tr>
    <td>Calcutta</td>
    <td>Orange</td>
  </tr>
</table>
```

由于第一列没有样式，使用 \<col />，\<col style="background-color: yellow" /> 为第二列提供样式

## \<caption>

表格标题，默认位于表格上并居中，有利于无障碍

```
<table>
  <caption>
    侏罗纪时期的恐龙
  </caption>
  ......
</table>
```

## \<thead>

表头，在 \<col> \<colgroup> 元素下方

## \<tbody>

表体，浏览器会自动添加，在表头或表尾的下方

可以让表格的正文部分显示在一个单独的页面上，并通过上下滚动来获得内容

## \<tfoot>

表尾，一般在最后一行