# Node.js basics

If you have some basic knowledge about Node.js, you can skip this chapter or just regard it as a reference.

## Node.js version "Hello World"

```js
console.log('Hello World');
```

- Run the script on your terminal

```sh
node test.js
```

## Version management of Node.js

With the effort of worlds's contributors, Node.js is getting better and better. So it is a usual for us to change and update the version of Node.js on our machine.

I recommend [NVM](https://github.com/creationix/nvm) to do this stuff. Its features are complete and convinent. For more infomation, you could visit its Github page.

## Module system

Node.js implement the [CommonJS sepc]((http://wiki.commonjs.org/wiki/Introduction)):

- Use `global` to define a global variable:

```js
global.test = true;
```

- Use `require` to import a module:

```js
var fs = require('fs');
```

- Use `module.exports` to exports a module:

```js
module.exports = function () {
    console.log('Hello Node.js');
};
```

- Use `exports` to export multiple methods or Object:

```js
exports.foo = function () {};
exports.bar = function () {};
```

## The simplest Node.js server:

```js
var http = require('http');

http.createServer(function (req, res) {
    res.send('Hello');
    res.end();
}).listen(3000);
```

Visit it on [localhost:300](http://localhost:3000) and you could see the word "Hello".
