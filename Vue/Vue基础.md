- [使用 Vue](#使用-vue)
  - [CDN 引入方式](#cdn-引入方式)
  - [第一个 Vue 实例](#第一个-vue-实例)
  - [Vue dev-tools](#vue-dev-tools)
  - [选项式 API](#选项式-api)
    - [data()](#data)
      - [定义数据](#定义数据)
      - [展示数据](#展示数据)
      - [获取数据](#获取数据)
    - [methods](#methods)
      - [定义方法](#定义方法)
      - [调用方法](#调用方法)
    - [computed](#computed)
    - [watch](#watch)
    - [生命周期](#生命周期)
  - [内置指令](#内置指令)
    - [v-cloak](#v-cloak)
    - [v-bind](#v-bind)
      - [class 绑定](#class-绑定)
      - [style 绑定](#style-绑定)
    - [v-html](#v-html)
      - [Cross Site Scripting (XSS)](#cross-site-scripting-xss)
    - [v-on](#v-on)
    - [v-model](#v-model)
      - [event](#event)
    - [v-if](#v-if)
    - [v-else-if](#v-else-if)
    - [v-else](#v-else)
    - [v-show](#v-show)
    - [v-for](#v-for)
      - [key](#key)
    - [\<template\> 标签](#template-标签)
  - [修饰符](#修饰符)
    - [事件修饰符](#事件修饰符)
      - [.prevent](#prevent)
    - [表单修饰符](#表单修饰符)
      - [.trim](#trim)
      - [.lazy](#lazy)
      - [.number](#number)
  - [虚拟 DOM](#虚拟-dom)
  - [响应式](#响应式)
  - [模板和编译器](#模板和编译器)
    - [有编译器版本？无编译器版本？](#有编译器版本无编译器版本)
  - [组件](#组件)
- [Vue 工程化](#vue-工程化)
  - [Vite](#vite)
  - [create-vue](#create-vue)
  - [组件](#组件-1)
    - [SFC](#sfc)
    - [组件注册方式](#组件注册方式)
    - [组件使用](#组件使用)
    - [组件样式](#组件样式)
      - [scoped-css](#scoped-css)
      - [Sass](#sass)
    - [组件传值](#组件传值)
      - [父传子](#父传子)
      - [子传父](#子传父)
        - [事件传值](#事件传值)
        - [函数传值](#函数传值)
      - [props 校验](#props-校验)
    - [组件插槽](#组件插槽)
      - [具名插槽](#具名插槽)
    - [动态组件](#动态组件)
  - [transition](#transition)
    - [过渡](#过渡)
    - [动画](#动画)
    - [事件钩子](#事件钩子)
    - [transition-gruop](#transition-gruop)
    - [Animate.css](#animatecss)
- [前端工具](#前端工具)
  - [Sass](#sass-1)
  - [PostCSS](#postcss)
  - [ESLint](#eslint)
  - [Prettier](#prettier)
  - [TailwindCSS](#tailwindcss)
  - [PurgeCSS](#purgecss)
  - [Pinia](#pinia)
  - [vee-validate](#vee-validate)
  - [Firebase](#firebase)
  - [JSON Web Token](#json-web-token)
  - [Vue Router](#vue-router)
  - [Font Awesome](#font-awesome)
  - [Howler.js](#howlerjs)
  - [Vue i18n](#vue-i18n)
  - [Lodash](#lodash)
  - [NProgress.js](#nprogressjs)
  - [Code Coverage](#code-coverage)
  - [rollup-plugin-visualizer](#rollup-plugin-visualizer)
  - [vercel](#vercel)
  - [vitest](#vitest)

# 使用 Vue

## CDN 引入方式

在 html 文件中引入 CDN 标签，开箱即用

[通过 CDN 使用 Vue](https://cn.vuejs.org/guide/quick-start.html#using-vue-from-cdn)

## 第一个 Vue 实例

createApp() 接收配置对象

```
Vue.createApp({}).mount('#app')
```

mount() 参数是 html 中元素的 id 选择器或 class 选择器，如果有多个匹配的 class，挂载到第一个元素上

允许创建多个 app 实例，并且实例中的 data 相互独立

[使用全局构建版本](https://cn.vuejs.org/guide/quick-start.html#using-the-global-build)

## Vue dev-tools

用于在浏览器上对 Vue 进行开发调试

如果以本地文件的方式打开 html，需要设置拓展，打开 Allow access to file URLs 选项

[Vue Devtools](https://devtools.vuejs.org/)

## 选项式 API

### data()

#### 定义数据

createApp() 可以接收 data() 方法，用于存储数据，data() 返回的对象告诉 Vue 有哪些数据

```
Vue.createApp({
    data() {
        return {
            firstName: 'Lin'
        }
    }
}).mount('#app')
```

#### 展示数据

文本插值，内容只能是 JS 表达式（expression），Vue 会展示表达式计算的值

JS 表达式（只要可以被计算为一个值就是表达式）：

```
2 + 2
"hello".toUpperCase()
100 === 100
```

在 html 中使用文本插值：

```
<div id="app">
    {{ 2 + 2 }}
</div>
<!-- 4 -->
```

展示上文在 data(){} 中返回的数据（只有在 data() 中定义的数据才能通过文本插值展示）：

```
<div id="app">
    {{ firstName }}
</div>
<!-- Lin -->
```

#### 获取数据

如何在 js 中获取定义的 data？

可以用一个变量接收 app 实例，然后直接访问属性

```
const vm = Vue.createApp({
    data() {
        return {
            firstName: 'Lin'
        }
    }
}).mount('#app')

console.log(vm.firstName)
```

这里直接通过 vm 就得到了 data 中的变量，这是因为 vue 为每个属性自动设置了 get set 方法，通过代理（proxy）让开发者可以方便地获取定义的 data

### methods

#### 定义方法

和 data 的定义类似，只不过不再是传给 createApp() 一个方法，而是一个属性 methods

```
methods: {
    fullName() {
        return `${this.firstName} ${this.lastName.toUpperCase()}`
    }
}
```

这里定义了一个 fullName() 方法，方法中可以访问 data 中定义的数据，只需要通过使用 this，但是如果使用箭头函数，会导致 this 指向改变，所有如果使用 this，要采用常规函数的方式来定义方法

#### 调用方法

可以通过文本插值直接调用方法

```
<div id="app">
    {{ fullName() }}
</div>
```

### computed

计算属性类似于 methods 属性，也可以在 createApp() 的对象参数中配置

问题：每当 data 中有数据被更新，文本插值中调用的 fullName() 方法都会被调用

```
<p>{{ fullName() }}</p>
```

可以将方法转移到计算属性中解决这个问题：

```
computed: {
    fullName() {
        return `${this.firstName} ${this.lastName.toUpperCase()}`
    }
}
```

vue 会将 computed 中方法当作属性名，方法返回值当作属性值，存储的是属性，而不是方法，每当需要更新返回值时，再调用方法修改这个属性。因此，文本插值中不再需要调用方法，而是直接将 fullName 视为属性调用：

```
<p>{{ fullName }}</p>
```

这样只有 fullName 中需要的 data 更新时，才会调用 fullName

计算属性节省了性能，可以看作是一种特殊的方法，只不过它专注于计算（calculate），这里的计算不单单是计算数字，也包括对字符串的修改，并且计算属性不能传递参数，因为它只是对 data 进行加工

### watch

侦听器类似于 methods，computed，也可以在 createApp() 的对象参数中配置

```
watch: {
    age(newVal, oldVal) {
      ...
    }
}
```

以上是一个示例，这个侦听器监听 data 中的 age，如果 age 的值变化，会调用这个方法，并且传入两个参数，第一个是新值，第二个是旧值

侦听器可以看作一种特殊的方法，相比较于计算属性，它更加灵活，可以根据参数中的 newVal，去执行一些异步的操作

### 生命周期

[生命周期](https://cn.vuejs.org/guide/essentials/lifecycle.html)

Vue 中有以下生命周期钩子：

- beforeCreate
- created
- beforeMount
- mounted
- beforeUpdate
- updated
- beforeUnmount
- Unmounted

开发者可以通过钩子，在 Vue 的工作流程中的某一阶段，插入一些代码进行自定义的操作

Vue 工作的流程和所有钩子运行的时机：

![](https://cn.vuejs.org/assets/lifecycle_zh-CN.W0MNXI0C.png)

created 和 mounted 区别：

- created 是创建 data、methods、computed 等选项式 API 完成之后，可以在此阶段获取数据
- mounted 是渲染完毕并将结果插入 DOM，可以在此阶段修改页面 DOM

用法：

和 data、methods 类似，在 createApp() 内插入声明周期钩子

```
created() {
    console.log("created!")
}
```

## 内置指令

### v-cloak

[v-cloak](https://cn.vuejs.org/api/built-in-directives.html#v-cloak)

对于没有构建步骤的环境，会出现未编译模板闪现的问题（模板未解析的初始值会显示，等到挂载完成才被替代为正常内容，这之间的时间很短，所以会一闪而过），给模板元素添加这个指令，就可以和 css 配合，实现效果：当模板挂载完成之后，再显示内容

```
[v-cloak] {
  display: none;
}
```

```
<div id="app" v-cloak>
  {{ fullName() }}
</div>
```

### v-bind

单向绑定

```
<a v-bind:href="url" target="_blank">Baidu</a>
<!-- 缩写 -->
<a :href="url" target="_blank">Baidu</a>
```

#### class 绑定

[类与样式绑定](https://cn.vuejs.org/guide/essentials/class-and-style.html#class-and-style-bindings)

可以结合 v-bind 动态绑定 class，接收的参数是一个对象，对象中的属性名是类名，属性值是一个布尔值，如果是 true 这个类就会被应用

```
<div class="circle" :class="{ purple: isPurple }">
  Hi
</div>
```

和计算属性配合使用：

```
<div class="circle" :class="circle_classes">
  Hi
</div>
```

```
computed: {
  circle_classes() {
    return { purple: this.isPurple }
  }
}
```

可以不使用对象，直接传入一个 data，它的值是一个字符串，这个字符串会被绑定为类名：

```
<div class="circle" :class="selectedColor">
  Hi
</div>
```

对于多个 class 的情况，可以传入一个数组，数组中可以有对象，或者单纯的计算属性，vue 会自动识别：

```
<div class="circle" :class="[circle_classes,selectedColor]">
  Hi
</div>
```

#### style 绑定

结合 v-bind 动态绑定 style，传入一个对象，每个属性名是 CSS 属性名称，属性值则是在 data 中定义好的字符串，可以对属性值进行拼接

```
<div :style="{ width: size + 'px', height: size + 'px' }">
    Hi
</div>
```

有的 CSS 属性名有连字符，比如 line-height，这样会导致属性不可用，有两种解决方式：

- 用引号将属性名包裹，比如 `'line-height'`
- 采用属性名的驼峰命名，比如 `lineHeight`

和 class 绑定类似，style 绑定也可以传入一个数组，数组中可以包含多个对象

### v-html

可以将 data 中的字符串转换为 html 标签

```
<p v-html="raw_url"></p>
```

#### Cross Site Scripting (XSS)

跨站脚本，攻击者可以通过在控制台修改 v-html 绑定的 data 值，达到攻击效果

避免攻击：后端对前端的数据进行检测过滤

### v-on

绑定事件

将点击事件绑定了自定义的 increment 方法，没有参数可以省略括号

```
<button type="button" v-on:click="increment">Increment</button>
```

v-on 简写为 @，并且可以直接在属性值中操作 data 中的数据

```
<button type="button" @click="age--">Decrement</button>
```

### v-model

data 和 视图双向绑定

```
<input type="text" v-model="firstName" />
```

v-model 实际上是一种语法糖：

```
<input type="text" :value="lastName" @input="(event) => lastName=event.target.value" />
```

event 是事件对象，target 是触发事件的元素

#### event

如果方法没有参数，默认会自动传递一个 event 对象

如果方法有参数，并且想要传递 event 对象，需要显示传入参数 $event

```
<input type="text" :value="lastName" @input="updateLastName('事件被触发！', $event)" />
```

[条件渲染](https://cn.vuejs.org/guide/essentials/conditional.html)

### v-if

如果表达式返回值为 true 显示该元素，否则直接移除该元素

```
<p v-if="mode == 1">Showing v-if content</p>
```

### v-else-if

需要和 v-if 配合使用，并且和使用 v-if 的元素是兄弟关系，当 v-if 判断为 false，会判断 v-else-if 的参数是否为真

```
<p v-else-if="mode == 2">Showing v-else-if content</p>
```

### v-else

需要和 v-if/v-else-if 配合使用，并且和使用 v-if/v-else-if 的元素是兄弟关系，当 v-if/v-else-if 判断均为 false，会显示 v-else 的元素，v-else 不需要参数

```
<p v-else>Showing v-else content</p>
```

### v-show

用法和 v-if 一样，区别在于 v-show 不会将元素移除，而是添加 `display:none` 样式，所以相比于 v-if 具有更少的切换开销

需要频繁切换状态使用 v-show，否则使用 v-if

### v-for

[列表渲染](https://cn.vuejs.org/guide/essentials/list.html)

列表渲染，如下：

```
<li v-for="bird in birds">
    {{ bird }}
</li>
```

这个例子中，birds 是 data 中定义的数组，bird 是自定义的遍历项名称，bird 可以在标签内任何地方使用，这个例子会遍历 birds 中的每一项，并通过文本插值展示

遍历时同时遍历每一项的索引值：

```
<li v-for="(bird, index) in birds">
    {{ bird }} - {{ index }}
</li>
```

这个自定义的变量 index 表示每一项在数组中的索引值，也可以在标签内任何地方使用

遍历对象：

```
<li v-for="(person, index) in people">
    <div v-for="(value, key, index) in person">
        {{ key }}: {{ value }} - {{ index }}
    </div>
</li>
```

people 定义：

```
people: [
    {
        name: 'lin',
        age: 23
    },
    {
        name: 'wang',
        age: 22
    }
]
```

以上示例展示了如何列表渲染对象，首先第一层遍历 people 中的所有对象，第二层遍历，将对象中的所有属性遍历，第一个参数是值，第二个参数是键，第三个参数是索引值，如果不需要可以省略参数

#### key

为什么需要 key？以下是一个示例：

```
<li v-for="(bird, index) in birds">
    {{ bird }} - {{ index }}
    <input type="text">
</li>
```

如果进行如下操作：在第一项的 input 中输入值，然后将 birds 数组中的第一项移动到最后一项。

会发现：bird 和 index 的值会随数组顺序改变，但是 input 却没有移动

原因：Vue 为了节省开销，不会移动 DOM 元素，而是重新计算每一项元素的数据，所以 input 元素并没有移动，但是文本插值内容却更新了

因此，需要 key 属性来告诉 Vue 移动元素位置：

```
<li v-for="(bird, index) in birds" :key="bird">
    {{ bird }} - {{ index }}
    <input type="text">
</li>
```

key 接收一个基础类型，不要将对象作为 key，key 可以给 Vue 一个提示，以便它可以跟踪每个节点的标识，从而重用和重新排序现有的元素。对于复杂的列表渲染，使用 key 很有必要

### \<template> 标签

template 标签是 Vue 提供的特殊标签，它本身不会渲染，不会影响 HTML 结构，所以不会影响 CSS 的应用，有时候可以用于代替 div 标签，用于条件渲染多个元素

```
<div>
    <p v-if="mode == 1">Showing v-if content</p>
    <template v-else-if="mode == 2">
        <p>Hello</p>
        <p>Showing v-else-if content</p>
    </template>
    <p v-else>Showing v-else content</p>
</div>
```

当 mode == 2 时，渲染结果：

```
<div>
    <p>Hello</p>
    <p>Showing v-else-if content</p>
</div>
```

## 修饰符

### 事件修饰符

用于简化对事件对象的操作

[事件修饰符](https://cn.vuejs.org/guide/essentials/event-handling.html#event-modifiers)

例如，原本需要在方法中阻止默认事件：

```
updateLastName(msg, event) {
    // 阻止默认事件
    event.preventDefault()
    this.lastName = event.target.value
}
```

这种方式比较繁琐，因为需要传递事件对象并调用 preventDefault() 方法，可以通过 .prevent 简写：

```
<input type="text" :value="lastName" @input.prevent="updateLastName('事件被触发！', $event)" />
```

这样就不用在方法中调用 preventDefault() 方法，并且也不需要传递 event 对象了

#### .prevent

阻止事件的默认行为，等价于在方法中的 `event.preventDefault()`

### 表单修饰符

[表单中的修饰符](https://cn.vuejs.org/guide/essentials/forms.html#modifiers)

#### .trim

删除输入内容两端空格

```
<input v-model.trim="msg" />
```

#### .lazy

在 change 事件后更新而不是 input 事件

```
<input v-model.lazy="msg" />
```

#### .number

让输入的内容默认是 number 类型，注意，如果 input 标签有 type 属性，要保证值为 number

```
<input v-model.number="age" />
```

## 虚拟 DOM

[虚拟 DOM](https://cn.vuejs.org/guide/extras/rendering-mechanism.html#virtual-dom)

虚拟 DOM 是真实 DOM 的一个轻量化的副本，可以通过它减少修改 DOM 的开销

将模板编译为虚拟 DOM：

```
<h1 class="blue">
    Hello World
</h1>
```

```
{
    tag: 'h1',
    attributes: {
        class: "blue"
    },
    content: "Hello World"
}
```

为了减少开销，Vue 不会直接更新 DOM，而是会修改虚拟 DOM，然后再比较虚拟 DOM 和 DOM，在 DOM 上打上补丁（patch）

## 响应式

[深入响应式系统](https://cn.vuejs.org/guide/extras/reactivity-in-depth.html)

关于 Proxy：

```
<div id="name"></div>
```

```
const data = {
    name: 'Luis'
}

// 为 data 对象创建一个代理，返回的实例是 data 的副本
const dataProxy = new Proxy(data, {
    // 第二个参数可以设置额外的操作
    // set 方法在对象属性要被修改时触发
    // target 是要操作的对象，key 是属性名，value 是要修改的属性值
    set(target, key, value) {
        // 这里进行额外操作，改变 DOM 的内容
        document.querySelector("#name").innerText = value
        target[key] = value
    }
})

// 通过代理对象修改属性
dataProxy.name = "Lin"

// div 元素的内容会变为 Lin
```

这是一个应用代理的示例，Vue 利用 Proxy 实现了 DOM 的响应式

## 模板和编译器

template 属性类似于 methods、data 等，可以通过使用 template 设置自己的模板：

```
<div id="app"></div>
```

```
let vm = Vue.createApp({
    data() {
        return {
            message: "Hello world!"
        }
    },
    template: `{{ message }}`
})

vm.mount("#app")
```

运行结果：页面中出现文字 Hello world!

以上代码通过 template 属性定义了一个模板，这个模板会插入到挂载的元素中。可以通过请求 html 文件，并将其赋值到模板，从而实现页面的展示。但是不建议这样使用 template，因为 JS 字符串模板语法兼容性不好，并且字符串内没有编辑器提供的代码高亮提示，不利于维护。所以建议将模板放到 html 文件的挂载元素中，让 Vue 去以字符串的方式获取它

### 有编译器版本？无编译器版本？

通常使用的 Vue 都是带编译器的版本，属于完全编译，Vue 可以根据模板，将其编译为虚拟 DOM

无编译器版本，属于运行时编译，优势在于体积缩小 30%，运行速度加快，缺点在于，需要手动管理

编译器官方定义：负责将模板字符串编译为 JS 渲染（render）函数的代码。Vue.compile() 方法：即编译器方法，传入字符串模板，返回一个 render 函数

无编译器版本 Vue，需要手动创建渲染函数：

```
let vm = Vue.createApp({
    data() {
        return {
            message: "Hello world!"
        }
    },
    // 手动创建渲染函数
    render() {
        // 返回一个 render 函数
        // h() 函数可以自动格式化 render 函数
        return Vue.h(
            'h1',
            this.message
        )
    }
})

vm.mount("#app")
```

运行结果：页面中出现 Hello world! 一级标题

运行时编译（无编译器）性能好，但是需要我们手动创建 render 函数，vue-cli 可以在提高性能的同时，让这个过程更加容易

## 组件

组件将 html 中的指定部分拆分，并放在不同的文件，这样可以实现组件重用，可以让代码结构更简洁清晰

组件包括模板，但不止于此，每个组件都可以有自己的 data、methods、computed 等

创建模板:

```
let vm = Vue.createApp({

})

vm.component('hello', {
    template: `<h1>{{ message }}</h1>`,
    data() {
        return {
            message: "Hello world!"
        }
    }
})

vm.mount("#app")
```

使用模板：

```
<div id="app">
    <hello></hello>
    <hello></hello>
    <hello></hello>
</div>
```

运行结果：页面出现三个 Hello world! 一级标题

值得注意的是，这三个模板中的 data 是完全相互独立的

# Vue 工程化

## Vite

[官方文档](https://cn.vitejs.dev/guide/)

打包工具（bunder），用于压缩项目文件，以投入生产环境

优势：

- 对于大型项目，打包速度快
- 支持许多第三方库
- 易拓展

在空目录运行命令，初始化 vite 项目：

```
npm create vite@latest
```

vite 为 JS 或其他框架提供了模板，[所有模板](https://vitejs.dev/guide/#trying-vite-online)

vite 中 js 文件可以通过 import 导入非 js 类型的文件

vite 提供的指令：

- dev：开发环境使用，在本地运行项目，实时更新
- build：将项目打包到 dist 目录，目录中文件可以直接投入生产环境
- preview：在本地服务器运行 dist 目录下打包好的项目，不会实时更新

## create-vue

[create-vue](https://github.com/vuejs/create-vue) 是 Vue 官方提供的构建工具，用于 Vue 项目的初始化构建，通过 create-vue 可以根据你的需要快速初始化一个 Vue 项目

初始化：

```
npm create vue@latest
```

create-vue 创建的项目中，使用的是无编译器的 vue 版本，这意味着我们需要去手动实现 render 函数，但是 vite 帮我们完成了这些工作，所有 .vue 后缀文件（SFC，单文件组件）会被编译为组件对象，对象中实现了 render 函数。单文件组件提供了一种方式，可以便捷地编写组件，所有幕后的工作都由 vite 和 vue 完成

main.js 文件，是项目的入口文件，文件进行了 createApp() 以及 mount() 操作，传入 createApp() 的参数就是名为 App.vue 的根组件，这正是由于 SFC 被编译为了对象

## 组件

### SFC

单文件组件是 Vue 工程中的一种特殊文档，结构如下：

```
<template></template>
<script></script>
<style></style>
```

script 中暴露一个对象，用于配置组件的 API：

```
<script>
export default {
    name: 'App',
    data() {
        return {
            message: "Hello World"
        }
    }
}
</script>
```

关于属性 name，用于给组件命名，在开发者工具中调试时可以看到组件名称

一个 SFC 就是一个组件，Vue 会自动将其编译为组件对象

### 组件注册方式

全局注册，可以在任何 SFC 中使用组件，在 main.js 中完成注册：

```
import { createApp } from 'vue'
import App from './App.vue'
import Greeting from '@/components/Greeting.vue'

const vm = createApp(App)

// 字符串是组件名称，第二个参数是组件对象
vm.component("Greeting", Greeting)

vm.mount('#app')
```

本地注册，在 SFC 中注册组件:

```
<script>
import Greeting from '@/components/Greeting.vue'

export default {
  name: 'App',
  components: {
    Greeting
  }
}
</script>
```

通过给 components 属性传入一个对象，以键值对的方式配置组件，这里的 `Greeting` 是 `Greeing: Greeting` 的缩写，键是组件名称，值是导入的组件对象

### 组件使用

在 template 标签中直接使用组件标签：

```
<template>
  <greeting></greeting>
</template>
```

组件的标签名首字母可以小写，并且对于驼峰命名的组件名，可以写为小写字母连字符格式的名称，Vue 会自动转换

[组件名格式](https://cn.vuejs.org/guide/components/registration.html#component-name-casing)

### 组件样式

style 标签中可以添加 CSS 样式

#### scoped-css

给 style 标签添加 scoped 属性可以保证 css 只在当前 SFC 中生效

```
<style scoped>
    ...
</style>
```

Vue 会为应用 css 的 html 标签添加一个特殊的属性标识，同时为标签中的所有 css 添加这个特殊属性的选择器，这样保证 css 只应用于当前文件中

[更多关于 scoped-css 介绍](https://cn.vuejs.org/api/sfc-css-features.html#scoped-css)

#### Sass

npm 安装 sass 之后就可以在 SFC 中使用 scss/sass 编写 css，只需要配置 style 标签的 lang 属性：

```
<style scoped lang="scss">
$font-color: #cc4444;

p {
    color: $font-color;
}
</style>
```

### 组件传值

Vue 没有为兄弟组件提供直接传值的方式，但是可以进行父子组件传值：

#### 父传子

父组件传给子组件 age 数据，子组件接收的 age 可当作 data 使用，并且会随父组件的 data 更新

父组件 App.vue

```
<template>
  <user :age="age"></user>
</template>
<script>
import User from '@/components/User.vue'

export default {
  name: 'App',
  components: {
    User
  },
  data() {
    return {
      age: 20
    }
  }
}
</script>
```

子组件 User.vue

```
<template>
    <p>
        The user is {{ age }} years old
    </p>
</template>
<script>
export default {
    name: 'User',
    props: ["age"]
}
</script>
```

#### 子传父

##### 事件传值

子传父可以间接实现兄弟间传值：

子组件 Greeting.vue

```
<template>
    <button @click="onClickChange">Update Age</button>
</template>

<script>
export default {
    name: 'Greeting',
    props: ["age"],
    // 对传递事件的方法进行注册，便于 Vue 记录
    emits: ['age-change'],
    methods: {
        onClickChange() {
            this.$emit('age-change', 30)
        }
    }
}
</script>
```

父组件 App.vue

```
<template>
  <user :age="age"></user>
  <greeting :age="age" @age-change="updateAge"></greeting>
</template>
<script>
import Greeting from '@/components/Greeting.vue'
import User from '@/components/User.vue'

export default {
  name: 'App',
  components: {
    Greeting,
    User
  },
  data() {
    return {
      age: 20
    }
  },
  methods: {
    updateAge(num) {
      this.age = num
    }
  }
}
</script>
```

以上示例通过子组件中的按钮触发事件，将事件以及参数传递到父组件，并在父组件中通过方法修改 age 的值，age 的更新会影响到 User 组件中 age 的值，这样通过父组件间接实现了兄弟组件之间的传值

虽然不能再子组件中修改父组件传递的值（props），但是可以通过计算属性对 props 进行加工

##### 函数传值

可以通过 props 将父组件中定义的函数，传递给子组件，并在子组件中调用这个函数，并传递参数给父组件，由于函数是父组件的，这种操作不会被阻止

还是建议采用事件传值，因为在开发者工具中可以对事件进行跟踪，便于调试

#### props 校验

如果要对传入的 props 进行限制，可以给 props 传入一个对象，在对象中进行数据类型、是否必须、默认值、校验器方法等配置

```
props: {
    type: [String, Number],
    required: true,
    default: 30,
    // 校验器方法会接收传入的数据，并判断返回布尔值，true 表示通过
    validator(val) {
        return val < 100;
    }
}
```

validator 方法在组件实例创建之前就存在，这意味着不能在 validator 中调用 data 或 methods 中定义的数据和方法

如果传入的 props 没有通过校验，会在控制台进行 warn

[这个示例](https://cn.vuejs.org/guide/components/props.html#prop-validation) 展示了 props 校验的所有用法

### 组件插槽

插槽提高了组件的可重用性

子组件 Form.vue：

```
<template>
    <form>
        <slot>Default content</slot>
    </form>
</template>
```

slot 标签提供了一个插槽，允许其父组件在组件标签内传入 html，slot 标签内是默认内容，当父组件没有传入 html 内容时显示

父组件 App.vue:

```
<template>
  <app-form>
    <div class="help">
      <p>Help text</p>
    </div>
  </app-form>
  <app-form></app-form>
</template>
<script>
import AppForm from "@/components/Form.vue"
export default {
  name: 'App',
  components: {
    AppForm
  }
}
</script>
```

父组件在 app-form 标签内传入 html，这些标签会被插入到子组件的 slot 标签位置

#### 具名插槽

子组件 Form.vue：

```
<template>
    <form>
        <slot name="help"></slot>
        <slot></slot>
    </form>
</template>
```

父组件 App.vue:

```
<template>
  <app-form>
    <template v-slot:help>
      <div class="help">
        <p>Help text</p>
      </div>
    </template>
    <p>Normal slot content</p>
  </app-form>
</template>
<script>
import AppForm from "@/components/Form.vue"
export default {
  name: 'App',
  components: {
    AppForm
  }
}
</script>
```

父组件中通过 `<template v-slot:help>` 标签指定具名插槽，并在这个插槽中传入内容，对于在 template 标签外的内容，会被传入普通插槽的位置

父组件中传入插槽的 html 内容可以直接使用 data 或 methods 等配置的属性或方法，而不用通过组件传值

[更多插槽介绍](https://cn.vuejs.org/guide/components/slots.html#slots)

### 动态组件

父组件：

```
<template>
  <select v-model="componentName">
    <option value="Home">Home</option>
    <option value="About">About</option>
  </select>

  <KeepAlive>
    <component :is="componentName"></component>
  </KeepAlive>
</template>

<script>
import Home from "@/components/Home.vue"
import About from "@/components/About.vue"
export default {
  name: 'App',
  data() {
    return {
      componentName: 'Home'
    }
  },
  components: {
    Home,
    About
  }
}
</script>
```

通过 component 标签可以根据 is 属性绑定的值切换组件，组件隐藏时会触发 unmounted() 钩子，组件显示时触发 mounted() 钩子

keepalive 标签保证组件一直保存在内存中，不会被销毁，组件在展示时触发 activated() 钩子，被隐藏时触发 deactiveted() 钩子

## transition

### 过渡

Vue 提供了内置组件 transition ，实现 CSS 过渡

为一个 transition 标签设置 name 属性，并通过特定类名的 css 实现过渡

进入动画（ \* 是在 transition 标签中定义的名称）：

- \*-enter-from，进入的起始帧
- \*-enter-to，进入完成的最终帧
- \*-enter-active，进入过程，一般用于定义动画速率

离开动画：

- \*-leave-from
- \*-leave-to
- \*-leave-active

示例：

```
<template>
  <button type="button" @click="flag = !flag">Toggle</button>

  <transition name="fade" mode="out-in">
    <h2 v-if="flag">Hello</h2>
    <h2 v-else>Hi</h2>
  </transition>

</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      flag: false
    }
  }
}
</script>

<style>
.fade-enter-from {
  opacity: 0;
}

.fade-enter-active {
  transition: all .25s linear;
}

.fade-leave-active {
  transition: all .25s linear;
}

.fade-leave-to {
  opacity: 0;
}
</style>
```

关于 transition 标签的 mode 属性，默认值是 in-out，表示进入动画和退出动画同时执行，这里设置为 out-in，表示退出动画执行完毕后再执行进入动画

### 动画

可以在 _-enter-acive 或 _-leave-acive 中添加动画属性，这样可以自定义进入和离开的动画

如果 _-enter-acive 或 _-leave-acive 中同时有 transition 和 animation 属性，并且它们的时长不一样，可以通过给 transition 标签添加 type="transition" 或 type="animation" 指定过渡的时间

transition 标签有 apppear 属性，设置后可以在页面第一次展示时加载进入动画

[更多 transition 介绍](https://cn.vuejs.org/api/built-in-components.html#transition)

### 事件钩子

Vue 为动画提供了许多 [事件钩子](https://cn.vuejs.org/guide/built-ins/transition#javascript-hooks)，可以在钩子函数中使用 Web Animation API 实现动画

```
<template>
  <button type="button" @click="flag = !flag">Toggle</button>
  <transition @enter="enter" @leave="leave" :css="false">
    <h2 v-if="flag">Hello</h2>
  </transition>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      flag: false
    }
  },
  methods: {
    enter(el, done) {
      const animation = el.animate([{ transform: "scale3d(0,0,0)" }, {}], {
        duration: 1000
      })

      animation.onfinish = () => {
        done()
      }
    },
    leave(el, done) {
      const animation = el.animate([{}, { transform: "scale3d(0,0,0)" }], {
        duration: 1000
      })

      animation.onfinish = () => {
        done()
      }
    }
  }
}
</script>
```

:css="false" 属性可以告诉 Vue 不检查 CSS 动画，直接使用 JS 动画

:css 属性默认值是 true，这样就算没有定义 JS 动画，Vue 也可以通过 CSS 动画知道何时调用事件钩子函数，并且 enter 和 leave 钩子不用再传递 done 回调函数（用于通知 Vue 动画完成）

关于 [transition 属性](https://cn.vuejs.org/api/built-in-components.html#transition)

### transition-gruop

transition-group 标签专门用于为循环列表提供动画，它的属性和 transition 基本一致，transition-group 不能设置 mode 属性

示例：点击 Add 按钮，会随机在列表中添加一项，点击列表项，这个列表项会消失

```
<template>
  <button @click="addItem">Add</button>
  <ul>
    <transition-group name="fade">
      <li v-for="(number, index) in numbers" :key="number" @click="removeItem(index)">
        {{ number }}
      </li>
    </transition-group>
  </ul>
</template>
```

这样虽然实现了每个列表项的动画（fade），但是当新列表项出现，下方列表项向下移动的过程却没有动画，可以通过在 css 中添加 fade-move 类实现

```
.fade-move {
    transition: all 1s linear;
}
```

列表项删除时，下方列表项向上移动仍然没有动画，可以设置 fade-leave-active 解决问题：

```
fade-leave-active {
    position: absolute;
}
```

这样做会让列表项在退出动画过程中不再占据空间，下方列表项就不再需要等待上方列表项完全消失，可以执行 fade-move 过渡动画

### Animate.css

流行动画库，[官网](https://animate.style/)，可以通过 npm 或 cdn 引入

transition 标签提供了属性，可以自定义 CSS 动画类的名称：

```
 /**
   * 用于自定义过渡 class 的 prop。
   * 在模板中使用短横线命名，例如：enter-from-class="xxx"
   */
  enterFromClass?: string
  enterActiveClass?: string
  enterToClass?: string
  appearFromClass?: string
  appearActiveClass?: string
  appearToClass?: string
  leaveFromClass?: string
  leaveActiveClass?: string
  leaveToClass?: string
```

比如在上文的示例基础上改造：

```
<template>
  <button @click="addItem">Add</button>
  <ul>
    <transition-group name="fade"
      enter-active-class="animate__animated animate__bounceIn"
      leave-active-class="animate__animated animate__bounceOut"
    >
      <li v-for="(number, index) in numbers" :key="number" @click="removeItem(index)">
        {{ number }}
      </li>
    </transition-group>
  </ul>
</template>
```

覆盖默认的动画时长：

```
.animate__animated {
    animation-duration: 1.5s;
}
```

保证删除列表项的同时，下方列表项上移会应用 fade-move 过渡动画：

```
.animate__bounceOut {
    position: absolute;
}
```

# 前端工具

## Sass

一种 CSS 预处理语言，运行时需要将 sass/scss 文件编译为 css 文件，是 css 的超集

安装

```
npm install sass --save-dev
```

`--save-dev` 指定 sass 保存到开发依赖中（devDependencies）

在 vite 中可以通过在 main.js 文件中使用 import 直接导入 sass 文件，vite 会自行编译打包

## PostCSS

在编写完 CSS 后对其进行处理

PostCSS 有许多插件，用于提供各种功能：

autoprefixer 插件用于为 CSS 添加浏览器供应商前缀（-webkit- 等）

```
npm install autoprefixer --save-dev
```

vite 中内置了 PostCSS，需要通过在根目录创建 postcss.config.cjs 文件来激活

```
module.exports = {
    plugins: [require('autoprefixer')]
}
```

这个文件对 postcss 进行配置，使用 autoprefixer 插件

## ESLint

ESlint 提供了许多规则，以检查代码格式是否符合规范

安装 eslint：

```
npm install eslint --save-dev
```

安装 [globals](https://www.npmjs.com/package/globals)（用于在 eslint 中配置 JS 运行环境）

```
npm install globals --save-dev
```

由于 vite 中没有集成 ESlint，必须通过社区插件将 ESlint 集成到工作流中：

[vite-plugin-eslint](https://www.npmjs.com/package/vite-plugin-eslint)

```
npm install vite-plugin-eslint --save-dev
```

[vite 配置插件](https://cn.vitejs.dev/guide/using-plugins.html#adding-a-plugin)： 在根目录创建 vite.config.js 以配置 ESlint

```
import { defineConfig } from 'vite'
import eslint from 'vite-plugin-eslint'

export default defineConfig({
  plugins: [eslint()]
})
```

还需要配置 eslint，创建文件 eslint.config.js

```
import globals from "globals";

export default [{
    languageOptions: {
        globals: {
            ...globals.browser,
        },

        ecmaVersion: 2022,
        sourceType: "module",
    },

    rules: {
        // 当使用单引号时会报错
        quotes: "error",
    },
}];
```

这时启动项目，就可以看到 eslint 的报错，列举了检查出的错误

为了更直观地在编辑器中看到错误，安装 vscode 插件：ESlint

ESlint 支持强制修复这些错误，这需要在 package.json 文件中配置指令。比如，修复 main.js 文件中的错误 `"lint": "eslint main.js --fix"`，配置完成后再控制台执行 `npm run lint` 执行指令即可修复错误

在 VSCode 中启用 ESlint 在保存文件时自动修复：

- 打开 VScode 的 settings.json 文件，添加以下配置：

```
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": "explicit"
}
```

## Prettier

格式化代码，功能和 ESlint 有重复，只不过 Prettier 只能检查代码格式，而 ESlint 还可以检查其他代码规范（比如变量类型 var const 的使用）

## TailwindCSS

提供了大量原子类，一个 CSS class 就是一条 CSS 样式，不用频繁地在 html 和 css 之间切换

## PurgeCSS

构建时，会剔除在项目中中没有用到的第三方库的多余样式，以减小第三方库的体积

## Pinia

Vue 提供的状态管理工具，可以集中管理状态数据，组件不用再通过一层一层的组件传值获取状态数据，可以直接进行访问

[选项式 API 使用 Pinia](https://pinia.vuejs.org/zh/cookbook/options-api.html)

## vee-validate

为 vue 打造的表单验证库，[官网](https://vee-validate.logaretm.com/v4/)

vee-validate 提供了组件 Form Field

## Firebase

为客户端提供后端服务的开发平台

[官方文档](https://firebase.google.com/docs/guides?hl=zh-cn)

## JSON Web Token

身份验证令牌

[官网](https://jwt.io/)

## Vue Router

[官方文档](https://router.vuejs.org/zh/guide/)

单页面应用都需要采用路由进行页面跳转，对比传统方式，节省带宽，减少性能开销

## Font Awesome

免费或付费 icon

导入后，通过 CSS class 使用

[官网](https://docs.fontawesome.com/)

## Howler.js

js 音频库

[文档](https://github.com/goldfire/howler.js#documentation)

## Vue i18n

internationalization，国际化

[Vue i18n](https://vue-i18n.intlify.dev/)

## Lodash

字符串处理 js 库

[官网](https://lodash.com/)

## NProgress.js

进度条

[官网](https://ricostacruz.com/nprogress/)

## Code Coverage

google devtools 提供的工具，在开发者工具中，可以查看当前页面使用的文件，以及文件中代码的使用情况

## rollup-plugin-visualizer

[rollup](https://rollupjs.org/) 是一个打包优化工具

vite 使用了 rollup，所以可以使用 [rollup-plugin-visualizer](https://www.npmjs.com/package/rollup-plugin-visualizer) 来进行打包优化，在 vite.config.js 中注册这个插件

## vercel

网站部署

[官网](https://vercel.com/)

## vitest

vite 的测试框架

[官网](https://cn.vitest.dev/guide/)
