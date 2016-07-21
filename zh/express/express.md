# 使用 Express

[Express](http://expressjs.com/) 堪称是 Node.js 领域最为流行的Web开发框架，由著名的开发者 [TJ](https://github.com/tj) 开发，现在已经衍生到4.x版本。

## Express的"Hello World"

以下是一个简单的使用 Express 作为服务器的代码，通过 `res.send()` 方法将 `Hello World` 字符串作为 Response 返回：

```js
var express = require('express');
var app = express();

app.get('/', function (req, res) {
    res.send('Hello World');
});

app.listen(3000, function () {
    console.log('Express server started.');
});
```

运行 `app.js`:

```sh
node app.js
```

## Express应用生成器

Express亦提供了诸如其他著名Web框架一样的快速生成项目的工具：[Express Generator](https://github.com/expressjs/generator)

- 安装：

```sh
npm install -g express-generator
```

- 快速生成Express项目：

```sh
express test
```

随后进入到该目录，并安装所依赖的模块：

```sh
cd test
npm install
```

此时，已经可以通过`npm start`启动这个自动生成的项目了。
