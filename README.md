# Week 10

## Mongoose

### Question #1

Describe the differences between a SQL and NoSQL DB, and when you might use each.

```text
SQL is a relational database and NoSQL is a non-relational database.

NoSQL allows the use of different datatypes within a given document, so taking on a project where the types of data are unknown may be ideal for NoSQL.

```

### Question #2

What's wrong with this mongoose code and how might we fix it?
(Hint: Assuming there is a document with a name of "Bob", why is results not an author model on the second line?)

```js
var results = AuthorModel.find({name: "Bob"});
console.log(results);
```

```js
var results = Author.findOne({name: "Bob"});
console.log(results);

### Question #3

Convert the following ActiveRecord sequence to Mongoose:

```rb
@andy = Instructor.find_by(name: "Andy")
@andy.wishlist_items.create(description: "Resin Laying Deer Figurine, Gold")
```

```js
var query = Instructor.findOneAndUpdate({name: "Andy"},
{
  $set: {
    "wishlist_items" : {"description":[Resin Laying Deer Figurine, Gold]}
  }
},{
  upsert:true
});

```

### Question #4

Convert the following create method in Mongoose to ActiveRecord.

```js
  var authors = {
  create: function(req, res){
  var author = new AuthorModel({name: req.body.name})
  author.save(function(err){
    if (!err){
      res.redirect("authors")
    }
  })
  }  
}
```

```rb
def create
  @author = Author.new(params[:id])
  @author.create

end

```
## Express

### Question #5

How does module.exports help us with separation of concerns?

```text

```

### Question #6

Write one Express route for each of the four HTTP methods.

Then, make each route respond with a one-word string containing the RESTful action that would most likely be associated with this route.

```js
var express = require("express");
var app = express();

// Your code starts here...

```

```js
// Your answer...
```
### Question #7

Describe the differences between Express and Rails as backend frameworks.

```text

```

### Question #8

What is the importance of using body-parser in our express application for post requests?

```js

```
