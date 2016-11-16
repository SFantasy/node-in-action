# Request API

The core feature of our command line tool is to request the API of Youdao dic. After handling with the response of the API, we could display the results to the terminal.

## Use request

[request](https://www.npmjs.com/package/request) is one of the most popular module on npm, it has been downloaded for 20~30 million time per day.

Just like Ajax methods of jQuery used in Front-end development and AFNetworking in iOS development, **request** is widely used in Node.js applications for requesting APIs.

And it is extremely easy and simple to understand its usage, following is the simplest way to use it:

```js
var request = require('request');

request('http://www.google.com', function (error, response, body) {
    if (!error && response.statusCode == 200) {
        console.log(body);
    }
});
```

## Youdao dic

Youdao dic provides a [Open platform](http://fanyi.youdao.com/openapi) for developers to register and apply for API services.

The most common way to request API is quite simple, we could just add parameters in the URL and request the API with GET method:

```
http://fanyi.youdao.com/openapi.do?keyfrom=node-translator&key=2058911035&type=data&doctype=json&version=1.1&q=test
```

It's convenient for us to find what the parameters mean in the documentations.

Next, we can have a try to call the API using request, we are going to get the Chinese meaning of the word 'test':

```js
var request = require('request');

request('http://fanyi.youdao.com/openapi.do?keyfrom=node-translator&key=2058911035&type=data&doctype=json&version=1.1&q=test', function (error, response, body) {
    if (!error && response.statusCode == 200) {
        console.log(body);
    }
});
```

Assuming the codes above has been saved as a JavaScirpt file named `request-test.js`, we could run it using `node request-test.js` and get the following result:

    {"translation":["测试"],"basic":{"us-phonetic":"tɛst","phonetic":"test","uk-phonetic":"test","explains":["n. 试验；检验","vt. 试验；测试","vi. 试验；测试","n. (Test)人名；(英)特斯特"]},"query":"test","errorCode":0,"web":[{"value":["测试","试验","检验"],"key":"test"},{"value":["测试工程师","测试员","软件测试工程师"],"key":"Test engineer"},{"value":["硬度试验","硬度测试","硬度实验"],"key":"hardness test"}]}

That's it! The JSON contents in the result body is what we need for our tool.
