---
layout: default
title: NodeJS implementation
nav_order: 4
---
### Connecting your Mongodb to Express Server

We will now start using the tools we have made to create a connection between your database and a node web application. 

## Step 1 - Setting your project folder
1. Select a directory and make a new folder.  
2. Create your files according to this structure in the following image insdie the new folder. 

![fileorder](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/fileorder.png?raw=true)

## Step 2 - Preparing your project with node module dependencies
1. Start up your node package manager for your dependencies with `npm init -y ` in your project directory in the terminal. 

2. Install `mongoose` and `expressJS` by entering this command:

```
npm install express mongoose
```


## Step 3 - Creating the nodejs server
1. Open up your code editor and have your workspace in the project folder. 
2. Create a javascript file called server.js. 
3. Enter the code shown below to have a basic server:

![server](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/server.png?raw=true)

```
Note that the number for port can be 2-5 digit integer. 8080 is not mandatory to use. When you run the server, it will give a blank page, but on the terminal you should see a message print out to show the server is working correctly.
```

## Step 4 - Getting your Connection string
In the previous step for cluster, you should have gotten the connection string from the cluster setting. It should look a little something like this: 
![connectstr](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/connectstring.png?raw=true)

1. Copy this string.

Recall back to the database administrator you set up. 

2. Customize your string so that your user name replaces `<sample>` and your user password replaces `<password>`.

## Step 5 - Creating a connection.js file
1. Create a new folder called Database. Enter into that directory and create a file called connection.js

2. Enter this code
```
const mongoose = require('mongoose);
```
3. Next, you will set the connection string form as a variable in the connection.js file. 

It should be similar to this code snippet:
```
const URI = "your-connection-string";
```

This allows your application to use mongoose as a more straightforward solution to creating schemas for data used for Mongodb.

## Step 6 - Linking your file to mongodb cluster
Copy and paste the code snippet, 

```javascript
const connectDB = ()=>{
     mongoose.connect(URI, {
        useNewUrlParser: true,
        useUnifiedTopology: true,
    });
  }
 ```
 
![mongooseconnect](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/connectdb.png?raw=true)

```
Note: It is important to keep our project modularized so we will take the connection and use it in the server file. 
```

## Step 7 - Modularizing the link connection

1. Export the connection link from the connection.js file by entering this code below:

```
module.exports = connectDB
```
2. Import it into the server.js file and call it as a function like the following code snippet. 
```
const connectDB = require('./DB/connection';

connectDB();
```

## Step 8 - Testing the connection
To check if the database is connected: 
1. Insert a `console.log('database connected')` statement at the end of your connectDB function in your connection.js file. 
2. Return back to your terminal and enter in "node server.js". 

You will be able to confirm that it is indeed connected when it prints out the string.

---

If you have completed all the steps above, you should have a project folder with a server.js and a connection.js. You should also have a working server that is connected to your mongodb database.
