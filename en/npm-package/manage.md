# Manage NPM package

You can view all the NPM modules that you have published to NPM on your homepage.

But if you are eager to view them in a more direct way, it's pretty cool to use a tool named [badgeboard](https://github.com/repo-utils/badgeboard).

![badgeboard](http://7u2gnn.com1.z0.glb.clouddn.com/badgeboard.png)

There're already many excellent services for managing and get in touch of your NPM modules.

As the picture shows above, here is a list of common services:

- Continuous integration: [travis](https://travis-ci.org)
- Test cases coverage: [coveralls](https://coveralls.io/)
- Module dependencies: [david-dm](https://david-dm.org/)

These tools can help you manage your modules easily and know the situation of the modules.

For example, using "david-dm" could know whether the dependencies of a module is newest. And if its dependencies are already behind, you'd better upgrade the module.

## Bug tracking

Even with tools such as travis and coveralls, there would also be many situations that test cases can't cover or something out of expectation.

For NPM, it's just a platform for hosting modules and provide tools for the modules, and NPM does not have features like BUG tracking and feedback. For this reason, we could use Github issues to collect the feedback of different users.
