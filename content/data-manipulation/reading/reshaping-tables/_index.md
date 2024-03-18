+++
title = "Reshaping Tables"
date = 2024-03-12T15:04:03-05:00
draft = false
weight = 3
+++

As you continue to answer questions about your data during the exploration and cleaning stages, you may want to reformat or *reshape* your tabular data. Below we will cover some common functions used when reshaping your dataset so that you can not only visualize it differently but also gather data related to a specific question you have.

## Sorting Values

The `.sort_values()` function allows you to reshape data to your specific use case. The below parameters are some of the more common:
1. `by`: Name of column(s) or list of column(s) to sort by
1. `axis`: Which axis to perform the operations on (`0` or `1`)
1. `ascending`: Sort the data in ascending or descending order

{{% notice blue Note "rocket" %}}
The above parameters are not the only ones available when using the `.sort_values()` function. If you would like a more extensive list you can view them here: [pandas docs](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.sort_values.html)
{{% /notice %}}

### Syntax

```python
data.sort_values(by="column_name", axis=1, ascending=True)
```

{{% notice blue Example %}}
```python
import pandas as pd

data = pd.read_csv("titanic.csv")

data.sort_values(by="embark_town").head()
```

![Sort the titanic dataset by the embark_town column](pictures/sort_by-embark-town.png?classes=border)
{{% /notice %}}

## Pivot Tables

Pivot tables are often used to provide summary statistics through aggregate functions while reorganizing your data.

Below are some of the commonly used parameters:
1. `values`: column(s) to aggregate
1. `aggfun`: aggregate function to apply
1. `index`: 

### Syntax

```python
data.pivot_table(values="column-name", aggfunc="", index="")
```

{{% notice blue Example "rocket" %}}
```python
import pandas as pd

pivot_table = data.pivot_table(values='age', aggfunc='mean', index='alive')
print(pivot_table)
```

**Output**

![pivot table created from the "age" and "alive" columns of the titanic dataset](pictures/age-alive-pivot-table.png?classes=border)

The above code accomplishes the following:
1. Imports pandas
1. Creates a pivot table using the `age` column with the `alive` column as the index, applying the `mean` function to agggregate the data.
1. The output displays the average age of people alive, and not alive.
{{% /notice %}}

## Wide to Long

## Melt