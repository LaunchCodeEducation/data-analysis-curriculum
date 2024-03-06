+++
title = "pandas DataFrames"
date = 2024-02-29T09:18:56-06:00
draft = false
weight = 3
+++

A `pandas` **DataFrame** is the second type of class that is capable of handling data.

Similar to a spreadsheet, a `DataFrame` has an index for each row and a name for each column. a `DataFrame` is capable of holding different types of data (strings, objects, integers, floats, booleans, numbers, and so on).

A `DataFrame` at its core is a colelction of `Series`. Similar to a `Series` there are multiple ways that a `DataFrame` can be created:
1. Using a multi-dimensional list, dictionary, or tuple
1. Combining or joining multiple `Series` together
1. From a pre-existing CSV file

{{% notice blue Note "rocket" %}}
The examples above are not the only options you have for creating a `DataFrame` but they are the ones we will focus on in this section.
{{% /notice %}}

A `DataFrame` at its core is a collection of Series.

Column values within a `DataFrame` are referred to as a `Series`. Below is an example of how multiple `Series` might be used to build a `DataFrame`

![diagram of how a pandas Series is used to build a dataframe](pictures/pandas-series.png?classes=border)

The image below provides another visual of the general `DataFrame` structure. A `DataFrame` is similar to a Python dictionary in that the column names are like keys and the values are the data for that column.

![A diagram of a pandas dataframe](pictures/pandas-dataframe.png?classes=border)

## Syntax

Let's dive in to some different ways you can create a `DataFrame`.

### Using a Multi-Dimensional List

```python {linenos=table}
# import pandas
import pandas as pd

# Create a pandas DataFrame by providing a list of lists
movie_list_of_lists = pd.DataFrame([["Interstellar", "Pride and Prejudice", "Inception", "Barbie"],["Marley & Me", "The Proposal", "The Guardian", "Bridesmaids"]])

# Create a pandas Series from a pre-existing list of lists
movies_dataframe_data = [["Interstellar", "Pride and Prejudice", "Inception", "Barbie"],["Marley & Me", "The Proposal", "The Guardian", "Bridesmaids"]]

dataframe_from_existing_list = pd.DataFrame(movies_dataframe_data)
```

The above code block accomplishes the following:
1. imports `pandas` as `pd`.
1. Creates a `pandas` `DataFrame` called `movie_list_of_lists` by providing a list of lists as a parameter into the `.DataFrame()` function..
1. Creates a `pandas` `DataFrame` called `dataframe_from_existing_list` by using the already existing list `movies_dataframe_data` and passing it in as a parameter to the `.DataFrame()` function.

{{% notice blue Note "rocket" %}}
One thing to note about lists when they are added into a `DataFrame` is that each list represents a *row* not a *column*.
{{% /notice %}}

### Using a Dictionary

```python {linenos=table}
# import pandas
import pandas as pd

# Create a pandas DataFrame by providing a dictionary
movie_dictionary_dataframe = pd.DataFrame(movies = {'Name': ["Interstellar", "Pride and Prejudice", "Inception", "Barbie"],'Release': [2014, 2005, 2010, 2003]})

# Create a pandas DataFrame from a pre-existing dictionary
movies = {'Name': ["Interstellar", "Pride and Prejudice", "Inception", "Barbie"],'Release': [2014, 2005, 2010, 2003]}

dataframe_from_movies_dictionary = pd.DataFrame(movies)
```

The above code block accomplishes the following:
1. imports `pandas` as `pd`.
1. Creates a `pandas` `DataFrame` called `movie_dictionary_dataframe` by providing a dictionary as a parameter to the `DataFrame` function.
1. Creates a `pandas` `DataFrame` called `dataframe_from_movies_dictionary` by using the already existing dictionary `movies` and passing it in as a parameter to the `.DataFrame()` function.

### Using a Tuple

```python {linenos=table}
# import pandas
import pandas as pd

# Create a pandas DataFrame by providing a tuple
example_tuple = pd.DataFrame(("Interstellar", "Pride and Prejudice", "Inception", "Barbie"))

# Create a pandas DataFrame by providing a pre-existing tuple
pre_existing_tuple = ("Interstellar", "Pride and Prejudice", "Inception", "Barbie")

dataframe_from_existing_tuple = pd.DataFrame(pre_existing_tuple)
```

The above code block accomplishes the following:
1. imports `pandas` as `pd`.
1. Creates a `pandas` `DataFrame` called `example_tuple` by providing a tuple with values.
1. Creates a `pandas` `DataFrame` called `series_from_existing_tuple` by using an already existing tuple `pre_existing_tuple` and passing it in as a parameter to the `.DataFrame()` function.

<!-- ### Creating a DataFrame from Series

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
{{% /notice %}} -->