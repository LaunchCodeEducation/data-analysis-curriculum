+++
title = "Nested Subqueries"
date = 2024-03-12T15:04:03-05:00
draft = false
weight = 2
+++

**Nested subqueries** are subqueries within subqueries, Not to be confused with a nested query (subquery). This adds an addiitonal layer of complexity to your query but allows for more filtering and manipulation should you need it.

## General Structure:

```sql
SELECT statement FROM table
WHERE expression = (
    SELECT statement FROM table
    WHERE expression = (
        SELECT statement FROM table
        WHERE expression
    )
)
```

{{% notice blue Example "rocket" %}}
```sql
-- select all from More_Movies table
SELECT * FROM More_Movies
-- specify genre with IN keyword
WHERE genre IN (
    -- select all genres from More_Movies table
    SELECT genre FROM More_Movies 
    -- filter out genres from more_movies table that have a higher rt_score than movies in Movies table
    WHERE rt_score > (
        -- the max rt_score from Movies table
        SELECT MAX(rt_score) FROM Movies)
)
GO
```

![Nested subquery to find genres from the More_Movies database that contain a single movie with a higher rt_score than the highest available in the Movies table](pictures/nested-subquery.png?classes=border)
{{% /notice %}}

Nested subqueries can be quite useful when filtering data from multiple tables as seen in the example above. We were able to filter out genres from the `More_Movies` table that did not have a higher rt_score than the highest score in the `Movies` table. Let's take a look at what happens if we add a movie within an existing genre to the `More_Movies` table that has a higher score so we can compare.

{{% notice blue Example "rocket" %}}
```sql
INSERT INTO More_Movies (id, title, genre, release, rt_score)
VALUES (14, 'Back To The Future', 'Science Fiction', 1985, 97)
GO
```

```sql
SELECT * FROM More_Movies
WHERE genre IN (
    SELECT genre FROM More_Movies
    WHERE rt_score > (
        SELECT MAX(rt_score) FROM Movies)
)
GO
```

**Result**

![Compare the same query as the previous example after adding a movie with a high rating to view the difference](pictures/compare-example.png?classes=border)
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
What is the key difference between a nested query and a nested subquery?
<!-- Solution: A nested query is simply a subquery, a nested subquery is a subquery within a subquery! -->
{{% /notice %}}