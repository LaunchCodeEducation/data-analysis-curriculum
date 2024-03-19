+++
title = "Recoding Data"
date = 2024-03-12T15:04:03-05:00
draft = false
weight = 2
+++

## Creating New Columns

As questions arrise during your data exploring and cleaning, you might want to test them out. In this instance, we want to make sure the values we want to manipulate remain untouched. One thing we can do is to add a new column that will contain our manipulations.

{{% notice blue Example "rocket" %}}
```python
import pandas as pd

data["survived_reformatted"] = data["survived"].replace({0 : False, 1: True})
```

The above code accomplishes the following:
1. Imports pandas
1. Creates a new column called `survived_reformatted` from the `survived` column after replacing all `0` and `1` integers with either `False`, or `True`.

Viewing the output of the dataframe you are able to see that a new `column` called `survived_reformatted` was created:

![Displaying the output of our dataframe using the data.head() function](pictures/survived-reformatted.png?classes=border)
{{% /notice %}}

## Replacing Values

Replacing values within a column to be more data friendly is a common practice. In particular, replacing strings of data to bools, where a "yes" or "no" would become `True` or `False`. We can accomplish this by using the `.replace` function.

The following example simply replaces the data that exists within the column, manipulating it directly as it is, without creating a new column from the manipulation itself.

{{% notice blue Example "rocket" %}}
Replace the "0" and "1" integer values within the `survived` column of the titanic dataset to `True` or `False` by passing in a dictionary as an argument into the `to_replace`.

```python
import pandas as pd

data["survived"] = data["survived"].replace(to_replace={0: False, 1: True})
```
{{% /notice %}}

## Using Functions to Manipulate Data

Creating a function to aggregate data or create new columns is another common practice used when analyzing data. Pandas utilizes the `.apply()` method to execute a function on a pandas Series or DataFrame.

{{% notice blue Example "rocket" %}}
SUppose you wanted to know how many survivors under the age of 20 are still alive from the titanic dataset:

```python
import pandas as pd

data = pd.read_csv("titanic.csv")

def under_age_21_survivors(data):
    age = data['age']
    alive = data['alive']

    if age <= 20 and alive == "yes":
        return True
    else:
        return False

data["under_21_survivors"] = data.apply(under_age_21_survivors, axis=1)
print(data)
```

**Output**

![pandas function that applies conditional formatting to a dataframe checking if survivors under the age of 21 are still alive](pictures/under-age-21-survivors.png?classes=border)
{{% /notice %}}

## Summary

When recoding your data there are some things you should think about:
1. Does the original data need to remain in-tact?
1. What data tyes should be replaced with new values, and what type of data should the new value be?
1. Would a function be useful for repetitive tasks and manipulation?