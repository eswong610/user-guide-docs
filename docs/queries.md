---
layout: default
title: Queries
nav_order: 7
---

### Queries and Data Input
{: .no_toc }
## Step 11 - Making the schema

To start storing data in the database, we will be using mongoose to create a model. Mongoose works with models and schemas so you will first need to define _how_ the data is stored before you actually store anything. Once you decide how the data should look like, you will define it with a model (e.g. a javascript object). The model will have several functions that you can use to either save, update, query the data, and so on. 


Create a new folder called _models_ and a schema.js file in it. This is where you will store the schemas of your database.
Import mongoose in the new file and create a new constant schema using mongoose schema method which passes a javascript object defining what the data should look like. 

It is convention to start off with _ _id_ with type _mongoose.schemas.Types.ObjectId_. This generates a randomized string/serialized string that uniquely identifies the data object. It is a function of mongoose. 

The rest of the data object can be given attributes you would like to input as data. For example 
```
name: String,
price: Number,
```
You would then need to export the model at the end of the file using `modules.exports = mongoose.model('name', variable)`.
The first argument is the name of the model you want to use internally. 
The second argument is the schema you want to use for that model. 

![mongoschema](https://github.com/eswong610/user-guide-docs/blob/gh-pages/docs/mongoschema.png?raw=true)

## Step 12 - Inserting into a schema

Mongoose is commonly used alongside Mongodb, 

In the file where your endpoints are, import mongoose. Create a post request endpoint so we can begin to insert new data. Start by creating an instance of the model and store it in a variable for it to be used as a constructor. 
##image 

Your first parameter _ _id_ should have the value `new mongoose.Types.ObjectId()`. It should have a constructor function since mongoose will create a unique id internally and assign it to the object. 

Call save on the data object you just made. Save is provided by mongoose to store the provided object into the database. 
It takes in a callback function or promises. 

If you are looking to get user data from a form, you will need to npm install body-parser as well to access the body of the request parameters. Once you have done so, insert `app.use(bodyParser.urlencoded({ extended: true }))` to fully enable the body parser and access your data. Try it out with a Postman post request!

Once you make a post request with data, and it saves to the database using the model construct, it should show up as an operation on MongoDB Atlas as a read or write operation in the cluster. This may take a few minutes. 

Here is an example of your operations graph after a post request. R stands for 'read', to represent queries into the database. W stands for 'write' which refers to post requests that alter or insert data into the database. 

![mongoatlas](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/mongoatlasrw.png?raw=true)

Congratulations! You've made your first entry into your database! 

## Step 13 - Querying the database

To query anything from the database, you will need to use various function calls on the schema. Since we have named our schema 
'sample', we will use the method `findById` to return a data object that matches the id you input. 

```
sample.findById(myId, function (err, obj) {
  if (!err) {
    obj.name.remove();
    obj.save(function (err) {
      console.log(err)
    });
  }
});
```
The code above will find the data object by the _id_ and remove the name attribute from the object. It will save the object and as it is without the name.  

There are a number of other querying functions such as find(), _findOne(), _findOneAndReplace().

