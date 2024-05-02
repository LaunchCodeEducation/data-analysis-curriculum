+++
title = "Databases with Python"
date = 2024-04-17T10:00:24-05:00
draft = false
weight = 1
+++

Working within a database command line interface can often times be cumbersome and difficult to replicate commands. Because of this, developers prefer to use a user-friendly graphical user interface (gui) or leverage programming languages like python and supported libraries to interact with them. We will use python and the `sqlite` library to complete the following:
1. Create a new sqlite database
1. Add a table
1. Populate the table
1. Perform CRUD operations on the table

## SQLite3 with Python

SQLite works in conjunction with python by allowing the user to establish a connection to the file-based datastore to store and reference the connection object through a variable.

The basic syntax is as follows:

```python
import sqlite3

# If the 'database.db` does not already exist, sqlite3 will create one!
connection_variable = sqlite3.connect('database.db')
```

{{% notice blue Note "rocket" %}}
If we were to print the `connection_variable` we would see the following output:

```python
<sqlite3.Connection object at 0x7334db1d3940> # the 0x7334db1d3940 portion will vary
```

This shows that a sqlite3.Connection object was created and can now be referenced using the `connection_variable`.
{{% /notice %}}

## Cursor Objects

Now that we have established a connection to the database we need a way to execute commands. The cursor object is a database cursor which allows us to do so.

We can create a new cursor object by referencing the cursor function and storing it within a variable:

```python
# variable named "cur" that references the connection object:
cur = connection_variable.cursor() 
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
You can find a list of SQLite data types here: [Data Types in SQLite](https://sqlite.org/datatype3.html)
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

The above for loop will return all rows within the specified column inside of the SELECT statement. You could also pass the * flag to return all values from all rows within the database.
{{% /notice %}}

You can also use the `fetchall()` function to read data from the database like so:

```python
cur.execute("SELECT * FROM table_name").fetchall()
```