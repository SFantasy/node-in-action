# NPM基础

## 简介

NPM，一般认为是Node Package Manager的缩写，当然也有很多其他的[别称](https://github.com/npm/npm-expansions)，这一点可以在NPM的主页的左上角作为一个彩蛋看到。

简单来说，NPM类似Java中的Maven，Python中的pip，Ruby中的Gem等，可以方便的管理Node.js项目中的依赖。

## 基本使用

以下介绍NPM的基本使用方式，简单来说包含了Node.js模块的依赖管理、模块的管理以及脚本的运行。

当然更好的方式是参阅NPM的文档，或者通过`npm -l`与`man npm`本地查阅各种命令的用途。

### 安装模块依赖

- 安装项目所依赖的模块

```sh
npm install
```

- 安装指定模块

```sh
npm install express
```

- 安装指定模块并将其保存为项目依赖

```sh
npm install express --save
```

- 安装指定模块并将其保存为项目的开发依赖

```sh
npm install express --save-dev
```

### 管理模块

- 初始化模块

```sh
npm init
```

这个命令其实只是通过一种交互式的方式生成一个项目的`package.json`文件，并不会创建一些可能是比较常见的NPM模块目录。

- 发布模块

```sh
npm publish
```

无论是第一次发布模块，亦或是更新模块之后发布更新到NPM上，都需要这个命令。不过要注意的是，在发布之前需要通过`npm adduser`添加注册过的NPM账号。
