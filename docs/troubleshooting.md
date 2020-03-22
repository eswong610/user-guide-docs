---
layout: default
title: Troubleshooting
nav_order: 8
---

## Troubleshooting
1. 

2. 

3. If you are having trouble inputting data and writing values to your database, check the authentication for your user's Database User's Priveledges. Make sure it is checked under the **Atlas Admin**, or **Read and Write to Any Database**.  

4. If you are unable to connect to your MongoDB cluster, verify your URI string has the right credentials of a Database administrator. Your user's username and password should replace the default characters given to you. 

5. If your MongoDB connection is closing automatically right after a connection is made, make sure to check that your IP address is whitelisted, or that your whitelist IP adresses is set to 0.00.00.0 to ensure anyone can access the cluster. This is caused by MongoDB Atlas blocking your access due to permission rights from your account. 




<!--![troubleshoot1](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/troubleshoot1.png?raw=true)-->

