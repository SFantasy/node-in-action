# MVC

MVC是很多应用开发时都会采用的一种「架构模式」，会把一个应用分成Model-View-Controller，每一部分各自负责：

- Model - 应用的功能实现、数据库相关操作等
- Controller - 负责转发请求，对请求进行处理等
- View - 应用的界面部分，与用户的交互等

同样的，我们在开发Express应用的时候也可以采取这样的清晰明了的开发模式，所以我们可以先构建好应用的文件目录，大致如下：

```
- models/
- controllers/
- views/
- app.js
- package.json
```
