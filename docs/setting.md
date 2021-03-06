---
layout: default
title: Setting Up
nav_order: 2
---

# How To Set Up A Mongodb Account And Configure Cluster Settings
{: .no_toc }

We are going to start off by making a Mongodb Atlas account and configuring the cluster settings. We will go through the settings step by step to make sure it is configured to our needs for a basic and small web application. 

## Step 1 - Creating a Mongodb Account.

1. Head over to the Mongodb website at `https://www.mongodb.com/cloud/atlas/signup` and register for an account. 
Once registered you will be redirect and prompted to pick a plan. There are 3 plans to choose from. For our purposes, a free account will be enough as it caters to small web applications. 

2. Choose the free $0 plan option.

![registration](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/register.png?raw=true "LOGIN")

## Step 2 - Choosing Your Cluster And Region
1. Create a new cluster to start your database. 
At the starter cluster webpage, it will give you options to choose a cloud provider and a region. 

2.  Choose **AWS** and a recommended region for your cluster. 

![cloudprovider](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/cloudprovider.png?raw=true "cloud provider")


```
Note: Make sure the cluster tier is checked under the free forever column in the M0 Sandbox row. 
```

![freecluster](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/cluster.png?raw=true "Free cluster")

Once you enter a name and click create starter cluster, a new cluster will be created which will take around 1-2 minutes. 

By now, you will have set up an account and we will proceed with configuring the settings. 


## Step 3 - Logging Onto Mongodb Atlas

1. Log into Mongodb Atlas using your email and password.

You should be redirected into this page if you have already set up a free cluster.


![mongo](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/mongodbaltasfront.png?raw=true)

## Step 4 - Creating A Database User

```
Note: The purpose of a database user is to authorize the application to read, write or both onto the cluster based on the settings you pick.
```

1. Click on to the **Security tab** and select **database access**. 

2. Click the **Add New User** on the far right side. A new window should pop up like the image below.

![mongo](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/newuser.png?raw=true)


From here you will enter in an username and a password. Save this in a notepad or safe viewable file. For the database priveleges you will set it to **read and write to any database**.

## Step 3 - Whitelisting Your IP Address


1. Go to  **Network access** in the side bar navigation, and add new IP address to whitelist your IP address.
There are two options to choose from. You can give permission to access from anywhere or only from specified IP adresses. 


```
Warning: This is a security step that will ensure that database access will be restrict to your current IP. You can also allow access for any IP , however you risk higher chance of security breach and exploits.
```

## Step 4 - Getting Your URI String

The URI string will be important for later steps. It is essential to connecting to any applications you make with the database we have just created in Mongodb.

1. Return back to the main page, click on **Clusters** on the sidebar. You will be viewing your current cluster.
Right below the cluster name, there is a connect button. 

2. Click on the **Connect** button and a new window will be prompted.


![mongo](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/connect.png?raw=true)


3. Click the **Connect your Application** option.
A new page will say connect to <your cluster name>.
  

![mongo](https://github.com/eswong610/user-guide-docs/blob/gh-pages/assets/images/uristring.png?raw=true)

In the driver, make sure you select the correct language. For this user guide, you will be using `node.js.`
The window will generate you the uri connection string will you can now use to connect your application to mongodb cluster.


---
By now, you should have your first cluster up and running with the necessary resources to connect to a remote web application. For a more in-depth tutorial on various other setting configurations, please visit: 
`https://docs.atlas.mongodb.com/getting-started/`

[Next is NodeJS](/expressconnect.md){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
