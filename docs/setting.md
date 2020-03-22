---
layout: default
title: Setting Up
nav_order: 2
---

# How To Set Up A Mongodb Account And Configure Cluster Settings
{: .no_toc }

We are going to start off by making a Mongodb Atlas account and configuring the cluster settings. 

## Step 1 - Creating a Mongodb Account.

Head over to the Mongodb website at https://www.mongodb.com/cloud/atlas/signup and register for an account. Once registered you will be redirect and prompted to pick a plan. There are 3 plans to choose from. For our purposes, a free account will be enough as it caters to small web applications. 

![registration](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/register.png?raw=true "LOGIN")

## Step 2 - Choosing Your Cluster And Region
To start your database, you will create a new _cluster_. At the starter cluster webpage, it will give you options to choose a cloud provider and a region. 

Choose AWS and a recommended region for your cluster. 

![cloudprovider](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/cloudprovider.png?raw=true "cloud provider")


<$>[note]
**Note:** Make sure the cluster tier is checked under the free forever column in the M0 Sandbox row. 
<$>

![freecluster](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/cluster.png?raw=true "Free cluster")

Once you enter a name and click create starter cluster, a new cluster will be created which will take around 1-2 minutes. 

By now, you will have set up an account and we will proceed with configuring the settings. 


## Step 3 - Logging Onto Mongodb Atlas

Log into mongodb atlas using your email and password.

You should be redirected into this page if you have already set up a free cluster.


![mongo](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/mongodbaltasfront.png?raw=true)

## Step 4 - Creating A Database User

>The purpose of a *database user* is to authorize the application to read, write or both onto the cluster based on the >settings you pick.

On the left sidebar, go to the Security tab and select **database access**. 

Click the add new user on the far right side. A new window should pop up like the image below.

![mongo](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/newuser.png?raw=true)


From here you will enter in an username and a password. Save this in a notepad or safe viewable file. For the database priveleges you will set it to **read and write to any database**.

## Step 3 - Whitelisting Your IP Address

>This is a security step that will ensure that database access will be restrict to your current IP. You can also allow >access for any IP , however you risk higher chance of security breach and exploits.

Go to  **Network access** in the side bar navigation, and add new IP address to whitelist your IP address.
There are two options to choose from. You can give permission to access from anywhere or only from specified IP adresses. 

<$>[warning]
**Warning :** Giving access to the database from anywhere could potentially be a security threat. Please keep this in mind when choosing your options.
<$>

## Step 4 - Getting Your URI String

The URI string will be important for later steps. It is essential to connecting any applications you make to the database we have just created in Mongodb.

Return back to the main page, click on the clusters on the sidebar. You will be viewing your current cluster.
Right below the cluster name, there is a connect button. Click on it and a new window will be prompted.


![mongo](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/connect.png?raw=true)


From here, click the **Connect your Application** option.
A new page will say connect to <your cluster name>.
  

![mongo](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/uristring.png?raw=true)

In the driver, make sure you select the correct language. For this user guide, you will be using node.js.
The window will generate you the uri connection string will you can now use to connect your application to mongodb cluster.
