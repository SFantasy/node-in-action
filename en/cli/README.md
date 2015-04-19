# Develop command line tool

In the second chapter, we're going to learn to develop command line tool with Node.js

In Linux (or Unix) systems, command line tools are especially helpful for daily work and development. And Node.js could provide us a rapid developing experience to build a command line tool.

Following is a simple Node.js script:

```sh
#!/usr/bin/env node

console.log('Hello CLI');
```

## Command line parameters

We will need to get parameters for the command line tool. [TJ](https://github.com/tj) has open sourced a practical module named [Commander.js](https://github.com/tj/commander.js) which is used to get different kinds of command line parameters. It is really convenient for our development.

For example, we could use commander.js like this:

```sh
#!/usr/bin/env node

var program = require('commander');

program.version('0.0.1').parse(process.argv);
```

It's easy and efficient to use this module, and now we could get the tool's version just like many other existed command line tool:

```sh
node test --version
```

Obviously, this module is required by the tools which needs passing a lot parameters.

## node-translator

node-translator is a command line tool which translate words using Youdao Dic's API in terminals. And in this chapter we are going to complete it:

![node-transaltor](http://7u2gnn.com1.z0.glb.clouddn.com/node-translator.png)

All the sections in this chapter would explain things using its codes.
