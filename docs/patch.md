---
layout: default
title: Patch
nav_order: 6
---

## Step 9 - Updating the database
{: .no_toc }


Following from our previous task, we will now learn to update values in the database. 

Using the patch method, set up an endpoint on your server that should update a pre-existing value. 
Patching only updates certain values of the identified object and keeps the object as a whole. 

req.params is used here because params comes from the parameters of the route passed. So for the example since the endpoint is `/:username` then the username parameter is retrievable through req.params.username.

![reqparams](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/reqparams.png?raw=true)

in the update method, it will take two parameters. The first one is to locate the object that matches the conditions, and the second parameter is using $set (from Mongoose) to pass another key value object

Call `.exec()` on the update and finish the promises with a `.then` and `.catch` statement to catch any errors. 

## Step 10 - Deleting from the database
Deleting values from the database is very similar to patching. With the delete CRUD method, set up an endpoint that should delete a pre-existing value. 

This code below basically says to delete any data object that matches the following criteria 
![sampledel](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/sampledel.png?raw-true)

With this, call the delete function on the schema to remove 
This example uses only the delete function, but there are other options to delete either one or multiple other data objects with `deleteOne()` or `deleteMany()`. 

Like patch above, call `exec()`to execute a promise where after you will chain a `.then` and `.catch` expression to fulfill the promise conditions. 
