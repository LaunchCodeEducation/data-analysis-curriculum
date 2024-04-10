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

## Check Your Understanding

{{% notice green Question %}}

What does an inner join do?

1. Returns results with matching rows in both tables.
1. Returns results with all the rows from the left table with null values for unmatched rows from the right table.
1. Returns results with all the rows from the right table with null values for unmatched rows from the left table.
1. Returns results from all the rows from both tables with null values filled in for all unmatched rows.

{{% /notice %}}

<!-- 1 -->