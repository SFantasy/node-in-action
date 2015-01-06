# 开发NPM包

> **NOTE**: 关于Node.js与NPM的有关内容，可以参考附录中的[Node.js基础部分](../appendix/basic.md)

在第一章中，将通过[node-validator](https://github.com/SFantasy/node-validator)的开发过程来介绍如何从头开发、测试、维护一个[NPM](https://www.npmjs.com/)的包，加入NPM的大家庭。

在学习开发你的第一个NPM包之前，让我们一起来看看将要实现的是一个什么样功能的包：

首先，`node-validator`可以通过`npm install is-valid`安装到你的项目中；

接下来，可以通过简单的代码来看看这个即将完成的包实现的功能，当然你也可以使用Node.js的REPL：

```
var validator = require('is-valid');

validator.isEmail('foo@bar.net'); // true
```

是的，我们的第一步很简单，但是也很重要。
