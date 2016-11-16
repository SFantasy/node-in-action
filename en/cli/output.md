# Beautify the output

Actually, we have finished the core feature of the tool with the data we needed.

However, it is better to output the result in a more user-friendly way for a command line tool.

## Add color

[colors](https://www.npmjs.com/package/colors) is a module for adding colors for command line tools, and here is a simple example:

```js
var colors = require('colors');

console.log('Color'.green);
```

By adding the name of a color after a string, we could make the output string colorful. For the list of colors it supports, you'd better refer the document on Github or npm.

## Format the output style

In the last chapter, we got the result in JSON as below:

    {"translation":["测试"],"basic":{"us-phonetic":"tɛst","phonetic":"test","uk-phonetic":"test","explains":["n. 试验；检验","vt. 试验；测试","vi. 试验；测试","n. (Test)人名；(英)特斯特"]},"query":"test","errorCode":0,"web":[{"value":["测试","试验","检验"],"key":"test"},{"value":["测试工程师","测试员","软件测试工程师"],"key":"Test engineer"},{"value":["硬度试验","硬度测试","硬度实验"],"key":"hardness test"}]}

Formatted:

    {
        "translation":["测试"],
        "basic":{
            "us-phonetic":"tɛst",
            "phonetic":"test",
            "uk-phonetic":"test",
            "explains":[
                "n. 试验；检验",
                "vt. 试验；测试",
                "vi. 试验；测试",
                "n.(Test)人名；(英)特斯特"
            ]
        },
        "query":"test",
        "errorCode":0,
        "web":[{
            "value":["测试","试验","检验"],
            "key":"test"
        },{
            "value":["测试工程师","测试员","软件测试工程师"],
            "key":"Test engineer"
        },{
            "value":["硬度试验","硬度测试","硬度实验"],
            "key":"hardness test"
        }]
    }

A better way to output the result should be with proper new lines, spaces. About this, you can refer the [output.js](https://github.com/SFantasy/node-translator/blob/master/lib/output.js) file in the 'node-translator'.
