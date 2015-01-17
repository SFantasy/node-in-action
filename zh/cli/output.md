# 美化输出

在获得了必要的数据之后，其实已经完成了整个命令行工具的核心功能了。

但是作为一个命令行的工具，还是比较好的输出形式以增强用户体验。

## 增添色彩

使用[colors](https://www.npmjs.com/package/colors)可以为命令行工具的输出增添色彩。

```js
var colors = require('colors');

console.log('Color'.green);
```

只需要简单的在字符串之后添加想要输出的颜色即可。具体支持的颜色可以移步其NPM或者Github上的文档查阅。

## 调整输出格式

在上一节中，我们获取到的JSON返回值如下：

    {"translation":["测试"],"basic":{"us-phonetic":"tɛst","phonetic":"test","uk-phonetic":"test","explains":["n. 试验；检验","vt. 试验；测试","vi. 试验；测试","n. (Test)人名；(英)特斯特"]},"query":"test","errorCode":0,"web":[{"value":["测试","试验","检验"],"key":"test"},{"value":["测试工程师","测试员","软件测试工程师"],"key":"Test engineer"},{"value":["硬度试验","硬度测试","硬度实验"],"key":"hardness test"}]}


格式化后可以得到：


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

比较好的输出格式应该包含合适的空行、空格与缩进，可以参考我在node-translator中写的[output.js](https://github.com/SFantasy/node-translator/blob/master/lib/output.js)。
