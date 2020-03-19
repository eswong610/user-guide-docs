---
layout: default
title: Schema
nav_order: 5
---

## Schema

Now that we have our mongodb cluster connected, we want to create a table or schema for data to be stored in.
To do this we need to use mongoose to create schema. Mongoose will also be used in other functions with Mongodb Atlas.

## step 1

In a folder, you will want to create a file to store the schema that will be exported onto your app.js.
Let's just called this file schema.js
From there, you want to call in the mongoose module like this
```
const mongoose = require('mongoose');
```
To make a schema, you set 'key: values' similar to mysql format. Schema are written as variable using const. 
In this example, we will do "const UserSchema". The next part is calling mongoose by inputing this command "mongoose.Schema({})". This will be the body of your schema and everything inside will define it.

```
const UserSchema = mongoose.Schema
```

For id => you will put _id 

```
_id: mongoose.Schema.Types.ObjectId,
```
for integer values, the basic is to use 'Number'

```
Cost: Number,
```

After you finish adding in the schema values. You will export them using module.export and it takes 2 parameters ("reference name", [name of the schema you called it]).

```
module.exports = mongoose.model('Product', ProductSchema);
```

>To learn more on the different key:value you can define in your schema, check the mongoose [link](https://mongoosejs.com/docs/guide.html).

![mongo](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/schemajs.png?raw=true)




