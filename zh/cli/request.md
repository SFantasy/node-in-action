# 调用接口

## 使用request

[request](https://www.npmjs.com/package/request)是NPM中被使用最多的模块之一，每天有20~30万左右的下载量。

正如前端开发中jQuery的Ajax方法和iOS开发中的AFNetworking一样，在Node.js应用中被广泛当作请求接口之用。

request的使用亦是非常简单易懂，以下是request的最简使用方式：

```js
var request = require('request');

request('http://www.google.com', function (error, response, body) {
    if (!error && response.statusCode == 200) {
        console.log(body); // 输出请求到的body
    }
});
```

## 有道词典

有道词典提供了开发者注册、申请调用API的[开放平台](http://fanyi.youdao.com/openapi)，开发者在填写了必要的信息之后就可以获得不限时间的API key。

基本的API请求形式也比较简单，可以在URL中添加参数后直接通过GET的方式请求之，例如有以下URL:

```
http://fanyi.youdao.com/openapi.do?keyfrom=node-translator&key=2058911035&type=data&doctype=json&version=1.1&q=test
```

具体的参数就不一一分析了，这些都可以在开放平台的文档中找到。

接下来，可以使用request测试一下接口调用：

```js
var request = require('request');

request('http://fanyi.youdao.com/openapi.do?keyfrom=node-translator&key=2058911035&type=data&doctype=json&version=1.1&q=test', function (error, response, body) {
    if (!error && response.statusCode == 200) {
        console.log(body);
    }
});
```

假定上述代码保存为`request-test.js`，然后运行之：`node request-test.js`，便可得到以下结果：

``` {"translation":["测试"],"basic":{"us-phonetic":"tɛst","phonetic":"test","uk-phonetic":"test","explains":["n. 试验；检验","vt. 试验；测试","vi. 试验；测试","n. (Test)人名；(英)特斯特"]},"query":"test","errorCode":0,"web":[{"value":["测试","试验","检验"],"key":"test"},{"value":["测试工程师","测试员","软件测试工程师"],"key":"Test engineer"},{"value":["硬度试验","硬度测试","硬度实验"],"key":"hardness test"}]}
```

可以发现调用接口后返回的body中的内容即为我们所需的JSON数据。
