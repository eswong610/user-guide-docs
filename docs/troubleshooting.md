---
layout: default
title: Troubleshooting
nav_order: 8
---

## Troubleshooting
### Unable to access Mongoose in one of your files?

A likely cause is that you have not imported it into the file. Ensure you have `const mongoose = require('mongoose')` for access to the library. 

### Can't login to your MongoDB account to view your activity?

Click the **Forgot Password** button to reset your password. For future ease, sign in using one of their social media options, such as Google. 

### Having trouble inputting data and writing values to your database?

Check the authentication for your user's Database User's Priveledges. Make sure it is checked under the **Atlas Admin**, or **Read and Write to Any Database**.  

### Unable to connect to your MongoDB cluster?

Verify your URI string has the right credentials of a Database administrator. Your user's username and password should replace the default characters given to you. 

### Is your MongoDB connection is closing automatically right after a connection is made?

Make sure to check that your IP address is whitelisted, or that your whitelist IP adresses is set to 0.00.00.0 to ensure anyone can access the cluster. This is caused by MongoDB Atlas blocking your access due to permission rights from your account. 




<!--![troubleshoot1](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/troubleshoot1.png?raw=true)-->

