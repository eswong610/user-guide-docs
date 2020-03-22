---
layout: default
title: Data Input and Queries
nav_order: 6
---

# How to Insert and Query Data from the Database
{: .no_toc }

Our database right now is empty. To make use of it, we will need to insert data with the schema we've just created. We will also go through querying data to actually retrieve values that we can use in our application. 

## Step 1 - Installing The body-parser Package 
If you are looking to get user data from a form, you will need to npm install body-parser to access the body of the request parameters. 

1. Install the `body-parser` package and insert ```app.use(bodyParser.urlencoded({ extended: true }))``` to fully enable the package and access your data.
 
## Step 2 - Creating A Post Request Endpoint In Server.js And Importing Mongoose.

1. Import Mongoose at the top of the file. We will be using a schema as demonstrated from the last step. 

```
const mongoose = require('mongoose')
```

We will begin to insert new data into this new endpoint.

2. Creating an instance of the model and store it in a variable for it to be used as a constructor. 

![postendpoint](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/post.png?raw=true)

3. Enter your first parameter _ _id_ with the value `new mongoose.Types.ObjectId()`. It should have a constructor function since mongoose will create a unique id internally and assign it to the object. 

4. Input other attributes that your schema requires. 

```
Note: In our example above, we assume there is going to be some input from a user so we will retrieve those values through `req.body` with the help of `body-parser` we installed in step one.
```

5. Call the `save()` function on the data object.

```
Note: Save is provided by mongoose to store the provided object into the database. It takes in a callback function or promises. 
```

Once you make a post request with data, and it saves to the database using the model construct, it should show up as an operation on MongoDB Atlas as a read or write operation in the cluster. This may take a few minutes. 

Here is an example of your operations graph after a post request. R stands for _read_, to represent queries into the database. W stands for _write_ which refers to post requests that alter or insert data into the database. 

![mongoatlas](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/mongoatlasrw.png?raw=true)

Congratulations! You've made your first entry into your database! 

## Step 3 - Setting up methods to query the database

To query anything from the database, you will need to use various function calls on the schema. Since we named our schema 
`sample`, we will use various methods on it to show queries.

1. Use the method `findById` to return a data object that matches the id you input. 

2. Create a callback function as the second parameter. This will take the data object as an argument and act upon it. 


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

---

By now, you will have successfully input data into your Mongodb database, and can retrieve it with a variety of query functions. You should also be able to see all your activity from your account at Mongodb Atlas. 

