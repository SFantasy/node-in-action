# 开发Express应用

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

这次我也是用的MVC的结构，同时稍微扩充了一个Service层把数据定义和操作分割：Model只定义数据，Service定义操作数据的方法。

## MongoDB

MongoDB对于Node而言确实很方便，由于MongoDB使用的是JSON风格的文档存储结构，所以特别是处理数据的时候就像是在处理JavaScript的对象一样。

> 有不知道MongoDB为何物的同学可以先点击本节末尾的链接了解一番。

在Express中使用Mongoose来操作MongoDB也特别的方便，例如以下是使用Mongoose连接数据库的一个操作：

```js
var mongoose = require('mongoose');

mongoose.connect('mongodb://127.0.0.1/test', function (err) {
  if (err) {
    console.log('connect to %s error: ', err.message);
    process.exit(1);
  }
});
```

再比如定义Schema，以简单的User为例:

```js
var mongoose = require('mongoose');
var Schema = mongoose.Schema;

var UserSchema = new Schema({
  name: { type: String },
  password: { type: String }
});

mongoose.model('User', UserSchema);
```

## 参考

- MongoDB: [https://www.mongodb.org/](https://www.mongodb.org/)
- Mongoose: [http://mongoosejs.com/](http://mongoosejs.com/)
