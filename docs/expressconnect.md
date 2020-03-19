---
layout: default
title: NodeJS implementation
nav_order: 4
---
## step 1 - Connecting your mongodb to express

Set up a new project folder and create your files according to this structure. 

![fileorder](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/fileorder.png?raw=true)

Start up your node package manager for your dependencies with `npm init`. 
Install mongoose and expressJS with `npm install express mongoose` to access both these packages.

In the server.js file, require the express module and set up a simple server like so. 

![server](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/server.png?raw=true)

In the set up, you should have gotten the connection string from the last step. It should look a little something like this.
![connectstr](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/connectstring.png?raw=true)

Recall back to the database administrator you set up. 
Customize your string so that your user name replaces <sample> and your user password replaces <password>.

In the connection.js file under the Database folder, require the mongoose module, and set the connection string from as a variable. 

This allows your application to use mongoose as a more straightforward solution to creating schemas for data used for Mongodb.

For ease, copy and paste the code snippet 

```javascript
const connectDB = ()=>{
     mongoose.connect(URI, {
        useNewUrlParser: true,
        useUnifiedTopology: true,
    });
  }
 ```
 
![mongooseconnect](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/connectdb.png?raw=true)

It is important to keep our project module. Export the connection from the file. 
Import it into the server.js file and call it as a function
```
const connectDB = require('./DB/connection';

connectDB();
```
To check if the database is connected, insert a `console.log('database connected')` statement at the end of your connectDB function in your connection.js file. You will be able to confirm that it is indeed connected when it prints out the string.
