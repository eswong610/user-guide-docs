---
layout: default
title: Updating and Deleting Values
nav_order: 7
---

# How To Update And Delete Values In The Database
{: .no_toc }

Following from our previous task, we will now learn to update values in the database using the RESTapi method _patch_. Patching will only updates certain values of the identified object and will keep the object as a whole.

Assuming you will retrieve the data object from a query, we will use `req.params` to retrieve the values you intend to change.  
`req.params` is used here instead of `req.body` because params comes from the parameters of the route passed.  

## Step 1 - Creating an endpoint on your server that should update a pre-existing value. 

![reqparams](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/reqparams2.png?raw=true)

The image above is an example of what your code should look like. Since the endpoint is `/:sampleid`, then the requested id parameter is retrievable through req.params.sampleid. You will also need values to replace or update the object you requested.
This will come through to the back-end from req.body. 

## Step 2 - Setting up the endpoint.
1. Create an empty object and set it to a variable. This will be to store the values you want to update. 
    
```Note: Assume again we will use information taken from a user``` 

2. Write a for-loop that will pair a property and value from `req.body` into a key-value pair 
3. Store it into the empty object. 

## Step 3 - Filling out the update method 

The update method will take two parameters. 

1. Assign the first parameter to locate the object that matches the conditions - your identifier.

2. Assign the second parameter is using `$set` (from Mongoose) to pass another key value object - your replacement.

You should have something like the image below by the end.

![patchmethod](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/patchsample.png?raw=true)

3. Call `.exec()` on the update method from above and finish the promises with a `.then` and `.catch` statement to catch any errors. 

## Step 4 - Repeat With Deleting Method
Deleting values from the database is very similar to patching. With the delete CRUD method, set up an endpoint that should delete a pre-existing value. 

1. Retrieve the identifier value from req.params and store it in a variable.

2. Call _remove_ on the schema with the identifier as a parameter.
This code will basically says to delete any data object that matches the following criteria.
 
3. Call `exec()`to execute a promise where after you will chain a `.then` and `.catch` expression to fulfill the promise conditions. 

![sampledel](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/deletesample.png?raw=true)

The code above is an example of what you should have by the end. It is more simple than the patch method since you will only need to have an identifier.

## Conclusion
By completing all these steps, you have familiarized yourself with the basics of MongoDB. You can now connect the database with your application, set up a schema, and add or change data as you wish within it. With these skills, you can now create more intricate and advanced web applications. 


