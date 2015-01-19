# 完善工具

在前面的章节中，已经介绍了如何通过`request`请求有道词典的接口、使用`colors`给命令行工具添加颜色等。毕竟那些都是组成我们这个工具的一些部分内容，现在我们需要的是如何将之前学习到的内容组成一个完整的工具。

## 获取参数

在第一节中介绍了TJ的`commander.js`工具，不过由于node-translator并不需要获取很多参数，所以完全可以直接获取命令行中的参数。

查阅[Node.js的文档](http://nodejs.org/api/process.html#process_process_argv)后，可以了解到通过Node.js内置的`process.argv`获取Node.js的命令行参数的数组，例如：

```js
node test.js a b
```

`process.argv`的返回结果为`['node', 'test.js', 'a', 'b']`。

在「调用接口」一节中，我们已经可以通过GET的方式获取到所需要的数据，但是在实际的使用中，所需要查阅的单词一定是通过命令行参数传递的方式获取而非直接写入到程序中的。

所以我们可以通过上述提到的方式获取参数：

```js
var param = process.argv[2];
var word = param ? param : '';
```

然后，将获取到的参数通过拼接字符串的方式添加到URL中即可请求到需要的返回值：

```js
var request = require('request');

request('http://fanyi.youdao.com/openapi.do?keyfrom=node-translator&key=2058911035&type=data&doctype=json&version=1.1&q=' + word, function (error, response, body) {
    if (!error && response.statusCode == 200) {
        console.log(body);
    }
});
```
