+++
title = "Full Outer Joins"
date = 2024-04-02T14:13:14-05:00
draft = false
weight = 4
+++

Joining two tables with a **full outer join** gives us a result set that
includes all records from both tables. Full outer joins are important to SQL,
but the syntax is not supported in MySQL. Instead, to achieve a full outer
join, you have to work with a left outer join and a right outer join. To show
what a full outer join looks like in other types of SQL, we have simulated some
possible syntax below.

Now that another event planner has joined Mary's company, to get all of the
events run by the company in August, we can use a full outer join to combine
`mary_events` and `leah_events`.

```sql {linenos=table}
SELECT *
FROM mary_events
FULL OUTER JOIN leah_events ON mary_events.month = leah_events.month
WHERE mary_events.month = 08;
```

.. figure:: figures/fullouterjoin.png
   :alt: Venn diagram with the entirety of both circles highlighted.

The Venn diagram above shows the result set highlighted in blue.

If you do want to try out a full outer join, the syntax to simulate it looks some like this:

```sql {linenos=table}
SELECT * FROM table_a LEFT JOIN table_b ON table_a.column_name_1 = table_b.column_name_1
UNION
SELECT * FROM table_a RIGHT JOIN table_b ON table_a.column_name_1 = table_b.column_name_2;
```

`UNION` is used to bring together the result sets of 2 `SELECT` queries.
Check out the [documentation](https://dev.mysql.com/doc/refman/8.0/en/union.html) for more information on how `UNION` works.