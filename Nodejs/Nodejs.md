# 基本命令

## node

进入 node，可以和浏览器控制台一样写 JS

## 控制台内命令或快捷键

### Tab

#### 全局变量

双击 Tab 键，可以打印所有全局变量

#### 所有方法

输入 `对象名.` ，例如 `String.`，在双击 Tab，可以查看对象的所有方法

### ctrl + D

退出 node

### .exit

退出 node

### \_

\_ 表示上次执行的结果

```
> 3+8
output: 11
> _+3
output: 14
```

### node

node 文件名，执行文件，例如：

```
node index.js
```

## 内置模块

### fs

file system，文件系统

#### readFileSync

同步读取文件

```
const textIn = fs.readFileSync("./txt/input.txt", "utf-8");
console.log(textIn);
```

#### writeFileSync

同步写入文件

```
const textOut = `This is what we know about the avocado: ${textIn}.\nCreated on ${Date.now()}`;
fs.writeFileSync("./txt/output.txt", textOut);
```

#### readFile

异步写入文件

```
fs.readFileSync("./txt/input.txt", "utf-8", (error,data) => {
    // 完成读取后执行的代码
})
```

#### writeFile

异步读取文件

```
fs.writeFileSync("./txt/output.txt", textOut，error => {
    // 完成写入后执行的代码
})
```
