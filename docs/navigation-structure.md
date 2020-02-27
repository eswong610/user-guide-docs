---
layout: default
title: Set-up 
nav_order: 5
---

## Step 1 
{: .no_toc }

### Set up a Mongodb account and install it locally 

Go to Mongodb site and register for an account. Once registered you will be redirect and prompted to pick a plan. There are 3 plans to choose from. For our purposes, a free account will be enough as it caters to small web applications. 

![registration](https://github.com/eswong610/user-guide-docs/blob/gh-pages/Screen%20Shot%202020-02-27%20at%202.17.37%20PM.png "LOGIN")

At the starter cluster webpage, it will give you options to choose a cloud provider and a region. Choose AWS and a recommended region. Make sure the cluster tier is checked under the free forever column. 
Once you click create starter cluster, a new cluster will be created which will take around 1-2 minutes 

In your terminal, paste in `brew tap mongodb/brew`    to find the Mongodb tap
Then type in `brew install mongodb-community` to install mongodb

To check you have the Mongodb installed, and you have the right version, type in `mongo --version` into the terminal.  
You should have the above as the output. 


