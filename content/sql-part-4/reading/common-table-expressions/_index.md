+++
title = "Common Table Expressions"
date = 2024-07-15T07:15:00-06:00
draft = false
weight = 1
+++

**Common Table Expressions** or CTEs are an alternative approach to subqueries, and can be easier to both logically read and write, as well as allow for their output to be referenced multiple times within a SQL code block.

The structure of a CTE is similar to a subquery, but has the following attributes:
1. `WITH` statement and an aliased name of the CTE
2. `SELECT` query
1. `FROM` clause
    - optional `WHERE` clause
    - optional `GROUP BY` clause
    - optional `HAVING` clause
1. Must be wrapped in parentheses
2. `,` to separate each CTE before the main query

The most efficient way to demonstrate the usefulness of a CTE is to rewrite one of the previously presented subqueries.

```SQL {linenos=table}
WITH cte_max_rt_score AS
(
SELECT MAX(rt_score)
FROM Movies
)
SELECT * FROM Movies
WHERE rt_score = (SELECT * FROM cte_max_rt_score);
```

The structre of a CTE flows from top to bottom, where each CTE — you can have more than one, enclosed in `()` and separated by `,` — is written first, and then referenced in the main query which follows. Each CTE can be referenced as if it were a table which existed in the database, and hence can be used in a FROM or JOIN statement as well as referenced more than once. It is also important to point out the CTEs only exist within the specific SQL block of code and are not created within the actual database — they merely "act" like actual tables.

As the complexity of a subquery or nested subqueries grows, the more useful CTEs become, given you write those elements first and can test each portion to ensure the appropriate results are returned. The readability of the SQL code can also improve, especially compared to nested subqueries, where each step follows the next as opposed to reading from the inner most subquery to the outer most.

## Check Your Understanding

{{% notice green Question "rocket" %}}
What are the main benefits of a CTE compared to a subquery?
<!-- Solution: CTEs improve the readability of the SQL code and allow for the output to be referenced in the SQL code block, even more than once, as if it were a table -->
{{% /notice %}}
