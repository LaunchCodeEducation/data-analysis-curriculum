+++
title = "Left and Right Joins"
date = 2024-04-02T14:13:14-05:00
draft = false
weight = 3
+++

## Left Outer Join

Joining two tables with a **left outer join** gives us a result set which
includes all values in the left table and any matching records from the right
table.

If we use a left outer join to combine `johnson_wedding` and `johnson_vow_renewal` in a query, the result set includes all of the guests invited to the wedding and any guests who were also invited to the vow renewal.

```sql {linenos=table}
SELECT last_name, first_name
FROM johnson_wedding
LEFT JOIN johnson_vow_renewal ON johnson_wedding.guest_id = johnson_vow_renewal.guest_id;
```

.. figure:: figures/leftouterjoin.png
   :alt: Venn diagram highlighting the center and entirety of left circle.

The Venn diagram above shows the result set highlighted in blue.

## Right Outer Join

Joining two tables with a **right outer join** gives us a result set that
includes all values in the right table and any matching records from the left
table.

If we use a right inner join to combine `johnson_wedding` and `johnson_vow_renewal` in a query, the result set includes all of the guests that were invited to the vow renewal and any guests who were also invited to the wedding.

```sql {linenos=table}
SELECT last_name, first_name
FROM johnson_wedding
RIGHT JOIN johnson_vow_renewal ON johnson_wedding.guest_id = johnson_vow_renewal.guest_id;
```

.. figure:: figures/rightouterjoin.png
   :alt: Venn diagram highlighting the center and entirety of right circle.

The Venn diagram above shows the result set highlighted in blue.
