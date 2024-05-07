+++
title = "Databases with pandas"
date = 2024-04-17T10:00:24-05:00
draft = false
weight = 2
+++

In addition to all the great things pandas is capable of, the library also makes it possible to inject data stored elsewhere into a pandas DataFrame or Series. This lesson will walk through the process of creating a pandas DataFrame from an existing table within a sqlite datastore.

This lesson will also utilize SQLite3 as the database used to demonstrate how to interact with a database using a separate tool or library (pandas). Since we have already covered how to manipulate data with pandas in previous lessons, we will instead focus on the following:
1. Reading data from the database
1. Storing the data inside of a pandas DataFrame
1. Creating a new table inside of the database
    - Adding the DataFrame data into the new table

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

After exploring, cleaning, or manipulating data with pandas, you can add that data back into your database. In the scenario below we will add a new movie to an existing DataFrame and then store the DataFrame inside of a new table within the sqlite database.

{{% notice blue Example "rocket" %}}
We will first start by adding a row to our existing DataFrame:

```python
new_movie = pd.DataFrame([{'title':'Dune', 'genre':'Science Fiction', 'release':2021, 'rt_score': 83}])
df = pd.concat([df, new_movie], ignore_index=True)
```

It was not necessary to update our DataFrame to add a new table to the database, but it will help visually when reading data to show that it was populated into a new table correctly.

```python {linenos=table}
# Inject dataframe into database as new table, if the table exists - replace it
df.to_sql('df', movies_db, if_exists="replace")
# Execute command to create a new table called new_movie_table with the new_movie dataframe data
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
