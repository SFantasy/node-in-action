# 开发命令行工具

在第二章中，我们将会学习如何使用Node.js开发命令行工具。

在*nix系统中，命令行工具是平日里开发、工作、日常生活的必备品，而使用Node.js可以快速的开发一个自己所需要或喜好的命令行工具。

一个Node.js的命令行工具其实都是通过`node`的可执行文件来运行的，然后通过NPM工具写入`/usr/local/bin`这样的可执行文件目录以达到可以通过命令行运行的目的。

以下是一个简单的Node.js的脚本：

```sh
#!/usr/bin/env node

console.log('Hello CLI');
```

## 命令行参数

在命令行之中，我们往往需要加入很多的参数。[TJ](https://github.com/tj)开发了一个非常实用的模块 -- [Commander.js](https://github.com/tj/commander.js)，专门用于获取命令行参数，从而方便程序的编写。

例如，我们可以这样使用commander.js:

```sh
#!/usr/bin/env node

var program = require('commander');

program.version('0.0.1').parse(process.argv);
```

然后就可以这样运行可执行文件获取其版本：

```sh
node test --version
```

此工具适合那些需要传入很多参数并获取的程序。

## node-translator

node-translator是一个在命令行中使用有道字典的API进行翻译的命令行工具，在本章中，我们就要完成这样一个非常实用的命令行工具：

![node-transaltor](http://7u2gnn.com1.z0.glb.clouddn.com/node-translator.png)
