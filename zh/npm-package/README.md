# 开发NPM模块

在第一章中，将通过 [node-validator](https://github.com/SFantasy/node-validator) 的开发过程来介绍如何从头开发、测试、维护一个[NPM](https://www.npmjs.com/)的模块，加入 NPM 的大家庭。

在学习开发你的第一个 NPM 模块之前，让我们一起来看看将要实现的是一个什么样功能的包。

`node-validator` 是一个用来校验字符串的 Node.js 模块，我们可以通过

```sh
npm install is-valid --save
```

将其作为依赖安装到你的项目中。

接下来，可以通过简单的代码来看看这个即将完成的模块实现的功能，当然你也可以使用Node.js的REPL：

```js
var validator = require('is-valid');

validator.isEmail('foo@bar.net'); // true
```

是的，我们的第一个模块很简单，但是学到的内容却很重要。
