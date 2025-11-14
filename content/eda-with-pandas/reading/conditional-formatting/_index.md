+++
title = "Conditional Formatting"
date = 2024-02-29T09:18:56-06:00
draft = false
weight = 5
+++

When exploring data, using pandas you can also apply conditional formatting similar to how you did using spreadsheets. Say, for instance, you only want to display data related to a specific city, state, movie genre, or name, you can do so!

We will begin by identifying rows based on a condition using one column of data.

{{% notice blue Example "rocket" %}}
```python
# import pandas
import pandas as pd

# Create a pandas DataFrame using a dictionary
movies = {'Name': ["Interstellar", "Pride and Prejudice", "Inception", "Barbie"],'Release': [2014, 2005, 2010, 2003], 'Genre': ["Science Fiction", "Novel", "Science Fiction", "Comedy"]}

movies_dataframe = pd.DataFrame(movies)

# Select only movies from the Science Fiction genre
science_fiction = movies_dataframe[movies_dataframe['Genre'] == "Science Fiction"]

# Print the data
print(science_fiction)
```

**Output**

```console
           Name  Release            Genre
0  Interstellar     2014  Science Fiction
2     Inception     2010  Science Fiction
```
{{% /notice %}}

### Multiple Conditions

In the below example we will apply conditional formatting based on the data in multiple columns. This is very useful when you are trying to identify a particular set of data so that you can properly analyze, clean, and prepare for further analysis like visualization!

{{% notice blue Example "rocket" %}}
```python
# import pandas
import pandas as pd

# Create a pandas DataFrame using a dictionary
movies = {'Name': ["Interstellar", "Pride and Prejudice", "Inception", "Barbie"],'Release': [2014, 2005, 2010, 2003], 'Genre': ["Science Fiction", "Novel", "Science Fiction", "Comedy"]}

movies_dataframe = pd.DataFrame(movies)

# Select only movies from the Science Fiction genre
science_fiction = movies_dataframe[(movies_dataframe['Genre'] == "Science Fiction") & (movies_dataframe['Release'] <= 2010)]

# Print the data
print(science_fiction)
```

**Output**

```console
        Name  Release            Genre
2  Inception     2010  Science Fiction
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
True or False: Conditional formatting can be applied using data from multiple columns.
<!-- Solution: True -->
{{% /notice %}}