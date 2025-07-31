+++
title = "What is SQL?"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 1
+++

So far, we have used spreadsheets to hold data. However, these are limited in how much information they can store.
This is where a relational database comes in.

**Relational databases** store data in tables, which are connected to each other in a variety of different ways.
Tables contain columns and rows of information, with each column specifying the data type of the information within, and each row having a unique key.
Relational databases provide flexibility for both expansion of the database and modification of the relationships between the tables as things change.

In order to access our information, we need to use a tool that can talk to a relational database. 
**Structured Query Language** or **SQL** is the main tool used by programmers to work with these data structures.
SQL is a **Relational Database Management System** or **RDMS**. 
We can use SQL to perform many essential operations on a database, such as adding and removing data.

## Transact-SQL

There are many different types of SQL. For this class, we will be using **Transact-SQL** or **T-SQL**. T-SQL is the pre-eminent form of SQL for managing large data stores and is an extension of the SQL language maintained by Microsoft.

{{% notice blue Note %}}

Throughout this course, we will be referring to T-SQL as SQL. This is common in industry and it can be assumed that when you hear SQL, the speaker is referring to T-SQL.

{{% /notice %}}

To get started with the chapter, you need to [set up Visual Studio Code for SQL]({{% relref "./../../../installations/install-vscode-sql" %}}) and connect to the instance of SQL server.

SQL has many of the same data types you have already worked with so far in this course. However, some of the types, like `string`, have a different name in SQL.

### Numbers

For integers, we will be using the `int` data type. As you grow in your career, you may see others such as `bigint` or `tinyint` in SQL databases.
The [SQL documentation](https://learn.microsoft.com/en-us/sql/t-sql/data-types/data-types-transact-sql?view=sql-server-ver16) offers a full breakdown of these different integer types.

SQL also has a `decimal` data type which, as the name implies, allows for a specified number of digits after the decimal. 

### Strings

There is no `string` type in SQL. Instead, we use the `varchar` type.
`varchar` produces a string of variable length, but we have to tell SQL how long the string will be *at a maximum*.
Therefore, when we use `varchar` in a declaration, we add the maximum number of characters like so: `VARCHAR(250)`. That declaration specifies that the string will be, at a maximum, 250 characters.

### Boolean

SQL does not support boolean data types for columns, but it can support a `bit` data type. A `bit` data type can either be `1` to represent true, `0` to represent false, or `NULL`.

## Check Your Understanding

{{% notice green Question %}}

Which of the following are supported data types in SQL? Select ALL that are correct.

1. `tinyint`
1. `int`
1. `double`
1. `varchar`
1. `boolean`
1. `string`

{{% /notice %}}

<!-- 1,2,3,4 -->
