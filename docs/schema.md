---
layout: default
title: Schema
nav_order: 5
---

### Setting your own Schema

Now that we have our Mongodb cluster connected, we want to create a table or schema for data to be stored in.
To do this we need to use Mongoose to create schema. Mongoose will also be used in other functions with Mongodb Atlas.

Step 1 - Create a new folder called models; you will create a file to store the schema that will be exported onto your app.js.
Let's call this file schema.js.

Step 2 - Call in the mongoose module into schema.js like this:
```
const mongoose = require('mongoose');
```
To make a schema, you set 'key: values' similar to mysql format. Schema are written as variable using const. 
In this example, we will do "const UserSchema". The next part is calling mongoose by inputing this command "mongoose.Schema({})". This will be the body of your schema and everything inside will define it. 

Step 3 - Set mongoose.Schema as a variable.

```
const UserSchema = mongoose.Schema
```

For id => you will put _ _id_.
It is convention to start off with _ id with type mongoose.schemas.Types.ObjectId. This generates a randomized string/serialized string that uniquely identifies the data object. It is a function of mongoose.

Step 4 - Set your id key value.
```
_id: mongoose.Schema.Types.ObjectId,
```
for integer values, the basic is to use 'Number'

```
Amount : Number,
```

After you finish adding in the schema values. You will export them where it takes 2 parameters ("reference name", [name]). The first argument is the name of the model you want to use internally. The second argument is the schema you want to use for that model.

Step 5 - Export your schema using module.exports

```
module.exports = mongoose.model('Product', ProductSchema);
```

Your code at the end should look like this: 
![mongoschema](https://github.com/eswong610/user-guide-docs/blob/gh-pages/docs/mongoschema.png?raw=true)


>To learn more on the different key:value you can define in your schema, check the mongoose [link](https://mongoosejs.com/docs/guide.html).

![mongo](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/schemajs.png?raw=true)


## Creating references

Your database will most likely need references for different relationship. In Mongodb, there are two types of references: manual and DBRefs. Manual reference uses the id from one schema then enter it into a new schema to reference the first schema.

![reference](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/reference.png?raw=true)


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

