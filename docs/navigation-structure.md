---
layout: default
title: Set-up 
nav_order: 5
---

## Step 1 
{: .no_toc }

### Set up a Mongodb account and install it locally 

This set up will include setting up a Mongodb Atlas account and downloading it for local use. 

Head over to the Mongodb website at https://www.mongodb.com/cloud/atlas/signup and register for an account. Once registered you will be redirect and prompted to pick a plan. There are 3 plans to choose from. For our purposes, a free account will be enough as it caters to small web applications. 

![registration](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/register.png?raw=true "LOGIN")

At the starter cluster webpage, it will give you options to choose a cloud provider and a region. Choose AWS and a recommended region. 

![cloudprovider](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/cloudprovider.png?raw=true "cloud provider")


Make sure the cluster tier is checked under the free forever column in the M0 Sandbox row. 
![freecluster](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/cluster.png?raw=true "Free cluster")

Once you enter a name and click create starter cluster, a new cluster will be created which will take around 1-2 minutes. 

By now, you will have set up an account and we will proceed with installing Mongodb locally. 

Using Homebrew, you will install Mongodb. In your terminal, paste in the following code
`brew tap mongodb/brew`    
to find the Mongodb tap. 

We will install the community server since it is available open source for Mac OS, Windows and Linux. 
Type in `brew install mongodb-community` to install mongodb in the terminal

To check you have the Mongodb installed, and you have the right version, type in `mongo --version` into the terminal.  
You should the following output. 
![mongoversion](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/terminal.png?raw=true "mongo version terminal")


