---
layout: default
title: NodeJS implementation
nav_order: 4
---
### Connecting your Mongodb to Express Server

## Step 1 - Setting your project folder
Select a directory and make a new folder. From that folder, you will create your files according to this structure in the following image. 

![fileorder](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/fileorder.png?raw=true)

## Step 2 - Preparing your project with node module dependencies
On the terminal, start up your node package manager for your dependencies with `npm init` in your project directory. Press enter until it prompts a yes/no question. You will enter in yes or y.

## Step 3 - Installing the mongoose and express.js module
While on the terminal, you will install mongoose and expressJS by entering this command:
```
npm install express mongoose
```


## Step 4 - Creating the nodejs server
Open up your code editor and have your workspace in the project folder. You will create a js file called server.js. 
Inside the server.js, you will enter the code shown below to have a basic server.

![server](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/server.png?raw=true)

> Note that the number for port can be 2-5 digit integer. 8080 is not mandatory to use. When you run the server, it will give a blank page, but on the terminal you should see a message print out to show the server is working correctly.

## Step 5 - Getting your Connection string
In the previous step for cluster, you should have gotten the connection string from the cluster setting. It should look a little something like this.
![connectstr](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/connectstring.png?raw=true)

You will copy this string with either command + c or right click it.

 
## Step 6 - Customizing your connection string 
Recall back to the database administrator you set up. Customize your string so that your user name replaces <sample> and your user password replaces <password>.

## Step 7 - Creating a connection.js file
On your code editor, create a new folder called Database. Enter into that directory and then create a file called connection.js

## Step 8 - Setting up your connecton.js
Enter this code
```
const mongoose = require('mongoose);
```
Next, you will set the connection string form as a variable in the connection.js file. It should be similar to this code snippet:
```
const URI = "your-connection-string";
```

This allows your application to use mongoose as a more straightforward solution to creating schemas for data used for Mongodb.

## Step 9 - Linking your file to mongodb cluster
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

It is important to keep our project modularized so we will take the connection and use it in the server file. 

## Step 10 - Exporting the link connection
Export the connection link from the file by entering this code below:

```
module.exports = connectDB
```


## Step 11 - Importing the link connection
Import it into the server.js file and call it as a function like the following code snippet. 
```
const connectDB = require('./DB/connection';

connectDB();
```

## Step 9 - Testing the connection
To check if the database is connected, insert a `console.log('database connected')` statement at the end of your connectDB function in your connection.js file. Return back to your terminal and enter in "node server.js". You will be able to confirm that it is indeed connected when it prints out the string.

### Conclusion

If you have completed all the steps above, you should have a project folder with a server.js and a connection.js. You should also have a working server that is connected to your mongodb database.
