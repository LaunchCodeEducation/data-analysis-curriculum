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

A `series` is capable of holding any type of data (strings, objects, integers, floats, booleans, number, and so on). All values within a `series` are associated with a labeled index. The labeled index can be either label or integer-based.

Column values within a `DataFrame` are called a `pandas Series`. Below is an example of how they may be used to build a `DataFrame`

![diagram of how a pandas Series is used to build a dataframe](pictures/pandas-series.png?classes=border)

{{% notice blue Note "rocket" %}}
While a `Series` is capable of holding any type of data it usually only holds one.
{{% /notice %}}

Before we dive into examples of creating a `Series` let's look at the general syntax:

```python
series_name = pd.series(data="", index=['', '', 'etc..'])
```

### Series examples

Now let's look into some examples below.

{{% notice blue Example "rocket" %}}
```python
import pandas as pd

movies = pd.Series(["Interstellar", "Pride and Prejudice", "Inception", "Barbie"], index=['1', '2', '3', '4'])
print(movies)
```

**Output**

```console {linenos=table}
1 Interstellar
2 Pride and Prejudice
3 Inception
4 Barbie
```
{{% /notice %}}

Alternatively you could change the index value above from an integer to a label like `'Christopher Nolan'`:

{{% notice blue Example "rocket" %}}
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

This represents the ability to have a label-based index *or* integer-based index.
{{% /notice %}}