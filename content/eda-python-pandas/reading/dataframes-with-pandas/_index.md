+++
title = "pandas DataFrames"
date = 2024-02-29T09:18:56-06:00
draft = false
weight = 1
+++

Similar to a spreadsheet a `DataFrame` has an index for each row and a name for each column. a `DataFrame` is capable of holding different types of data (strings, objects, integers, floats, booleans, number, and so on).

A `DataFrame` at its core is a collection of Series. pandas also allows for the creation of a `DataFrame` by combining one or more series together. A `pandas DataFrame` is similar to a Python dictionary. The column names are like keys and the values are the data for that column.

![A diagram of a pandas dataframe](pictures/pandas-dataframe.png?classes=border)

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

### Creating a DataFrame from Series

In the following example we will create a DataFrame from two Series using pandas and the built-in `.concat()` function.

{{% notice blue Example "rocket" %}}
```python
movies = pd.Series(["Interstellar", "Pride and Prejudice", "Inception", "Barbie"], index=['1', '2', '3', '4'], name = 'movies')
```

```python
genres = pd.Series(["Science Fiction", "Novel", "Science Fiction", "Comedy"], index=['1', '2', '3', '4'], name='genres')
```
Using the two series above we can concatenate the two together in order to create a DataFrame.

``` python
df = pd.concat([movies, genres], axis=1) # axis 1 specifies that the operations will be performed down each column
```

**Output**

```console
                movies           genres
1         Interstellar  Science Fiction
2  Pride and Prejudice            Novel
3            Inception  Science Fiction
4               Barbie           Comedy
```
{{% /notice %}}

{{% notice blue Note "rocket" %}}
the `axis` option specifies whether the data will be joined or combined along the *row* or *column*. The table below provides an overview of the `axis` option.

| Axis | Represents | Use Case |
|---|---|---|---|
| 0 | **Row** | Operations performed **across rows** |
| 1 | **Column** | Operations performed **down each column** |
{{% /notice %}}