# Node.js 基础

如果你已经有 Node.js 的编程基础，那么可以跳过此章节，但也不妨将其作为一个参考。

## Node.js 版本的 Hello World

```js
console.log('Hello World');
```

- 运行Node.js

```sh
node test.js
```

## Node.js 的版本管理

Node.js 的稳定版，亦即 LTS (Long Time Support) 版本是最为主流使用的版本，一般而言版本号为偶数 -- 4，6 等，而奇数版本的则为两个稳定版之间的中间产物。因此建议在使用的时候安装 LTS 的版本。

不同版本的 Node.js 还是有不少差异的，而造成这些差异的原因，包含了诸如 V8 的版本，诸如对 ES6 等标准中特性的实现等，所以，切换 Node.js 的版本可能是经常会做的一件事情。

Node.js 的版本可以通过 [NVM](https://github.com/creationix/nvm) 以及 [N](https://github.com/tj/n) 进行管理。

相比这两个工具而言，前者可能做的更为的完善、易用。当然你也不妨将两者都尝试一下，选择更为适合自己的。

## 模块系统

Node.js 实现的是[CommonJS规范](http://wiki.commonjs.org/wiki/Introduction)：

- 使用`global`定义全局对象

```js
global.test = true;
```

- 使用`require`引入模块

```js
var fs = require('fs');
```

- 使用`module.exports`输出模块

```js
module.exports = function () {
    console.log('Hello Node.js');
};
```

- 使用`exports`输出多个方法或者对象：

```js
exports.foo = function () {};
exports.bar = function () {};
```

## 最简单的Node.js服务器

使用Node.js的`http`模块可以创建一个最简易的HTTP服务器：

```js
var http = require('http');

http.createServer(function (req, res) {
    res.send('Hello');
    res.end();
}).listen(3000);
```

随后访问浏览器：`localhost:3000` 便可看到"Hello"字样。
