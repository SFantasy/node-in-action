# npm

## Introduction

npm is usually short for Node Package Manager, and there exists many other [alias](https://github.com/npm/npm-expansions).

In my opinion, the relationship between Node.js and npm is just similar with Maven on Java, PIP on Python and GEM on Ruby.

With npm, you could manage the dependencies of your Node.js projects with ease.

## Basic use

The basic usage of npm includes dependencies management, module management and scripts.

> Surely it is better to refer the documentation of npm or via `npm -l` or `man npm` to read the documentation.

### Install dependencies

- Install the dependencies of a projects

```sh
npm install
```

- Install a module

```sh
npm install express
```

- Install a module as project's dependency

```sh
npm install express --save
```

- Install a module as project's dev-dependency

```sh
npm install express --save-dev
```

### Module management

- Initial a module

```sh
npm init
```

This command only create a package.json for your module, and will not create other files.

- Publish a module

```sh
npm publish
```

No matter whether it is the first time you publish it, use this command. And it is a must to `npm adduse` before you publish.

## npm mirrors

Due to the existence of "GFW", developers in China can use [Taonpm](https://npm.taobao.org/) as the mirror of npm and install modules without panic.
