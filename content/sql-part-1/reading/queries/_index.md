+++
title = "SQL Queries"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 10
+++

When we want to perform an operation on a database, we write a SQL **query**.
Queries can vary widely in complexity and purpose depending on the operation we
need to perform. Each query produces a **result set** containing the requested
data. Ultimately, we can boil down each query's purpose into one of the
following four categories:

1. Create
1. Read
1. Update
1. Delete

**CRUD** or *Create*, *Read*, *Update*, *Delete* represents the four major
operations we perform when we work with data. For now, we are going to be focusing on just read queries. Later on, we will learn more about create, update, and delete queries.

{{% notice blue Note %}}

On this page, we will be using an example of an `events` database.
Our event planner, Mary, has a database storing the guest info of every event she has ever planned, as well as event info about each event.
She named each table of guest info after the event itself.

{{% /notice %}}

When reading data, we don't want to modify anything, we just want to know what
is there. In order to get information from a table, we need to use a `SELECT`
statement.

`SELECT` statements have a few different components to them. We need to know
what we are selecting, which table the information is in, and if necessary, we
can also use `WHERE` to apply a conditional. You may also oftentimes see the `USE` keyword which specifies which database in the instance of SQL server is needed for the query and `GO`, which lets T-SQL know that the query is complete and ready to be run. In general, `SELECT` statements look like the following:

```sql {linenos=table}
USE database_name;

SELECT column_name_1, column_name_2, ...
FROM table_name
WHERE some condition is true;

GO;
```

If Mary wants to get the information of all of the guests who are vegetarian at
the Li wedding, we need to use a `SELECT` statement to pull the first and
last names of guests who will be in attendance and are vegetarian. So, we will
`SELECT` the `last_name` and `first_name` columns `FROM` the
`li_wedding` table `WHERE` the value of `attending` is true or `1` and the
value of `diet` is `"vegetarian"`.

```sql {linenos=table}
SELECT last_name, first_name
FROM li_wedding
WHERE (attending = 1) AND (diet = "vegetarian");
```

If Mary just wants all of the guests for the Li wedding, we need to modify our
`SELECT` statement. We won't apply a `WHERE` condition to our query and we
will use a `*` to denote that we want all columns.

```sql
SELECT *
FROM li_wedding;
```

## Take Queries One Step Further

### Use an Alias

While you are querying a database, you may want to give a column a nickname to make the result set easier to read. You can use the `AS` keyword to specify an alias for a column. You might want to do this for Mary when she is working on the Li wedding like so:

```sql {linenos=table}
SELECT first_name, last_name, diet AS "Dietary Restriction"
FROM li_wedding
WHERE attending = 1;
```

This query would return a result set of all the people who are coming to the Li Wedding with their dietary restrictions, but instead of the result set specifying a `diet` column, it would say "Dietary Restriction". If your alias does not contain spaces, you do not need double quotation marks when specifying the alias name.

### Limiting Result Sets

You can limit the number of results returned with the `TOP` keyword. Let's say Mary wants to return 10 weddings from last year and all her weddings are stored in one table called `weddings`.

```sql {linenos=table}
SELECT TOP 10 *
FROM weddings
WHERE wedding_year = 2023;
```

In addition to using a number, you can also select the top 50% or another percentage with the following syntax:

```sql {linenos=table}
SELECT TOP 10 PERCENT *
FROM weddings
WHERE wedding_year = 2023;
```

### Sorting Results

Sorting the result set can help us get the answers we need faster. In the case of Mary's work as an event planner, she may want to sort the guests by last name so that she can efficiently put together place cards.

```sql {linenos=table}
SELECT last_name, first_name
FROM li_wedding
ORDER BY last_name;
```

Because `last_name` is full of string values, the query above will automatically sort alphabetically. To sort in reverse alphabetical order, you would need the `DESC` keyword.

```sql {linenos=table}
SELECT last_name, first_name
FROM li_wedding
ORDER BY last_name DESC;
```

If you want to order the result sets in numerical order for integer or decimal values, then the final clause in your query would look like `ORDER BY numerical_column ASC`, for ascending order and `ORDER BY numerical_column DESC` for descending order.

### Filtering

The following query served as an example of filtering:

```sql {linenos=table}
SELECT last_name, first_name
FROM li_wedding
WHERE (attending = 1) AND (diet = "vegetarian");
```

We can use operators such as `=` and `<=` to specify a specific value for a column that we would like to look for.

In the case of strings, we can also use `LIKE` to perform **pattern matching**. Pattern matching allows us to look for similar strings as opposed to just equal strings. For example, pattern matching might help in situations where two last names are similar or to find results where there might be a typo. We use the wildcard operator in conjunction with `LIKE` to specify zero or more characters can appear where there is a `%`.

If Mary wants to ensure that all the members of the extensive Smith family are seated together at the Li wedding, we would need to use the `LIKE` operator to ensure that we get the main Smiths, that one branch of the family called the Smithes, and anyone with a name that is hyphenated such as the Smythe-Smiths.

```sql {linenos=table}
SELECT first_name, last_name
FROM li_wedding
WHERE last_name LIKE '%Smith%';
```

### Grouping the Result Set

Finally, we can group the result set. We might want to group our result set based on table numbers if we are working on the `events` database.

```sql {linenos=table}
SELECT first_name, last_name
FROM li_wedding
GROUP BY table_number;
```

### SQL Comments

Adding brief documentation and notes to your SQL code can pay dividends down the road, making your code easier to read and understand its intent for others as well as your "future self" should you need to reuse the code some time later and facilitating your refamiliarization with the code, its purpose, and, for example, why specific filters were chosen. Comments do not impact the execution of the code, but are there to help the person reading the code to understand and maintain it.

Let's walk through three examples of SQL comments and their use cases. First, the single-line comment.

```sql {linenos=table}
-- Ensure all members of the extensive Smith family are seated together
SELECT first_name, last_name
FROM li_wedding
WHERE last_name LIKE '%Smith%';
```

Single-line comments are added by inserting a double dash "`--`" before the text that follows. These are generally used to add a brief statement explaining the intent or purpose of the specific block of code. As the name implies, the comment is just a single line only.

What if you want to add additional detail or further explain a portion of code, requiring additional lines of code? The easiest method to do so is through the use of multi-line comments. Multi-line comments start with "`/*`" and end with "`*/`", such as the following:

```sql {linenos=table}
/* Ensure all members of the extensive Smith family are seated together
   As there are several variations of the name "Smith" in their family
   the LIKE operator will be used to capture the entire family */
SELECT first_name, last_name
FROM li_wedding
WHERE last_name LIKE '%Smith%';
```
All text inbetween the "`/*`" and "`*/`" are identified as comments. Multi-line comments are used to provide additional detail on a block of code, or can also be used to provide details of who was the author of the code, when it was written, the tables used, the purpose of the code, and any modifications made since it was originally written. Such commnets are refered to as "header comments".

Lastly, in-line comments can be added within or at the end of line of SQL code. These can be used to temporarily exclude a column from being returned in the resulting output, or to add an explanation immediately following a line of code which may not be self explanatory and to add additional context.

Here is an example of in-line comments, using both of the above mentioned methods.

```sql {linenos=table}
SELECT last_name/*, first_name */
FROM li_wedding
WHERE (attending = 1) AND (diet = "vegetarian"); -- List confirmed wedding attendees who are vegitarian
```

## Best Practices for Writing SQL Queries

Throughout your career, you will become more and more acquainted with the best practices around writing SQL queries. For this chapter, before you run a query, ask yourself the following questions:

1. How many results do you really need to return? If a table contains 10,000 rows, do you actually need to see all of those rows?
1. What columns of data do you really need for each result set? If a table contains ten columns, do you need to see the values of all of those columns or can you reduce the scope of the result set?
1. Would pattern matching be effective in the current situation or should you be more precise? Pattern matching will return a larger number of results so before you use it, ask yourself whether or not it is appropriate to use.

The larger the result set, the slower your query will run. By asking yourself these questions to start, you will find that your queries will take less time!

## Check Your Understanding

{{% notice green Question %}}

What does the following query do?

```sql
SELECT EventID
FROM EventsMaster
WHERE (Month=07);
```

1. Returns the event id from a table called `EventsMaster` for all events in 7 months of the year.
1. Returns the event id for all events in a table called `EventsMaster` for the month of July.
1. Returns the event id for all events in a table called `EventsMaster` for the month of June.

{{% /notice %}}

<!-- answer is 2 -->
