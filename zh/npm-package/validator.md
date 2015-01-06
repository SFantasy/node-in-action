# 开发node-validator

首先我们需要建立一个包的目录：

```
node-validator
  |- lib/
  |- test/
  |- package.json
  |- index.js
  |- README.md
```

由于项目比较简单，可以把所以的代码放在根目录下的`index.js`中。

当然为了项目的可扩展性，我们会把所有实现代码放在`lib`文件夹内，这样一来`index.js`就可以只作为一个入口文件存在：

```js
module.exports = require('./lib');
```

接下来在`lib`文件夹中创建一个`index.js`文件，用以编写我们的包的「内容」：

```js
module.exports = function () {
    console.log('Hello NPM!');
};
```

是的，这就是NPM版本的"Hello, World!"。

在CommonJS的模块系统中，`module.exports`可以输出一个函数，也可以输出一个对象。
