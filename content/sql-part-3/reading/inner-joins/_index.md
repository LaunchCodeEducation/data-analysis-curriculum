+++
title = "Inner Joins"
date = 2024-04-02T14:13:14-05:00
draft = false
weight = 2
+++

Joining two tables with an **inner join** produces a result set that only
includes the values that are present in *both* tables. For the rest of this chapter, we will be returning to Mary, the event planner, to see what different types of joins can do.

Mary is working with the Johnsons again. She previously planned their wedding and is now planning their vow renewal. If we use an inner join to combine `johnson_wedding` and `johnson_vow_renewal` in a query, we can see what guests are invited to both the vow renewal and the wedding.

```sql {linenos=table}
SELECT last_name, first_name
FROM johnson_vow_renewal
INNER JOIN johnson_wedding ON johnson_vow_renewal.guest_id = johnson_wedding.guest_id;
```

This query will give us a result set of the first and last names of the guests from the `johnson_vow_renewal` table that are also in the `johnson_wedding` table.

![Venn diagram highlighting just the center where the two circles meet](./pictures/innerjoin.png)

The Venn diagram above shows the result set highlighted in blue.

You can filter a join with the `WHERE` clause as well. In the case of the Johnsons, Mary may want to see which guests who attended the wedding are confirmed for the vow renewal.

```sql {linenos=table}
SELECT last_name, first_name
FROM johnson_vow_renewal
INNER JOIN johnson_wedding ON johnson_vow_renewal.guest_id = johnson_wedding.guest_id
WHERE johnson_wedding.attending = 1 AND johnson_vow_renewal.attending = 1;
```

Now, let's say we want to use an aggregate function with our join. We can use `GROUP BY` to group the result sets by dietary restrictions. We can write the following inner join.

```sql {linenos=table}
SELECT last_name, first_name
FROM johnson_vow_renewal
INNER JOIN johnson_wedding ON johnson_vow_renewal.guest_id = johnson_wedding.guest_id
GROUP BY johnson_vow_renewal.diet;
```

The above query groups the result set by dietary restriction, but since Mary is currently working with the caterers to plan out the dinner options, she wants to make sure that she is only looking at guests who RSVP'd yes for the vow renewal. We cannot use `WHERE` with an aggregate function like `GROUP BY` so we need to use `HAVING` instead.

```sql {linenos=table}
SELECT last_name, first_name
FROM johnson_vow_renewal
INNER JOIN johnson_wedding ON johnson_vow_renewal.guest_id = johnson_wedding.guest_id
GROUP BY johnson_vow_renewal.diet
HAVING johnson_vow_renewal.attending = 1;
```

`GROUP BY` is frequently used in conjunction with aggregate functions, which were introducted in Part 2. To be clear, if you use an aggregate function in a `SELECT` statement along with at least one other column, `GROUP BY` is required.

Let us pose the question of "How many guests of both the wedding and renewal are there with each last name?" The following query would provide such insight.

```sql {linenos=table}
SELECT last_name, COUNT(first_name) AS "Number of Guests"
FROM johnson_vow_renewal
INNER JOIN johnson_wedding ON johnson_vow_renewal.guest_id = johnson_wedding.guest_id
GROUP BY last_name;
```

The aggregate `SUM` function could also be used in this instance, given the `attending` column:

```sql {linenos=table}
SELECT last_name, SUM(johnson_vow_renewal.attending) AS "Number of Guests"
FROM johnson_vow_renewal
INNER JOIN johnson_wedding ON johnson_vow_renewal.guest_id = johnson_wedding.guest_id
GROUP BY last_name;
```

Before we proceed, you will notice the use of a column alias in the above code. This is not the only place where an alias can be used in SQL. Table names can have aliases as well, and this is often useful when creating joins and referencing column names for a specific table. The use of table aliases allows us to shorten, sometimes significantly, the name of the table when it is referenced in a `SELELCT`, `HAVING`, or other SQL statement. When creating an alias for a table, it is good practice for the alias to be short (generally two to three charaters) and be representative of the full table name (so, for example, not creating an alias named "a") as this makes identifying which table the alias belongs to easier for the person reading the code.

The table alias is created simply by typing the alias immediately after the full table name in the `FROM` and `JOIN` statements. The `AS` statement is generally omitted, as it is not required.

The following shows how the above SQL code can be rewritten using table aliases.

```sql {linenos=table}
SELECT last_name, SUM(jvr.attending) AS "Number of Guests"
FROM johnson_vow_renewal jvr
INNER JOIN johnson_wedding jw ON jvr.guest_id = jw.guest_id
GROUP BY last_name;
```

In the above SQL code, we have created the alias `jvr` for the table `johnson_vow_renewal` and the alias `jw` for the table `johnson_wedding`. Notice both are representative of their respective full (original) table name, as well as much shorter than the original. The alias does not rename the table in the datebase — it only exists within the SQL code. Also notice you can reference the table aliases in the `SELECT` statement which prceedes the creation of the aliases in the `FROM` and `JOIN` statements!

## Check Your Understanding

{{% notice green Question %}}

What does an inner join do?

1. Returns results with matching rows in both tables.
1. Returns results with all the rows from the left table with null values for unmatched rows from the right table.
1. Returns results with all the rows from the right table with null values for unmatched rows from the left table.
1. Returns results from all the rows from both tables with null values filled in for all unmatched rows.

{{% /notice %}}

<!-- 1 -->
