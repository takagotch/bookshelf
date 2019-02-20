### bookshelf
---
https://github.com/bookshelf/bookshelf

```
npm install knex --save
npm install bookshlf --save

npm install pg
npm install mysql
npm install mariasql
npm install sqlite3
```

```js
var knex = require('knex')({
  client: 'mysql',
  connection: {
    host : '127.0.0.1',
    user : 'your_database_user',
    password : 'your_database_password',
    database : 'myapp_test',
    charset : 'utf8'
  }
});

var bookshelf = require('bookshelf')(knex);

var User = bookshelf.Model.extend({
  tableName: 'users'
});


var knex = require('knex')(dbConfig);
module.exports = require('bookshelf')(knex);

var bookshelf = require('./bookshelf');

var Post = bookshelf.Model.extend({
});


var knex = require('knex')({
  client: 'mysql',
  connection: process.env.MYSQL_DATABASE_CONNECTION
});
var bookshelf = require('bookshelf')(knex);

var User = bookshelf.Model.extend({
  tableName: 'users',
  post: function() {
    return this.hasMany(Posts);
  }
});

var Posts = bookshelf.Model.extend({
  table: 'messages',
  tags: function() {
    return this.belongsToMany(Tag);
  }
});

var Tag = bookshelf.Model.extend({
  tableName: 'tags'
})

User.where('id', 1).fetch({withRelated: ['posts.tags']}).then(function(user) {
  console.log(user.related('posts').toJSON());
}).catch(function(err) {
  consoleerror(err);
});

process.stderr.on('data', function(data) {
  console.log(data);
});
```

```js
user.fetch({withRelated: ['accounts', {
  'accounts.settings': function(qb) { qb.where()}
}, 'other_data']})
.then()
```


