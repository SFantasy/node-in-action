# 管理NPM模块

所有发布在NPM上的模块，都可以在自己的NPM主页上看到。

但是如果想要更为直观的管理，可以通过一个名为[badgeboard](https://github.com/repo-utils/badgeboard)的工具来浏览，以下是我的NPM badgeboard:

![badgeboard](http://7u2gnn.com1.z0.glb.clouddn.com/badgeboard.png)

对于NPM的模块，已经有很多成熟的服务，方便开发者了解自己的模块状态。

正如上图中所示，常用的服务有：

- 持续集成：[travis](https://travis-ci.org)
- 测试覆盖：[coveralls](https://coveralls.io/)
- 查看模块依赖：[david-dm](https://david-dm.org/)

这些工具都可以非常好的帮助你管理自己的NPM模块、了解模块的状态。

例如，了解模块的依赖是否为最新，若依赖有所落后，则最好及时跟进最新版。

## 跟踪Bug

即使拥有travis和coveralls这样的工具，还是难以避免测试用例没有覆盖等没有预料到的情况。

而对于NPM而言，本身只是一个模块的平台，并不具备BUG跟踪、反馈的功能。所以还是需要配合Github的issues来收集用户反馈，及时修复Bug。
