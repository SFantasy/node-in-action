# NPM 基础

## 简介

NPM，一般认为是 Node Package Manager 的缩写，当然也有很多其他的[别称](https://github.com/npm/npm-expansions)，这一点可以在 NPM 的主页的左上角作为一个彩蛋看到。

简单来说，NPM 类似 Java 中的 Maven，Python 中的 pip，Ruby 中的 Gem 等，可以方便的管理 Node.js 项目中的依赖，在项目中以 `package.json` 的形式展示。

## 基本使用

以下介绍NPM的基本使用方式，简单来说包含了 Node.js 模块的依赖管理、模块的管理以及脚本的运行。

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

- 全局安装指定模块

```sh
npm install express -g
```

### 管理模块

- 初始化模块

```sh
npm init
```

这个命令其实只是通过一种交互式的方式生成一个项目的`package.json`文件，而并不会创建一些常见的 NPM 模块目录的文件夹。

- 发布模块

```sh
npm publish
```

无论是第一次发布模块，亦或是更新模块之后发布更新到NPM上，都需要这个命令。不过要注意的是，在发布之前需要通过 `npm adduser` 添加注册过的NPM账号。

- 取消发布模块

```sh
npm unpublish
```

## NPM镜像

鉴于 NPM 在国内会受到 GFW 的影响，可以选择使用 [TaoNPM](https://npm.taobao.org/) 作为 NPM 的镜像，方便安装 NPM 中的模块。

或者可以选择直接安装 CNPM 加速项目依赖的安装：

```sh
npm install -g cnpm
```
