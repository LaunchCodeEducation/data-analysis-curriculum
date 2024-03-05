+++
title = "pandas Series"
date = 2024-02-29T09:18:56-06:00
draft = false
weight = 2
+++

The `pandas` library comes with two types of classes to handle data. The first that we will learn about is the **pandas Series**. A `pandas Series` is a one-dimensional array. A good way to visualize this is to think about one column within a spreadsheet.

A `pandas Series` is capable of holding any type of data (strings, objects, integers, floats, booleans, number, and so on). All values within a `Series` are associated with a labeled index. The labeled index can be either label or integer-based. An example of a label-based index would be `groceries` or `movies` while an integer-based index would be numeric (`1`, `2`, `3`, `etc..`).

{{% notice blue Note "rocket" %}}
While a `Series` is capable of holding any type of data it usually only holds one.
{{% /notice %}}

## Syntax

Let's take a look at the syntax for creating a `Series` using lists, dictionaries, and tuples.

### Using a List

```python {linenos=table}
# import pandas
import pandas as pd

# Create a pandas Series by providing a list
example_list = pd.Series(["value-1", "value-2", "value-3", "value-4"])

# Create a pandas Series from a pre-existing list of values
pre_existing_list = ["value-1", "value-2", "value-3", "value-4"]

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
example_dictionary = pd.Series({'i-1': value-1, 'i-2': value-2, 'i-3': value-3, 'i-4': value-4})

# Create a pandas Series from a pre-existing dictionary, the i represents the index of the dictionary
pre_existing_dictionary = {'i-1': value-1, 'i-2': value-2, 'i-3': value-3, 'i-4': value-4}

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

## Indexing

When creating a `pandas Series` you have the ability to add custom index values. If you do not add custom index values to a `Series` and none already exist it will default to a typical index range of `0, 1, 2, 3, 4, 5, etc..`.

In order to add custom index labels you can add in an additional parameter when creating the `Series`:

{{% notice blue Example "rocket" %}}
```python
custom_index_labels = pd.Series(["value-1", "value-2", "value-3", "value-4"], index = ["custom-value", "..", "..", ".."])
```
{{% /notice %}}

{{% notice green Tip "rocket" %}}
You can also store index labels inside of a variable as shown below:

```python
custom_index_variable = ["custom-value", "..", "..", ".."]

custom_index_labels = pd.Series(["value-1", "value-2", "value-3", "value-4"], index = custom_index_variable)
```
{{% /notice %}}