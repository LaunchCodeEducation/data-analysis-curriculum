+++
title = "Databases with Python"
date = 2024-04-17T10:00:24-05:00
draft = false
weight = 1
+++

Working within a database command line interface can oftentimes be cumbersome and difficult to execute multiple commands. Because of this, analysts oftentimes prefer to use a user-friendly graphical user interface (GUI) or leverage programming languages like Python and supported libraries to interact with them. We will use Python and the **sqlite3** library to complete the following:
1. Create a new sqlite database
1. Add a table
1. Perform CRUD operations on the table

While you can accomplish more than just the above using python and pandas, like performing joins, it is not always best practice. As it relates to joins, database engines are built and optimized to perform joins extremely well. It is always important to know what you will be doing with your data before acting.

{{% notice blue Note "rocket" %}}
The examples below are also available in the `data-analysis-projects/databases-python-pandas/python-db-walkthrough.ipynb` file.
{{% /notice %}}

## sqlite3 with Python

[sqlite3](https://docs.python.org/3/library/sqlite3.html) works in conjunction with python by allowing the user to establish a connection to a file located on your machine. You can then reference the connection variable to begin executing sql commands.

The basic syntax is as follows:

```python
import sqlite3

# If the 'Movies.db` database does not already exist, sqlite3 will create one!
movies_db = sqlite3.connect('Movies.db') # connect to database
```

{{% notice blue Note "rocket" %}}
If we were to print the `connection_variable` we would see the following output:

```python
<sqlite3.Connection object at 0x7334db1d3940> # the 0x7334db1d3940 portion will vary
```

This shows that a `sqlite3.Connection` object was created and can now be referenced using the `movies_db` variable.
{{% /notice %}}

## Cursor Objects

Now that we have established a connection to the database we need a way to execute commands. The **cursor object** is a database cursor which allows us to do so.

We can create a new cursor object by referencing the cursor function and storing it within a variable:

```python
# variable named "cur" that references the connection object:
cur = movies_db.cursor()
```

The basic syntax for executing a command with the cursor object is as follows:

```python
cur.execute("SQL statement")
```

## Creating a table

```python
cur.execute("CREATE TABLE table_name (column DATA TYPE, column DATA TYPE, etc..)")
```

{{% notice blue Note "rocket" %}}
You can find a list of SQLite data types here: [Data Types in SQLite](https://sqlite.org/datatype3.html).
{{% /notice %}}

### Insert Table Values

```python
cur.execute("INSERT INTO table_name ('value-one', 'value-two', etc..)")
```

### Reading Data

There are a couple strategies that you can use to read data from your database. Since the cursor object is an iterator in and of itself, you can iterate over the cursor object to fetch data.

{{% notice blue Example "rocket" %}}

```python
# For loop to iterate over cursor object
for row in cur.execute("SELECT column FROM table_name")
    print(row)
```

The above for loop will return all rows within the specified column inside of the `SELECT` statement. You could also pass the `*` flag to return all values from all rows within the database.
{{% /notice %}}

You can also use the `fetchall()` function to read data from the database like so:

```python
cur.execute("SELECT * FROM table_name").fetchall()
```

### Updating Data

When running dynamic queries against a database there are some risks to be made aware of, specifically SQL injection attacks or SQLi attacks. While we have multiple strategies to avoid SQLi attacks, the one we will focus on in this class is using **parameterized queries**.

Parameterized queries allow you to inject a placeholder (`?`) into your SQL statement and pass in the desired value as a parameter.

{{% notice blue Example "rocket" %}}
```python
# Desired value
update_release_year = 1997 # Value that needs to be updated
movie_to_update = 'Good Will Hunting'
# Execute an UPDATE statement using the ? placeholder, passing in the update variables as a list literal
cur.execute("UPDATE movies SET release = ? WHERE title = ?", [update_release_year, movie_to_update])
```
{{% /notice %}}

### Deleting Data

Similar to updating data we will want to use parameterized queries as best and safe practice!

{{% notice blue Example "rocket" %}}
```python
movie_to_delete = 'Inception' # Too many sci fi movies!
# Execute a DELETE statement using the ? placeholder, passing in the variable as a list literal
cur.execute("DELETE FROM movies WHERE title = ?", [movie_to_delete])
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
What type of database is SQLite?

<!-- Solution: disk-based database, does not require its own server. Stored isnide of a file on your machine -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
What is the primary reason for creating a cursor object?

<!-- Solution: Executing commands inside of the datastore -->
{{% /notice %}}