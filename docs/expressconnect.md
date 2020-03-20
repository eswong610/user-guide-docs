---
layout: default
title: NodeJS implementation
nav_order: 4
---
## Connecting your Mongodb to Express Server

Step 1 - Set up a new project folder and create your files according to this structure in the following image. 

![fileorder](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/fileorder.png?raw=true)

Step 2 - Start up your node package manager for your dependencies with `npm init`. 

Step 3 - Install mongoose and expressJS with `npm install express mongoose` to access both these packages.

Step 4 - Require the express module and set up a simple server in the server.js file, like so. 

![server](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/server.png?raw=true)

In the set up, you should have gotten the connection string from the last step. It should look a little something like this.
![connectstr](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/connectstring.png?raw=true)

Recall back to the database administrator you set up. 
Step 5 - Customize your string so that your user name replaces <sample> and your user password replaces <password>.

Require the mongoose module, and set the connection string from as a variable in the connection.js file under the Database folder. 

This allows your application to use mongoose as a more straightforward solution to creating schemas for data used for Mongodb.

Step 6 - Copy and paste the code snippet, 

```javascript
const connectDB = ()=>{
     mongoose.connect(URI, {
        useNewUrlParser: true,
        useUnifiedTopology: true,
    });
  }
 ```
 
![mongooseconnect](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/connectdb.png?raw=true)

It is important to keep our project modularized so we will take the connection and use it in the server file. 

Step 7 - Export the connection from the file. 

Step 8 - Import it into the server.js file and call it as a function like the following code snippet. 
```
const connectDB = require('./DB/connection';

connectDB();
```
Step 9 - To check if the database is connected, insert a `console.log('database connected')` statement at the end of your connectDB function in your connection.js file. Y

ou will be able to confirm that it is indeed connected when it prints out the string.
