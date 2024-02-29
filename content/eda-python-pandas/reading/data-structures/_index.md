+++
title = "pandas Data Structures"
date = 2024-02-29T09:18:56-06:00
draft = false
weight = 1
+++

The `pandas` library comes with two types of classes to handle data:

1. **Series**: A `pandas` Series is a one-dimensional array. A good way to visualize this is to think about one column within a spreadsheet.
1. **DataFrame**: A DataFrame is a two-dimensional table. Similar to the above example, a DataFrame can be visualized as the rows *and* columns within a spreadsheet.

## Series

A `series` is capable of holding any type of data (strings, objects, integers, floats, booleans, number, and so on). All values within a `series` are associated with a labeled index. The labaled index can be either label or integer-based.

{{% notice blue Note "rocket" %}}
While a `Series` is capable of holding any type of data it usually only holds one type.
{{% /notice %}}

Let's look into some examples below.

{{% notice blue Example "rocket" %}}
```python
import pandas as pd

movies = pd.Series(["Interstellar", "Pride and Prejudice", "Inception", "Barbie"], index=['1', '2', '3', '4'])
print(movies)
```

**Output**

```console {linenos=table}
1 Interstellar
2 Prider and Prejudice
3 Inception
4 Barbie
```
{{% /notice %}}

Alternatively you could change the index value above from an integer to a label like `'Christopher Nolan'`:

```python
movies = pd.Series(["Interstellar", "Pride and Prejudice", "Inception", "Barbie"], index=['Christopher Nolan', '2', '3', '4'])
print(movies)
```

**Output**

```console {linenos=table}
Christopher Nolan Interstellar
2 Pride and Prejudice
3 Inception
4 Barbie
```

This represents the ability to have a label-based index or integer-based index.

## DataFrame

Similar to a spreadsheet a `DataFrame` has an index for each row and a name for each column. a `DataFrame` is capable of holding different types of data (strings, objects, integers, floats, booleans, number, and so on).

A `DataFrame` at its core is a collection of Series. pandas also allows for the creation of a `DataFrame` by combining one or more series together.

Let's take a look at some examples below.

{{% notice blue Example "rocket" %}}
```python
movies = {
    'Name': ["Interstellar", "Pride and Prejudice", "Inception", "Barbie"],
    'Release': [2014, 2005, 2010, 2003]
}

movie_df = pd.DataFrame(movies, index=['Christopher Nolan', 'Joe Wright', 'Christopher Nolan', 'Greta Gerwig'])

print(movie_df)
```

**Output**

```console
                        Name                Release
Christopher Nolan       Interstellar        2014
Joe Wright              Pride and Prejudice 2005
Christopher Nolan       Inception           2010
Greta Gerwig            Barbie              2003
```
{{% /notice %}}
