
Set up a new project folder and create your files according to this structure. 

and start up your node package dependencies with `npm init`
Install mongoose and expressJS with `npm install express mongoose`




In the server.js file, require the express module and set up a simple server like so. 

///javascript
const express = require('express');
const app = express();

const PORT = process.env.PORT || 8080;'
app.listen(PORT, ()=>{console.log('Your server is started on {PORT}')

///
In the set up, you should have gotten the connection string from the last step. It should look a little something like this.
In the connection.js file under the Database folder, require the mongoose module, and set the connection string from as a variable. 

`const connectDB = async()=>{
  await mongoose.connect(URI);
}
`
Export the connection. 

Import it into the server.js file and call it as a function
`const connectDB = require('./DB/connection';
connectDB();

