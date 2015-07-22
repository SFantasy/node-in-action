# Develop Express application

MVC is common architecture which many applications prefer. MVC stands for Model-View-Controller:

- Model - Implement the main features of the application, handling databases and so on.
- Controller - Dealing with requests, communicating with Models and Views.
- View - The UI layer of the application

So, we would like to choose this application development mode, and here is the basic structure of our folders:

```
- models/
- controllers/
- views/
- app.js
- package.json
```

And in this project, I also create a Service layer which take the responsibility to handling the data -- so the Model layer just needs to define the Data objects.

## Routes

In the project, we could define routing rules in the Controllers, but it is better to declare the rules in separated files.

For some small projects, a single route file is enough. Because there would not be many routing rules in the project comparing to other codes.

However, it is a better practice to use multiple routing files as it will make your project's structure clearer. Here is a example routing rules:

```js
app.get('/', site.index);
app.post('/register', user.register);
```

`site` and `user` are the names of two Controllers, defining different `GET` or `POST` rules.

## MongoDB

MongoDB is convenient for Node.js to manipulating for MongoDB is a document database which use JSON objects to store data. So it is quite simple to handle data with MongoDB using Node.js.

In the project, we would like to use `Mongoose` as our ORM for MongoDB. Below is an example of connecting MongoDB:

```js
var mongoose = require('mongoose');

mongoose.connect('mongodb://127.0.0.1/test', function (err) {
  if (err) {
    console.log('connect to %s error: ', err.message);
    process.exit(1);
  }
});
```

And define a Scheme called User:

```js
var mongoose = require('mongoose');
var Schema = mongoose.Schema;

var UserSchema = new Schema({
  name: { type: String },
  password: { type: String }
});

mongoose.model('User', UserSchema);
```

## Reference

- MongoDB: [https://www.mongodb.org/](https://www.mongodb.org/)
- Mongoose: [http://mongoosejs.com/](http://mongoosejs.com/)
