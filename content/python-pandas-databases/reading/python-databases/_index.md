+++
title = "Databases with Python"
date = 2024-04-17T10:00:24-05:00
draft = false
weight = 1
+++

Working within a database command line interface can oftentimes make it cumbersome and difficult to execute multiple commands. Because of this, analysts usually prefer to use a user-friendly graphical user interface (GUI) or leverage programming languages like Python and supported libraries to interact with them. We will use Python and the **sqlite3** library to complete the following:
1. Create a new SQLite database
1. Add a table
1. Perform CRUD operations on the table

While you can accomplish more than just the above using python and pandas, like performing joins, it is not always best practice. As it relates to joins, database engines are built and optimized to perform joins extremely well. It is always important to know what you will be doing with your data before acting.

## When to Use sqlite3 vs pandas

Understanding when to use each tool will help you write more efficient code:

**Use sqlite3 directly when:**
- Performing complex SQL operations (joins, aggregations, subqueries)
- Working with large datasets that don't fit in memory
- You need precise control over transactions and commits
- Creating or modifying database schema (tables, indexes, constraints)
- The data will remain in the database without further analysis

**Use pandas when:**
- You need to perform complex data analysis or visualization
- Applying statistical operations or transformations
- Cleaning and reshaping data
- Integrating database data with other data sources
- The dataset is small to medium-sized and fits in memory

**Best Practice:** Use sqlite3 to filter and join data in the database, then load the results into pandas for analysis. This leverages the strengths of both tools!

{{% notice red Warning "rocket" %}}
We have created a new repo for Class 19 and 20 exercises and studios. 
Please fork this repo to your Github account, and then clone it to your local device

[Class 19 and 20 Exercise Studio Repo](https://github.com/LaunchCodeEducation/data-analysis-projects-class-19-and-20)

The examples below can be found at `data-analysis-projects-class-19-and-20/class-20/python-db-walkthrough.ipynb`
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

## Using Context Managers

A better practice for managing database connections is to use Python's context manager pattern with the `with` statement. This ensures that connections are properly closed even if an error occurs:

{{% notice blue Example "rocket" %}}
```python
import sqlite3

# Using a context manager - connection closes automatically
with sqlite3.connect('Movies.db') as movies_db:
    cur = movies_db.cursor()
    cur.execute("SELECT * FROM movies")
    results = cur.fetchall()
    print(results)
# Connection is automatically closed here
```

This pattern is especially useful when performing multiple operations, as it guarantees proper cleanup.
{{% /notice %}}

## Creating a table

```python
cur.execute("CREATE TABLE table_name (column DATA TYPE, column DATA TYPE, etc..)")
```

{{% notice blue Note "rocket" %}}
You can find a list of SQLite data types here: [Data Types in SQLite](https://sqlite.org/datatype3.html).
{{% /notice %}}

### Insert Table Values

```python
cur.execute("INSERT INTO table_name (column1, column2) VALUES ('value-one', 'value-two')")
# Commit the changes to save them to the database
movies_db.commit()
```

### Reading Data

There are a couple strategies that you can use to read data from your database. Since the cursor object is an iterator in and of itself, you can iterate over the cursor object to fetch data.

{{% notice blue Example "rocket" %}}

```python
# For loop to iterate over cursor object
for row in cur.execute("SELECT column FROM table_name"):
    print(row)
```

The above for loop will return all rows within the specified column inside of the `SELECT` statement. You could also pass the `*` flag to return all values from all rows within the database.
{{% /notice %}}

You can also use the `fetchall()` function to read data from the database like so:

```python
cur.execute("SELECT * FROM table_name").fetchall()
```

### Updating Data

When running dynamic queries against a database there are some risks to be aware of, specifically SQL injection attacks or SQLi attacks. While we have multiple strategies to avoid SQLi attacks, the one we will focus on in this class is using **parameterized queries**.

Parameterized queries allow you to inject a placeholder (`?`) into your SQL statement and pass in the desired value as a parameter.

{{% notice blue Example "rocket" %}}
```python
# Desired value
update_release_year = 1997 # Value that needs to be updated
movie_to_update = 'Good Will Hunting'
# Execute an UPDATE statement using the ? placeholder, passing in the update variables as a list literal
cur.execute("UPDATE movies SET release = ? WHERE title = ?", [update_release_year, movie_to_update])
# Commit the changes to save them to the database
movies_db.commit()
```
{{% /notice %}}

### Deleting Data

We should also use parameterized queries to safely delete data.
Using parameterized queries to update and delete data is a best practice!

{{% notice blue Example "rocket" %}}
```python
movie_to_delete = 'Inception' # Too many sci fi movies!
# Execute a DELETE statement using the ? placeholder, passing in the variable as a list literal
cur.execute("DELETE FROM movies WHERE title = ?", [movie_to_delete])
# Commit the changes to save them to the database
movies_db.commit()
```
{{% /notice %}}

## Error Handling

When working with databases, it's important to handle potential errors gracefully. Common errors include trying to access tables that don't exist, constraint violations, or connection issues.

{{% notice blue Example "rocket" %}}
```python
import sqlite3

try:
    with sqlite3.connect('Movies.db') as movies_db:
        cur = movies_db.cursor()

        # Attempt to insert a duplicate record or violate a constraint
        cur.execute("INSERT INTO movies (title, genre, release) VALUES (?, ?, ?)",
                   ['Inception', 'Sci-Fi', 2010])
        movies_db.commit()

except sqlite3.IntegrityError as e:
    print(f"Database integrity error: {e}")

except sqlite3.OperationalError as e:
    print(f"Database operational error (table may not exist): {e}")

except sqlite3.Error as e:
    print(f"Database error: {e}")

except Exception as e:
    print(f"Unexpected error: {e}")
```

Using try-except blocks helps your program handle errors without crashing and provides useful feedback.
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