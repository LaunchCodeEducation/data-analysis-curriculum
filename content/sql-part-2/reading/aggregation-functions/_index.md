+++
title = "Aggregation Functions"
date = 2024-03-26T11:48:30-05:00
draft = false
weight = 3
+++

Use the examples and links in the following tables to get familiar with the various SQL [Aggregate Functions](https://docs.microsoft.com/en-us/sql/t-sql/functions/aggregate-functions-transact-sql?view=sql-server-ver15).

The following examples are using the BooksDB.  

| **Function** | **Definition** | **Syntax** | **Value Returned** |
|--------------|-----------------|------------|---------------------|
| [`SUM`](https://docs.microsoft.com/en-us/sql/t-sql/functions/sum-transact-sql?view=sql-server-ver15) | Returns sum of all values or DISTINCT values. | `SELECT SUM(ratings_2) FROM BooksDB.dbo.books;` | 31108850 |
| [`MAX`](https://docs.microsoft.com/en-us/sql/t-sql/functions/max-transact-sql?view=sql-server-ver15) | Returns the highest value. | `SELECT MAX(ratings_2) FROM BooksDB.dbo.books;` | 436802 |
| [`MIN`](https://docs.microsoft.com/en-us/sql/t-sql/functions/min-transact-sql?view=sql-server-ver15) | Returns the lowest value. | `SELECT MIN(ratings_2) FROM BooksDB.dbo.books;` | 30 |


## `NULL` Functions 

### `IS NULL`

| **Function** | **Definition** | **Syntax** | **Value Returned** |
|--------------|-----------------|------------|---------------------|
| [`IS NULL`](https://docs.microsoft.com/en-us/sql/t-sql/queries/is-null-transact-sql?view=sql-server-ver15) | Determines whether value is null, often used as a condition with `WHERE`. | See examples below. | |

{{% notice blue Example "rocket" %}}
```SQL
SELECT  TOP 5 title, isbn, original_publication_year
FROM BooksDB.dbo.books
WHERE isbn IS NULL AND original_publication_year IS NULL;
```

**Value Returned**
(3 rows affected)

|    | title                                     | isbn     | original_publication_year |
|----|--------------------------------------------|---------|-----------------------|
| 1  | BookRags Summary: A Storm of Swords        | *NULL*   | *NULL*                |
| 2  | A Shade of Blood (A Shade of Vampire, #2)  | *NULL*   | *NULL*                |
| 3  | زغازيغ                                    | *NULL*   | *NULL*                |
{{% /notice %}}

{{% notice blue Note "rocket" %}}
In the first example, we asked for the `TOP` 5 rows, but only 3 qualified and were returned.
{{% /notice %}}

{{% notice blue Example "rocket" %}}
```SQL
SELECT title, original_title
FROM BooksDB.dbo.books
WHERE authors LIKE 'Sophocles%' AND original_title IS NULL;
```

**Value Returned**
|    | title | original_title |
|----|-------|----------------|
| 1  | The Oedipus Cycle: Oedipus Rex/Oedipus at Colonus/Antigone (The Theban Plays, #1-3)NULL | *NULL* |
{{% /notice %}}

### `IS NOT NULL`

| **Function** | **Definition** | **Syntax** |
|--------------|-----------------|------------|
| [IS NOT NULL](https://docs.microsoft.com/en-us/sql/t-sql/queries/is-null-transact-sql?view=sql-server-ver15) | Determines whether value is not null, often used as a condition with `WHERE`. | See examples below. |

{{% notice blue Example "rocket" %}}
```SQL
SELECT  TOP 5 title, isbn, original_publication_year
FROM BooksDB.dbo.books
WHERE isbn IS NOT NULL AND original_publication_year IS NOT NULL;
```

**Value Returned**

(5 rows affected)

|    | title                                                     | isbn      | original_publication_year |
|----|-----------------------------------------------------------|-----------|---------------------------|
| 1  | The Hunger Games (The Hunger Games, #1)                  | 439023483 | 2008                      |
| 2  | Harry Potter and the Sorcerer's Stone (Harry Potter, #1) | 439554934 | 1997                      |
| 3  | Twilight (Twilight, #1)                                   | 316015849 | 2005                      |
| 4  | To Kill a Mockingbird                                     | 61120081  | 1960                      |
| 5  | The Great Gatsby                                          | 743273567 | 1925                      
{{% /notice %}}

{{% notice blue Example "rocket" %}}
```SQL
SELECT title, original_title
FROM BooksDB.dbo.books
WHERE authors LIKE 'Sophocles%' AND original_title IS NOT NULL;
```

**Value Returned**

|    | title                              | original_title      |
|----|-------------------------------------|----------------------|
| 1  | Oedipus Rex (The Theban Plays, #1) | Οἰδίπους Τύραννος    |
| 2  | Antigone (The Theban Plays, #3)    | Ἀντιγόνη             |
{{% /notice %}}

### `ISNULL` 

| **Function** | **Definition** | **Syntax** |
|--------------|-----------------|------------|
| [`ISNULL`](https://docs.microsoft.com/en-us/sql/t-sql/functions/isnull-transact-sql?view=sql-server-ver15) | Replaces a specific null value. | See example below. |

{{% notice blue Note "rocket" %}}
Note the use of an alias in the example below.
{{% /notice %}}

{{% notice blue Example "rocket" %}}
```SQL
SELECT original_title, ISNULL(original_title, title) AS UpdatedOriginalTitle
FROM BooksDB.dbo.books
WHERE authors LIKE 'Sophocles%';
```

**Value Returned**

|    | original_title                     | UpdatedOriginalTitle                                                                  |
|----|-------------------------------------|---------------------------------------------------------------------------------------|
| 1  | Οἰδίπους Τύραννος                   | Οἰδίπους Τύραννος                                                                    |
| 2  | Ἀντιγόνη                            | Ἀντιγόνη                                                                             |
| 3  | NULL                                | The Oedipus Cycle: Oedipus Rex/Oedipus at Colonus/Antigone (The Theban Plays, #1-3) |
{{% /notice %}}

### `COALESCE`

| **Function** | **Definition** | **Syntax** |
|--------------|-----------------|------------|
| [`COALESCE`](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/coalesce-transact-sql?view=sql-server-ver15) | Returns the first value that is not null. Can also be used to test multiple expressions unlike `ISNULL`. Can be used to address null values when paired with string concatenation. | See examples below. |

{{% notice blue Example "rocket" %}}
The code below demonstrates returning the first non-null value.

```SQL
SELECT COALESCE(NULL, 'cat', 'bird');
SELECT COALESCE('cat', NULL, 'bird');
```

**Value Returned**

| *cat* | *cat* |
|-------|-------|
{{% /notice %}}

{{% notice blue Example "rocket" %}}
The code below demonstrates using paring `COALESCE` with concatenation.

```SQL
SELECT COALESCE(original_title, title) + ' by ' + authors AS 'Reading List'
FROM BooksDB.dbo.books
WHERE authors LIKE 'Sophocles%';
```

**Value Returned**

|    | *Reading List*                                                                                          |
|----|----------------------------------------------------------------------------------------------------------|
| 1  | Οἰδίπους Τύραννος by Sophocles, J.E. Thomas                                                               |
| 2  | Ἀντιγόνη by Sophocles, J.E. Thomas                                                                       |
| 3  | The Oedipus Cycle: Oedipus Rex/Oedipus at Colonus/Antigone (The Theban Plays, #1–3) by Sophocles, Dudley Fitts, Elena Bono, Robert Fitzgerald |
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Francis has a database that contains information about car rentals.  She wants to create a query that would return the oldest car the company owns.  Which aggregation method would be a good fit for this query?

1. `AVG`
1. `MIN`
1. `COUNT`
1. `MAX`
{{% /notice %}}

{{% notice green Question "rocket" %}}
Francis wants to find the car with the highest mileage.  Which aggregation method would be a good option for this query?

1. `MAX`
1. `AVG`
1. `COUNT`
1. `MIN`
{{% /notice %}}

{{% notice green Question "rocket" %}}
Francis wants to create a column that contains a complete address for each car rental office in her database.  She has a column for street address, suite number, city, state, and zip code.  After some quick EDA, she has discovered that every rental office has a street address, city, state, and zip code.  She also discovered that only about 20% have suite numbers while the remaining 80% are null.  What function would let her still join these elements into addresses without worrying about the null elements affecting the final output?  

1. `COALESCE`
1. `IS NOT NULL`
1. `ISNULL`
1. `IS NULL`
{{% /notice %}}