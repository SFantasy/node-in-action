# Write test cases

There're lots of excellent test frameworks written in Node.js. For example, [mocha](https://www.npmjs.com/package/mocha), [jasmine](https://github.com/jasmine/jasmine) and so on.

We would like to use mocha to write our test cases.

> Anyone who wants to know more about Mocha could visit its homepage for more information: [mocha.org](http://mochajs.org/)

- Install mocha

```sh
npm install -g mocha
```

- Use `assert`

```js
var assert = require('assert');
```

"assert" includes many Node.js modules about assertion, e.g. [should.js](https://github.com/visionmedia/should.js), [expect](https://github.com/LearnBoost/expect.js). Most of this modules are practices on Behavior Driven Development, a.k.a, BDD.

- Example of assert

```js
describe('Array', function() {
    describe('#indexOf()', function() {
        it('should return -1 when the value is not present', function() {
            [1,2,3].indexOf(5).should.equal(-1);
            [1,2,3].indexOf(0).should.equal(-1);
        });
    });
});
```

It seems that we have just described a thing using English. Yes, what we are going to do is to describe what the functions in "node-validators" would works like.

Following the examples above, here comes the prototype of our use cases:

```js
var assert = require('assert');
var validator = require('validator-test');

describe('Validator', function () {
    describe('#isEmail', function () {
        it('should return true when the string is an email address', function () {
            if (validator.isEmail('foo@bar.net') !== true) {
                throw new Erorr('Validator not right');
            }
        });
    });
});
```

Type `mocha` in your terminal, this would run the `test.js` file in `test` folder automatically:

```sh
mocha
```

The we will get the result:

```sh
Validator
#isEmail
✓ should return true when the string is an email address


1 passing (6ms)
```

What's next? Just write test cases for every functions in "node-validator" in order to cover all.
