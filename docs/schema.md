---
layout: default
title: Creating a Schema
nav_order: 5
---

# How To Set Up Your Own Schema

Now that we have our Mongodb cluster set up, we want to create a table or schema for data to be stored in.
To do this we need to use Mongoose to create schema. Mongoose will also be used in other functions with Mongodb Atlas.

## Step 1 - Creating a new folder called models

1. Create a file to store the schema that will be exported onto your server.js. Let's call this file schema.js.

## Step 2 - Calling in the mongoose module
1. Enter in this code into your schema.js file:
```
const mongoose = require('mongoose');
```
2. Set 'key: values' similar to mysql format. 

```
Note: Schema are written as variable using const. 
```

In this example, we will do "const UserSchema". The next part is calling mongoose by inputing this command "mongoose.Schema({})". This will be the body of your schema and everything inside will define it. 

3. Set mongoose.Schema as a variable. Such as this:

```
const UserSchema = mongoose.Schema({});
```

## Step 3 - Setting your id key value.

1. Input `key:values` inside the `{}` bracket to define the schema. 
```
Note: They can be attributes like id, name, password, phone number etc. Specifically, for the `id` attribute,you will put _ _id_. It is convention to start off with _ id with type `mongoose.schemas.Types.ObjectId`. This generates a randomized string/serialized string that uniquely identifies the data object. It is a function of mongoose.
```
2. Enter this for the id:

```
_id: mongoose.Schema.Types.ObjectId,
```
For key:values such as phone number you want the value to be `Number` as illustrated below.

```
Amount : Number,
```

## Step 4 - Export Your Schema Using module.exports

1. Export the schema after you finish adding its values, where it takes 2 parameters ("reference name", [name]). 

```
Note: The first argument is the name of the model you want to use internally. The second argument is the schema you want to use for that model.
```
2. Enter in this code to export:
```
module.exports = mongoose.model('Product', ProductSchema);
```

Your code at the end should look like this: 
![mongoschema](https://github.com/eswong610/user-guide-docs/blob/gh-pages/docs/mongoschema.png?raw=true)


>To learn more on the different key:value you can define in your schema, check the mongoose [link](https://mongoosejs.com/docs/guide.html).

![mongo](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/schemajs.png?raw=true)


## Step 5 - Creating References

Your database will most likely need references for different relationship. In Mongodb, there are two types of references: manual and DBRefs. Manual reference uses the id from one schema then enter it into a new schema to reference the first schema.

![reference](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/reference.png?raw=true)

1. Use _ _id_ of one value and insert into into another schema. Such as

```
original_id = ObjectId()

db.places.insert({
    "_id": original_id,
    "name": "Broadway Center",
    "url": "bc.example.net"
})

db.people.insert({
    "name": "Erin",
    "places_id": original_id,
    "url":  "bc.example.net/Erin"
})
```

The DbRef references uses the value in one schema. Like this example:

```
{
  "_id" : ObjectId("5126bbf64aed4daf9e2ab771"),
  // .. application fields
  "creator" : {
                  "$ref" : "creators",
                  "$id" : ObjectId("5126bc054aed4daf9e2ab772"),
                  "$db" : "users"
               }
}
```

Most cases you will use manual references as the developer community view DBRef negatively due to field ordering that can lead to mistake in the reading and writing of the schema.

--- 

By this point, you should be familiar with how to make a schema using Mongoose and referencing other schemas to use for different data relationships. 

[Next is Data Input](/queries.md){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
