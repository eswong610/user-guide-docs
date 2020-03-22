---
layout: default
title: Data Input and Queries
nav_order: 6
---

# How to Insert and Query Data from the Database
{: .no_toc }

## Step 1 - Installing The body-parser Package 
If you are looking to get user data from a form, you will need to npm install body-parser to access the body of the request parameters. 

Install the `body-parser` package and insert ```app.use(bodyParser.urlencoded({ extended: true }))``` to fully enable the package and access your data.
 
## Step 2 - Creating A Post Request Endpoint In Server.js And Importing Mongoose.

Import Mongoose at the top of the file. We will be using a schema as demonstrated from the last step. 

```
const mongoose = require('mongoose')
```

We will begin to insert new data into this new endpoint. Start by creating an instance of the model and store it in a variable for it to be used as a constructor. 

![postendpoint](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/post.png?raw=true)

Your first parameter _ _id_ should have the value `new mongoose.Types.ObjectId()`. It should have a constructor function since mongoose will create a unique id internally and assign it to the object. 
Input other attributes that your schema requires. In our example above, we assume there is going to be some input from a user so we will retrieve those values through `req.body` with the help of `body-parser` we installed in step one.

## Step 3 - Calling the save() on the data object
Save is provided by mongoose to store the provided object into the database. It takes in a callback function or promises. 

Once you make a post request with data, and it saves to the database using the model construct, it should show up as an operation on MongoDB Atlas as a read or write operation in the cluster. This may take a few minutes. 

Here is an example of your operations graph after a post request. R stands for _read_, to represent queries into the database. W stands for _write_ which refers to post requests that alter or insert data into the database. 

![mongoatlas](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/mongoatlasrw.png?raw=true)

Congratulations! You've made your first entry into your database! 

## Step 4 - Setting up methods to query the database

To query anything from the database, you will need to use various function calls on the schema. Since we named our schema 
`sample`, we will use various methods on it to show queries.

Use the method `findById` to return a data object that matches the id you input. 
Have a callback function as the second parameter. This will take the data object as an argument and act upon it. 

## Step 5 - Creating a callback function
Create a callback function to use the data object you will retrieve.

The following code snippet is an example of how the code should look like when you make a query. 

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

## Conclusion

By now, you will have successfully input data into your Mongodb database, and can retrieve it with a variety of query functions. You should also be able to see all your activity from your account at Mongodb Atlas. 

