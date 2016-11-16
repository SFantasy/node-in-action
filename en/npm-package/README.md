# Develop npm package

In the first chapter, I will introduce you the develop process of [node-validator](https://github.com/SFantasy/node-validator) and give your some instructions about how to develop a npm module, write test case about it and finally publish it to the npm. Anyway, welcome to the family of npm.

Before develop the first npm module, let's have a look at what it is like.

Firstly, you can have `node-validator` installed on your own computer with a simple command `npm install is-valid` in the Node.js REPL or create an empty JavaScript file in any place:

```js
var validator = require('is-valid');

validator.isEmail('foo@bar.net'); // true
```

Yes, that's it. It's really simple but also meaningful.
