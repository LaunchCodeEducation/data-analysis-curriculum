+++
title = "Inner Joins"
date = 2024-04-02T14:13:14-05:00
draft = false
weight = 2
+++

Joining two tables with an **inner join** produces a result set that only
includes the values that are present in *both* tables.

If we use an inner join to combine `johnson_wedding` and `johnson_vow_renewal` in a query, we can see what guests are going to both the vow renewal and the wedding.

```sql {linenos=table}
SELECT last_name, first_name
FROM johnson_vow_renewal
INNER JOIN johnson_wedding ON johnson_vow_renewal.guest_id = johnson_wedding.guest_id;
```

This query will give us a result set of the first and last names of the guests from the `johnson_vow_renewal` table that are also in the `johnson_wedding` table.

.. figure:: figures/innerjoin.png
   :alt: Venn diagram highlighting just the center where the two circles meet.

The Venn diagram above shows the result set highlighted in blue.