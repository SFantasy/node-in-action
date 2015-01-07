# 编写测试用例

Node.js中已经有很多优秀的测试框架，例如：[mocha](https://www.npmjs.com/package/mocha), [jasmine](https://github.com/jasmine/jasmine)等。

这里，我们选择了mocha作为测试框架。

> 想要了解mocha的读者，可以访问其主页以获取更多信息: [mochajs.org](http://mochajs.org/)

- 安装mocha

```sh
npm install -g mocha
```

mocha集成了很多的特性，用户可以根据项目的特点选择合适的特性进行测试用例的编写。而在此，我们可以选择"assertion"（断言）来对"node-validator"进行测试。

- 引入`assert`

```js
var assert = require('assert');
```

"assert"中包含了很多Node.js中有关断言的模块，例如[shoud.js](https://github.com/visionmedia/should.js), [expext](https://github.com/LearnBoost/expect.js)等。这些模块多数都是行为驱动开发（BDD）的实践。

- assert示例

```js
describe('Array', function() {
    describe('#indexOf()', function() {
        it('should return -1 when the value is not present', function() {
            [1,2,3].indexOf(5).should.equal(-1);
            [1,2,3].indexOf(0).should.equal(-1);
        });
    });
});
```

这看起来就像是我们用英语描述了一件事情。没错，我们要做的就是描述"node-validator"中的函数运行正确是什么样的，运行错误是什么样的。

照着上面的例子，可以写出测试用例代码原型：

```js
var assert = require('assert');
var validator = require('validator-test');

describe('Validator', function () {
    describe('#isEmail', function () {
        it('should return true when the string is an email address', function () {
            if (validator.isEmail('foo@bar.net') !== true) {
                throw new Erorr('Validator not right');
            }
        });
    });
});
```

然后在终端中输入mocha，会自动运行`test`目录下的`test.js`文件：

```sh
mocha
```

得到以下结果：

```sh
Validator
#isEmail
✓ should return true when the string is an email address


1 passing (6ms)
```

所以接下来要做的事情，就是为每一个"node-validator"中的函数编写测试用例，以期将所有的情况都覆盖到。
