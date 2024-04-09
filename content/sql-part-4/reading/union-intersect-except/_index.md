+++
title = "UNION, INTERSECT, EXCEPT"
date = 2024-03-12T15:04:03-05:00
draft = false
weight = 2
+++

## UNION

The `UNION` operator combines table rows from multiple query statements. This is especially useful if you would like to view data from multiple tables without including duplicates. By default, the `UNION` set operator will return data *without* duplicates. However, if you wish to include duplicates in your returned data you can do so by using the `ALL` flag with `UNION`.

{{% notice blue Example "rocket" %}}
```sql
-- Select all data from the Movies Table
SELECT * FROM Movies
-- Apply the UNION set operator to concatenate the two SELECT queries into a single result
UNION
-- Select all data from the More_Movies Table
SELECT * From More_Movies
GO
```

The above code will return a result set of data from the `Movies` and `More_Movies` tables with only unique rows (no duplicates).

```sql
SELECT * FROM Movies
-- Apply the UNION ALL set operator to include all data from both Movies and More_Movies tables
UNION ALL
SELECT * FROM More_Movies
GO
```

The above code using the `ALL` flag will return a result set of data from `Movies` and `More_Movies` with all rows from both tables (duplicates included).
{{% /notice %}}

The `UNION` operator does not require multiple tables in order to work. It is also useful for returning a set of data with only unique rows when working on the same table but with mutliple query statements.

{{% notice blue Example "rocket" %}}
```sql
SELECT * FROM Movies
WHERE genre = 'Science Fiction'
UNION
SELECT * FROM Movies
WHERE genre = 'Comedy'
GO
```

The above code will return a result set of data from the `Movies` table that are in the Science Fiction and Comedy genre, without providing any duplicates.
{{% /notice %}}

## INTERSECT

## EXCEPT