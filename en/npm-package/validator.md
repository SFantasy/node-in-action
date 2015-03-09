# A string validator

We are going to develop a NPM module which is used to validate string.

First of all, build the folder structure of a package:

```
node-validator
  |- lib/
  |- test/
  |- package.json
  |- index.js
  |- README.md
```

As the project is quite simple, it's fine to put all the codes in `index.js`.

However, we can place all the implement codes in the `lib` folder for extending the project later and regard the `index.js` file as an entrance of the moudle.

```js
module.exports = require('./lib');
```

Creating a `index.js` file in the `lib` in order to write the core of our moudle:

```js
module.exports = function () {
    console.log('Hello NPM!');
}
```

The program above is the NPM version of the well-known "Hello World". There's no problem to use `node index.js` to have a test of it.

In the module system of CommonJS, `module.exports` can output a function or an object. So we can easily write codes like this:

```js
module.exports = {
    isEmail: function () {},
    isAllEnglish: function () {}
};
```

After that, we can continue programming the module using regular expressions:

```js
module.exports = {
    isEmail: function (str) {
        return /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?(?:\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$/.test(str);
    },
    isAllEnglish: function (str) {
        return /^[a-zA-Z]+$/.test(str);
    }
}
```

Up to now, the first alpha version of `node-validator` is ready for use.

Using `npm link` command could place the current module to the system's NPM module folders. In the other words, if we modify the codes in our project, we could feel that when using the module.

Assuming we have changed the name to `validator-test` in the `package.json` file, then the code below can work as expected:

```js
var validator = require('validator-test');

validator.isEmail('foo@bar.net'); // true
```

There's no doubt that we can add more functions to the object showing above. And we can also split different functions into different files and combine them into one module using the module system of Node.js.
