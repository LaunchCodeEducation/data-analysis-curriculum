+++
title = "What is a Join?"
date = 2024-04-02T14:13:14-05:00
draft = false
weight = 1
+++

A **join** combines two tables into one result set.
We can use joins when we want to query two tables at the same time.
Whenever we join two tables, we have to specify the condition upon which the
tables need to be joined.

In SQL, there are four different types of joins:

1. Inner Join
1. Left Outer Join
1. Right Outer Join
1. Full Outer Join

No matter which join you are working with, the general syntax for the query
looks like so:

```sql {linenos=table}
SELECT column_name_1, column_name_2, ....
FROM table_a
TYPEOFJOIN JOIN table_b ON table_a.column_name_1 = table_b.column_name_1;
```

In this general query, we specified what columns we want (or we could have used
the `*` to read data from all columns). We have also specified that
`table_a` is the *left* table and that `table_b` is the *right* table. On
line 3, we need to include the type of join as part of our query with the
`JOIN` keyword and the condition upon which we are joining the tables. Our
condition follows the `ON` keyword and tells SQL what we believe to be
matching records. This may mean we want to join on matching customer ids or
matching dollar amounts or matching dates depending on the tables we are
working with and what questions we need to answer.

Let's dive into the specific type of joins and how each one works.