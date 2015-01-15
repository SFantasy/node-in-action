# 美化输出

在获得了必要的数据之后，其实已经完成了整个命令行工具的核心功能了。

但是作为一个命令行的工具，还是比较好的输出形式以增强用户体验。

## 增添色彩

使用[colors](https://www.npmjs.com/package/colors)可以为命令行工具的输出增添色彩。

```js
var colors = require('colors');

console.log('Color'.green);
```

只需要简单的在字符串之后添加想要输出的颜色即可。具体支持的颜色可以移步其NPM或者Github上的文档。
