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

## step 3 - Getting the URI string

