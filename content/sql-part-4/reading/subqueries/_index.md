+++
title = "SQL Subqueries"
date = 2024-03-12T15:04:03-05:00
draft = false
weight = 1
+++

**Subqueries** are similar to nested Python conditionals in that it is a SQL statement nested inside of another. Like conditionals, one of the main use cases for subqueries is to apply additional logic or filtering to your data. As that is the case, subqueries are most often nested inside of a `WHERE` or `HAVING` clause although, it is not required. 

The structure of a subquery has the following attributes:
1. `SELECT` query
1. `FROM` clause
    - optional `WHERE` clause
    - optional `GROUP BY` clause
    - optional `HAVING` clause
1. Must be wrapped in parentheses

One of the many benefits of using subqueries is that it allows you to apply aggregate functions within  `WHERE` clause that you will see in an example below.

{{% notice blue Note "rocket" %}}
The following examples will reference the tables `Movies` and `More_Movies`. You can view tables data here: [Movies and More_Movies table data]({{< relref "../union-intersect-except/table-data/_index.md" >}})
{{% /notice %}}

## Non-Correlated Subqueries

Non-Correlated subqueries are queries that can run on their own regardless of the outer query. This type of subquery will only run one time instead of executing row by row.

{{% notice blue Example "rocket" %}}
The example below will utilize a nested subquery to return the row with the max rotten tomatoes score:

```SQL {linenos=table}
SELECT * FROM Movies
WHERE rt_score = (SELECT MAX(rt_score) FROM Movies);
GO
```

**Output**

![Subquery within a WHERE clause of a SELECT statement](pictures/subquery.png?classes=border)

The output of a simple one-line `SELECT` query when applying an aggregate function would look like the following:

```SQL
SELECT MAX(rt_score) FROM Movies
```

![Single-line select query applying an aggregate function](pictures/simple-select-query.png?classes=border)

One major difference to note here is that when the aggregate function is applied using a subquery you receive the entire row of data as a result, instead of just the single value that satisfies the aggregate function within the column.
{{% /notice %}}

{{% notice blue Example "rocket" %}}
What if you wanted to produce a result set of movies from the `More_Movies` table with a higher score than the average score of all movies within the `Movies` table? Let's start by gathering the average score from the `Movies` table:

```sql
-- gather average score from Movies table
SELECT AVG(rt_score) FROM Movies
GO
```

**Result**

![Result from running a SELECT AVG() query on the Movies table](pictures/rt-avg-score-from-movies.png?classes=border)

Now let's apply the same logic within a subquery:

```sql
-- Select all data from More_Movies
SELECT * FROM More_Movies
-- Apply condition that we only want movies with a rt_score greater than --> subquery statement/expression
WHERE rt_score > 
-- Use subquery to gather AVG rt_score from the Movies table (this is non-correlated as it does not reference and columns within the More_Movies table)
(SELECT AVG(rt_score) FROM Movies)
GO
```

**Result**

![Result from running a subquery using the same logic above on a separate table of data](pictures/rt-avg-score-compare.png?classes=border)
{{% /notice %}}

{{% notice blue Example "rocket" %}}
The last non-correlated example will utilize the `IN` keyword within a `WHERE` clause.

```sql
-- Select all from Movies
SELECT * FROM Movies
-- Filter outer query based on genres from inner query
WHERE genre IN (SELECT genre FROM Movies WHERE rt_score > 88);
-- Will result in all movies that are within genres that have a minimum of one film with a score above 88
GO
```

![Query utilizing the IN keyword within a WHERE clause against the Movies table](pictures/where-in.png?classes=border)

The same query and subquery using the `More_Movies` table:

![Query using the IN keyword within a WHERE clause against the More_Movies table](pictures/more-movies-where-in.png?classes=border)
{{% /notice %}}

## Correlated Subqueries

**Correlated Subqueries** are inner queries that rely on data from a column specified in the outer query. A common trait among correlated subqueries is that they will execute once for every row in the outer query and cannot execute on its own. This process can be rather performance intensive and consume lots of memory if you are working on larger datasets. 

Let's take a look at an example below:

{{% notice blue Example "rocket" %}}
```sql
-- Select all from the Movies table and create an alias (m1) for it
SELECT * FROM Movies AS m1
-- Where clause 
WHERE rt_score = (
    -- subquery to select max rt_score from movies and create a new alias (m2) for it
    SELECT MAX(rt_score) FROM Movies AS m2
    -- subquery where clause to compare movies within the same genre
    WHERE m1.genre = m2.genre
    -- check rt_score against movie with highest score
    AND m1.rt_score <= m2.rt_score
    )
GO
```

**Result**

![Correlated subquery against the movies table, comparing the rt_scores within the same genre](pictures/correlated-subquery-example.png?classes=border)
{{% /notice %}}

## Check Your Understanding

{{< mermaid >}}
---
title: Non-Correlated and Correlated Subqueries
---
graph LR;
    A[Non-Correlated] --> B(self-contained) --> C(executes only once)
    D[Correlated] --> E(cannot execute alone) --> F(executes per row)
{{< /mermaid >}}

{{% notice green Question "rocket" %}}
Is the following block of code an example of a correlated or non-correlated subquery?

```sql
SELECT * FROM More_Movies
WHERE release IN (
    SELECT release from More_Movies 
    WHERE release > 2010
    )
GO
```
<!-- Solution: non-correlated -->
{{% /notice %}}