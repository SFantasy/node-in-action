# 使用Express

[Express](http://expressjs.com/)堪称是Node.js领域最为流行的Web开发框架，现在已经衍生到4.x版本。

## Express的"Hello World"

以下是一个简单的使用Express作为服务器的代码，通过`res.send()`方法将`Hello World`字符串输出返回到页面上：

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

运行`app.js`:

```sh
node app.js
```
