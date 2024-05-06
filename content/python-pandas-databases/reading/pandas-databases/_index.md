+++
title = "Pandas with Databases"
date = 2024-04-17T10:00:24-05:00
draft = false
weight = 2
+++

In the previous lesson we talked about ease of use when manipulating data stored within a database. Pandas makes working with data much easier than executing numerous queries within the database itself.

<!-- TODO: Reassess this note -->
{{% notice blue Note "rocket" %}}
Just because pandas makes working with data easier for the user than working within the database does not make it the right tool for every job. 

Some analysts may prefer to work with a different tool and that is okay!
{{% /notice %}}

This lesson will also utilize SQLite3 as the database used to access and manipulate data. Since we have already covered how to manipulate data with pandas in previous lessons we will instead focus on reading data, and repopulating the database with an updated dataframe.

{{% notice blue Note "rocket" %}}
The following examples can be found within the `data-analysis-projects/databases-python-pandas/pandas-db-walkthrough.ipynb` file.
{{% /notice %}}

## Create a DataFrame

{{% notice blue Example "rocket" %}}
```python
import sqlite3
import pandas as pd

# Create sqlite connection to Movies.db file
movies_db = sqlite3.connect('Movies.db')

# Use the pandas read_sql_query function to return a pandas DataFrame
df = pd.read_sql_query('Select * from movies;', movies_db)

# Use .head() function to return first five rows (there are only 5 rows currently)
df.head()
```
{{% /notice %}}

## Create New Table from DataFrame

{{% notice blue Example "rocket" %}}
We will first start by adding a row to our existing DataFrame:

```python
new_movie = pd.DataFrame([{'title':'Dune', 'genre':'Science Fiction', 'release':2021, 'rt_score': 83}])
df = pd.concat([df, new_movie], ignore_index=True)
```

It was not necessary to update our DataFrame to add a new table to the database, but it will help visually when reading data to show that we are pulling a new table and did not somehow duplicate an existing table.

```python {linenos=table}
# Inject new dataframe into database as new table
df.to_sql('new_movie', movies_db, if_exists="replace")
# Execute command against database
movies_db.execute(
    """
    create table new_movie_table as
    select * from new_movie
    """
)
```

```python
# Read data from newly created table, passing in existing movies_db connection as parameter
new_movies_df = pd.read_sql_query('Select * from new_movie_table;', movies_db)
# Read first 6 rows
new_movies_df.head(6)
```
{{% /notice %}}