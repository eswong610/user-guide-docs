---
layout: default
title: NodeJS implementation
nav_order: 4
---
## step 1 - Connecting your mongodb to express

Set up a new project folder and create your files according to this structure. 

![fileorder](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/fileorder.png?raw=true)

Start up your node package manager for your dependencies with `npm init`. 

Install mongoose and expressJS with `npm install express mongoose`.

In the server.js file, require the express module and set up a simple server like so. 

![server](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/server.png?raw=true)

In the set up, you should have gotten the connection string from the last step. It should look a little something like this.
![connectstr](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/connectstring.png?raw=true)

In the string, instead of <password>, replace it with the password you have customized.

In the connection.js file under the Database folder, require the mongoose module, and set the connection string from as a variable. 
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

Export the connection. 

Import it into the server.js file and call it as a function
`const connectDB = require('./DB/connection';

connectDB();
`
To check if the database is connected, put a console.log statement at the end of your connectDB function in your connection.js file so that when it runs, you can check if anything prints in the console. 
