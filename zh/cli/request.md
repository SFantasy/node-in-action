# 调用接口

将要开发的这个命令行工具的核心功能就是通过请求有道词典的 API，然后将接口返回的结果通过一些处理之后输出到终端。

## 使用request

[request](https://www.npmjs.com/package/request) 是 npm 中被使用最多的模块之一，每天有20~30万左右的下载量。

正如前端开发中 jQuery 的 Ajax 方法和 iOS 开发中的 AFNetworking 一样，在 Node.js 应用中被广泛当作请求接口之用。

request 的使用亦是非常简单易懂，以下是request的最简使用方式：

```js
var request = require('request');

request('http://www.google.com', function (error, response, body) {
    if (!error && response.statusCode == 200) {
        console.log(body); // 输出请求到的body
    }
});
```

## 有道词典

有道词典提供了开发者注册、申请调用API的[开放平台](http://fanyi.youdao.com/openapi)，开发者在填写了必要的信息之后就可以获得不限时间的 API key。

基本的 API 请求形式也比较简单，可以在 URL 中添加参数后直接通过 GET 的方式请求之，例如有以下 URL:

```
http://fanyi.youdao.com/openapi.do?keyfrom=node-translator&key=2058911035&type=data&doctype=json&version=1.1&q=test
```

具体的参数就不一一分析了，这些都可以在开放平台的文档中找到。

接下来，可以使用 request 测试一下接口调用，我们将会通过接口获取单词"test"的中文释义：

```js
var request = require('request');

request('http://fanyi.youdao.com/openapi.do?keyfrom=node-translator&key=2058911035&type=data&doctype=json&version=1.1&q=test', function (error, response, body) {
    if (!error && response.statusCode == 200) {
        console.log(body);
    }
});
```

假定上述代码保存为`request-test.js`，然后运行之：`node request-test.js`，便可得到以下结果：

    {"translation":["测试"],"basic":{"us-phonetic":"tɛst","phonetic":"test","uk-phonetic":"test","explains":["n. 试验；检验","vt. 试验；测试","vi. 试验；测试","n. (Test)人名；(英)特斯特"]},"query":"test","errorCode":0,"web":[{"value":["测试","试验","检验"],"key":"test"},{"value":["测试工程师","测试员","软件测试工程师"],"key":"Test engineer"},{"value":["硬度试验","硬度测试","硬度实验"],"key":"hardness test"}]}

可以发现调用接口后返回的body中的内容即为我们所需的JSON数据。
