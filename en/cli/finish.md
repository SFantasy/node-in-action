# Complete the tool

In the previous sections, we have already know how to use `request` to request the API of Youdao Dictionary and use `colors` to make the tool colorful.

And now we are going to make it complete.

## Get parameters

In the first chapter, I've introduced `commander.js` which is created by TJ, however, `node-translator` does not need lots of parameters, so we could get the parameters directly from the command line.

It is easy for us to get the array of parameters by using `process.argv` according to the official [Node.js documentation](http://nodejs.org/api/process.html#process_process_argv).

```js
node test.js a b
```

The return of `process.argv` is `['node', 'test.js', 'a', 'b']`.

In the previous section, we could get the data needed by `GET` method. Actually, there are more situations to pass parameters by command line rather than hard coded in our programs.

So we are able to get parameters in the way we mentioned above:

```js
var param = process.argv[2];
var word = param ? param : '';
```

Then we could append parameters to the URL and request for appropriate return values:

```js
var request = require('request');

request('http://fanyi.youdao.com/openapi.do?keyfrom=node-translator&key=2058911035&type=data&doctype=json&version=1.1&q=' + word, function (error, response, body) {
    if (!error && response.statusCode == 200) {
        console.log(body);
    }
});
```
