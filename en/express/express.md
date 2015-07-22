# Use Express

[Express](http://expressjs.com/) is the most popular Web development framework created by [TJ](https://github.com/tj), and the latest version of it is 4.x.

## Hello World in Express

Here is a simple snippet code using Express, return a string `Hello World` via method `res.send()`:

```js
var express = require('express');
var app = express();

app.get('/', function (req, res) {
    res.send('Hello World');
});

app.listen(3000, function () {
    console.log('Express server started.');
});
```

Run `app.js`:

```sh
node app.js
```

## Express generator

Express also provide a tool to generate project in seconds like other popular web frameworks: [Express Generator](https://github.com/expressjs/generator)

- Install

```sh
npm install -g express-generator
```

- Generate project

```sh
express test
```

Enter the folder and install all the dependencies:

```sh
cd test && npm install
```

Now you are able to run this project with `npm start`. Awesome!
