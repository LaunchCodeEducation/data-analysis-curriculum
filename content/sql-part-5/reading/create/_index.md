+++
title = "Create"
draft = false
weight = 2
+++

Previously, we outlined the four types of operations we can perform with SQL queries as CRUD. We have only done read operations so far with `SELECT` queries. Now we get to focus on operations that create new tables and add new records to existing tables.

## Creating Tables

When creating new tables, you first want to sketch out what columns the table should have. Modifying a table after creation to add a column you didn't think of is not advisable so you want to make sure that you know what that table needs to have before you run your query to create the table.

Let's say that we work for a major grocery store chain and are part of the team evaluating the success of their rewards program. The database is called `FineFoods`, but the tables associated with the rewards program are going to be groupe together in a schema called `rewards`. As the rewards program rolls out, we want to track which in-app coupons were used by consumers 

```sql {linenos=table}

```

## Adding Records