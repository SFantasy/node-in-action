# 开发node-validator

"node-validator"，顾名思义，我们要开发的是一个验证字符串合法性的NPM模块。

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

不过为了项目的可扩展性，我们会把所有实现代码放在`lib`文件夹内，这样一来`index.js`就可以只作为一个入口文件存在：

```js
module.exports = require('./lib');
```

接下来在`lib`文件夹中创建一个`index.js`文件，用以编写我们的模块的「内容」：

```js
module.exports = function () {
    console.log('Hello NPM!');
};
```

是的，这就是NPM版本的 "Hello, World!""。

这时候可以创建另外一个 JavaScript 文件，然后 `require('./lib')` 来测试、运行一下刚刚编写的代码。

在 CommonJS 的模块系统中，`module.exports` 可以输出一个函数，也可以输出一个对象。所以我们可以这样编写`lib`中的`index.js`:

```js
module.exports = {
    isEmail: function () {},
    isAllEnglish: function () {}
};
```

接下来，就可以开始编写函数体内的正则代码了：

```js
module.exports = {
    isEmail: function (str) {
        return /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?(?:\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$/.test(str);
    },
    isAllEnglish: function (str) {
        return /^[a-zA-Z]+$/.test(str);
    }
}
```

那么到了这里，第一个版本的`node-validator`就已经完工了。

通过 `npm link` 可以将当前的NPM包链接到存放系统中 NPM 模块的文件夹。也就是说，当前文件夹的改动会在运行的时候体现出来，所以也是开发NPM模块时候的利器。

假设我们在 `package.json` 文件中将 `name` 命名为 `validator-test`，那么就已经可以通过如下代码使用了新鲜出炉的模块了：

```js
var validator = require('validator-test');

validator.isEmail('foo@bar.net'); // true
```

我们可以不断的在这个对象中添加函数，当然也可以根据不同的类别分成不同的文件模块，通过`require`的方式构成我们的第一个完整的模块。
