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
  - [](#)


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

## 