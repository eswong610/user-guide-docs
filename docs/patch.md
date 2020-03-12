---
layout: default
title: Patch
nav_order: 6
---

## Step 1 
{: .no_toc }

### Updating the database
Following from our previous task, we will now learn to update values in the database. 

Using the patch method, set up an endpoint on your server that should update a pre-existing value. 
Patching only updates certain values of the identified object and keeps the object as a whole. 

req.params is used here because params comes from the parameters of the route passed. So for the example since the endpoint is `/:username` then the username parameter is retrievable through req.params.username.

![reqparams](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/reqparams.png?raw=true)

in the update method, it will take two parameters. The first one is to locate the object that matches the conditions, and the second parameter is using $set (from Mongoose) to pass another key value object
