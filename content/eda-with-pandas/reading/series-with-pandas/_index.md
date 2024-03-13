+++
title = "pandas Series"
date = 2024-02-29T09:18:56-06:00
draft = false
weight = 2
+++

The `pandas` library comes with two types of classes to handle data. The first that we will learn about is the **pandas Series**. A `pandas Series` can be visualized as an individual column within a spreadsheet. The column typically has a name and an index for each row associated with that column.

A `pandas Series` can hold any data type and all values within a `Series` are associated with a labeled index. The labeled index can be either label or integer-based. An example of a label-based index would be `groceries` or `movies` while an integer-based index would be numeric (`1`, `2`, `3`, `etc..`).

{{% notice blue Note "rocket" %}}
While a `Series` is capable of holding any type of data it usually only holds one.
{{% /notice %}}

{{% notice blue Note "rocket" %}}
If you would like to change the code within the blocks of code below to view different outputs and work with the code on your own, you can access them by opening up `data-analysis-projects/eda-with-pandas/reading-examples` in Jupyter Notebook for this section and following sections!
{{% /notice %}}

## Creating a Series
Let's take a look at the syntax for creating a `Series` using lists, dictionaries, and tuples.

### Using a List

```python {linenos=table}
# import pandas
import pandas as pd

# Create a pandas Series by providing a list
example_list = pd.Series(["apple", "banana", "avocado", "honey dew"])

# Create a pandas Series from a pre-existing list of values
pre_existing_list = ["apple", "banana", "avocado", "honey dew"]

series_from_existing_list = pd.Series(pre_existing_list)
```

The above code block accomplishes the following:
1. imports `pandas` as `pd`.
1. Creates a `pandas` `Series` called `example_list` by providing a list of values.
1. Creates a `pandas` `Series` called `series_from_existing_list` by using the already existing list `pre_existing_list` and passing it in as a parameter to the `.Series()` function.

### Using a Dictionary

```python {linenos=table}
# import pandas
import pandas as pd

# Create a pandas Series by providing a dictionary, the i represents the index of the dictionary
example_dictionary = pd.Series({'0': "apple", '1': "banana", '2': "avocado", '3': "honey dew"})

# Create a pandas Series from a pre-existing dictionary, the i represents the index of the dictionary
pre_existing_dictionary = {'0': "apple", '1': "banana", '2': "avocado", '3': "honey dew"}

series_from_existing_dictionary = pd.Series(pre_existing_dictionary)
```

The above code block accomplishes the following:
1. imports `pandas` as `pd`.
1. Creates a `pandas` `Series` called `example_dictionary` by providing a dictionary.
1. Creates a `pandas` `Series` called `series_from_existing_dictionary` by using the already existing dictionary `pre_existing_dictionary` and passing it in as a parameter to the `.Series()` function.

### Using a Tuple

```python {linenos=table}
# import pandas
import pandas as pd

# Create a pandas Series by providing a tuple
example_tuple = pd.Series(("Interstellar", "Pride and Prejudice", "Inception", "Barbie"))

# Create a pandas Series by providing a pre-existing tuple
pre_existing_tuple = ("Interstellar", "Pride and Prejudice", "Inception", "Barbie")

series_from_existing_tuple = pd.Series(pre_existing_tuple)
```

The above code block accomplishes the following:
1. imports `pandas` as `pd`.
1. Creates a `pandas` `Series` called `example_tuple` by providing a tuple with values.
1. Creates a `pandas` `Series` called `series_from_existing_tuple` by using an already existing tuple `pre_existing_tuple` and passing it in as a parameter to the `.Series()` function.

## Indexing and Naming

When creating a `pandas Series` you have the ability to add custom index labels and a name (sometimes also referred to as a label) for the column associated with the `Series`.  

If you do not add custom index labels to a `Series` and none already exist it will default to a typical index range of `0, 1, 2, 3, 4, 5, etc..`. In regards to column names, if you do not add a custom name to the column it will default to `none`.

{{% notice blue Example "rocket" %}}
In order to add custom index labels you can add in an additional parameter when creating the `Series`:

```python
custom_index_labels = pd.Series(["apple", "banana", "avocado", "honey dew"], index = ["red", "yellow", "green", "green"])
```
{{% /notice %}}

{{% notice blue Example "rocket" %}}
If you would like to add a customized column name you would also need to add in an additional parameter when creating the `Series`:

```python
custom_index_labels = pd.Series(["apple", "banana", "avocado", "honey dew"], index = ["red", "yellow", "green", "green"], name = "fruit")
```

You could also use the `.name()` function:

```python
custom_index_labels = pd.Series(["apple", "banana", "avocado", "honey dew"], index = ["red", "yellow", "green", "green"])

custom_index_labels.name = "fruit"
```
{{% /notice %}}

{{% notice green Tip "rocket" %}}
You can also store index labels inside of a variable as shown below:

```python
fruit_color = ["red", "yellow", "green", "green"]

custom_fruit_labels = pd.Series(["apple", "banana", "avocado", "honey dew"], index = fruit_color)
```
{{% /notice %}}

## Subsetting a Series

`pandas` allows you to use *slicing* to subset a `Series`. You can accomplish this using bracket notation and specifying an index range. Let's take a look at how we can do this using the dictionary created above as an example.

{{% notice blue Example %}}
```python {linenos=table}
# import pandas
import pandas as pd

# Create a pandas Series from a pre-existing dictionary, the i represents the index of the dictionary
fruit_data = {'0': "apple", '1': "banana", '2': "avocado", '3': "honey dew"}

# create a series from the fruit_data
fruit_series = pd.Series(fruit_data)

# Subset the existing series
subset_fruit = fruit_series[:2]

# Print the subset
print(subset_fruit)

# Subset Series to include elements from index 1 to 3
subset_fruit_twice = fruit_series[1:4]
# Print the series
print("Subset elements from index 1 to 3")
print(subset_fruit_twice)
```

**Output**

```console
0     apple
1    banana

Subset elements from index 1 to 3
1       banana
2      avocado
3    honey dew
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
What does index-labeling default to if none are provided?

<!-- Solution: Basic indexing: 0, 1, 2, 3, 4 -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
What type of data is a `pandas Series` capable of holidng?

<!-- Solution: Any type -->
{{% /notice %}}
