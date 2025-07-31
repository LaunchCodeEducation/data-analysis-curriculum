+++
title = "Schemas"
draft = false
weight = 1
+++

Before we can dive into the queries, we need to talk about schemas.

A **schema** is a way to group database objects(tables, views, ect) into a logical collection. 
Let's look at the `AdventureWorks2019` database in Visual Studio Code. 

In the Object Explorer, if you expand the tables, you will see something like this:

![File Tree, Tables Folder with Human Resources schemes highlighted](./pictures/TableSchemas.png)

Notice how the tables are grouped together. The syntax is `schema_name.table_name`. 
You wouldn't want someone accidentally deleting a table or being able to view sensitive information. 
Schemas allow companies to easily control who has access to specific tables and how they have access.

Another way to think of schemas is that they are like using folders on your Google Drive. 
You can group together like-documents and control who has access by granting different permissions to different people. 
At any time you can also change permissions or remove someone from having access. You can also move documents from one folder to another. 
Multiple people can work together in each folder. The creator of the folder or document is the owner. 
But, you can easily reassign the ownership to another person. The same is true of schemas.
