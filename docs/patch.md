---
layout: default
title: Updating and Deleting Values
nav_order: 7
---

# How To Update And Delete Values In The Database
{: .no_toc }

Following from our previous task, we will now learn to update values in the database using the RESTapi method _patch_. Patching will only updates certain values of the identified object and will keep the object as a whole.

Assuming you will retrieve the data object from a query, we will use `req.params` to retrieve the values you intend to change.  
`req.params` is used here because params comes from the parameters of the route passed.  

## Step 1 - Creating an endpoint on your server that should update a pre-existing value. 

![reqparams](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/reqparams2.png?raw=true)

The image above is an example of what your code should look like. Since the endpoint is `/:sampleid`, then the requested id parameter is retrievable through req.params.sampleid. You will also need values to replace or update the object you requested.
This will come through to the back-end from req.body. 

## Step 2 - Setting up the endpoint.
Create an empty object and set it to a variable. This will be to store the values you want to update. 
Then, write a for-loop that will pair a property and value from `req.body` into a key-value pair and store it into the empty object. 

## Step 3 - Filling out the update method 

The update method will take two parameters. The first one is to locate the object that matches the conditions, and the second parameter is using `$set` (from Mongoose) to pass another key value object.

Assign the two parameters to your identifier and your replacement. 

You should have something like the image below by the end.

![patchmethod](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/patchsample.png?raw=true)

## Step 4 - Execute the update

You will call `.exec()` on the update method from above and finish the promises with a `.then` and `.catch` statement to catch any errors. 

## Deleting from the database
Deleting values from the database is very similar to patching. With the delete CRUD method, set up an endpoint that should delete a pre-existing value. 

## Step 1 - Storing the identifier value
Retrieve the identifier value from req.params and store it in a variable.

## Step 2 - Removing the endpoint
To remove the endpoint, call _remove_ on the schema with the identifier as a parameter.

This code will basically says to delete any data object that matches the following criteria.

## Step 3 - Calling `exec()`to execute promise conditions. 
Call `exec()`to execute a promise where after you will chain a `.then` and `.catch` expression to fulfill the promise conditions. 
![sampledel](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/deletesample.png?raw=true)

The code above is an example of what you should have by the end. It is more simple than the patch method since you will only need to have an identifier.
