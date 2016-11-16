# npm 基础

## 简介

npm，一般认为是 Node Package Manager 的缩写，当然也有很多其他的[别称](https://github.com/npm/npm-expansions)，这一点可以在 npm 的主页的左上角作为一个彩蛋看到。

npm 类似 Java 中的 Maven，Python 中的 pip，Ruby 中的 Gem 等，可以方便的管理 Node.js 项目中的依赖，在项目中以 `package.json` 的形式展示。

## 基本使用

以下介绍 npm 的基本使用方式，简单来说包含了 Node.js 模块的依赖管理、模块的管理以及脚本的运行。

当然更好的方式是参阅npm的文档，或者通过 `npm -l` 与 `man npm` 本地查阅各种命令的用途。

### 安装模块依赖

- 安装项目所依赖的模块

```sh
npm install
```

- 安装指定模块

```sh
npm install express
```

- 安装指定模块并将其保存为项目依赖（会写入 `package.json` 文件的 `depdendencies` 字段）

```sh
npm install express --save
```

- 安装指定模块并将其保存为项目的开发依赖（会写入 `package.json` 文件的 `devDepdendencies` 字段）

```sh
npm install express --save-dev
```

- 全局安装指定模块

```sh
npm install express -g
```

上述命令有些可以写成更为简略的形式。

例如 `npm install express --save` 可以缩写为 `npm i express -S`，而 `npm install express --save-dev` 可以缩写为 `npm i express -D`，是不是很方便呢。

### 管理模块

- 初始化模块

```sh
npm init
```

这个命令其实只是通过一种交互式的方式生成一个项目的 `package.json` 文件，而并不会创建一些常见的 npm 模块目录的文件夹。

- 发布模块

```sh
npm publish
```

无论是第一次发布模块，亦或是更新模块之后发布更新到npm上，都需要这个命令。不过要注意的是，在发布之前需要通过 `npm adduser` 添加注册过的npm账号。

- 取消发布模块

```sh
npm unpublish
```

npm 在 [left-pad](http://blog.npmjs.org/post/141577284765/kik-left-pad-and-npm) 事件后， 规定在模块发布后的一定时间后就不能 `unpublish`。

## npm 镜像

鉴于 npm在国内会受到 GFW 的影响，可以选择使用 [Taonpm](https://npm.taobao.org/) 作为 npm 的镜像，方便安装 npm 中的模块。

或者可以选择直接安装 cnpm 加速项目依赖的安装：

```sh
npm install -g cnpm
```
