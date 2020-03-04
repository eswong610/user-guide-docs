---
layout: default
title: Cluster setting
nav_order: 5
---

## Setting up your cluster

----

In this section, you will set up your cluster to allow a server such as node js to connect.

## step 1 - Logging onto Mongodb Atlas

Log into mongodb atlas using your email and password.

You should be redirected into this page if you have already set up a free cluster.

![mongo](/assets/images/mongodbaltasfront.png)


## step 2 - Creating a database user
>The purpose of a *database user* is to authorize the application to read, write or both onto the cluster based on the >settings you pick.

On the left sidebar, go to the Security tab and select the database access. 

Now press the add new user on the far right side. A new window should pop up like the image below.

![mongo](/assets/images/newuser.png)


From here you want to enter in an username and a password. Save this in a notepad or safe viewable file. For the database priveleges you will want to set it as "read and write to any database".

## step 3 - whitelisting your IP address

>This is a security step that will ensure that database access will be restrict to your current IP. You can also allow >access for any IP , however you risk higher chance of security breach and exploits.

Go to the Network access, and add new IP address to whitelist your IP address.

## step 4 - Getting the URI string

Return back to the main page, click on the clusters on the sidebar. You will be viewing your current cluster.
Right below the cluster name, there is a connect button. Click on it and a new window will be prompted.

![mongo](/assets/images/connect.png)

From here, you want to click the **Connect your Application** option.
A new page will say connect to <your cluster name>.
  
![mongo](/assets/images/uristring.png)
