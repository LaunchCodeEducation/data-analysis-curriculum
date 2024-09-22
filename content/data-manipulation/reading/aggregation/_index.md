+++
title = "Aggregation"
date = 2024-03-12T15:04:03-05:00
draft = false
weight = 1
+++

{{% notice blue Note "rocket" %}}
This reading, and following readings, will provide examples from the `titanic.csv` dataset file that will also be used in the exercise portion of this chapter.
{{% /notice %}}

## Groupby

The `.groupby()` function groups data together from one or more columns. As we group the data together, it forms a new **GroupBy** object. The offical [pandas documenation](https://pandas.pydata.org/pandas-docs/stable/user_guide/groupby.html) states that a "group by" accomplshes the following:
1. Splitting: Split the data based on the criteria provided.
1. Applying: Provide an applicable function to the groups that were split.
1. Combining: Combine the results from the function into a new data structure.

### Syntax

Syntax for the `.groupby()` method when providing a single column as a parameter is as follows:

```python
grouping_variable = your_data.groupby("column-name")
```

{{% notice blue Example "rocket" %}}
Let's take things a step further and aggregate the data within the grouped column name using the `.sum()` function through method chaining:

```python
grouping_variable = your_data.groupby(["column_name"]).sum()
```

The above code will group the dataset by 'column_name', and will then return the sum of all values within each column grouped by each unique value in the 'column_name' column
{{% /notice %}}

The `.groupby()` method can take multiple columns as a parameter upon creation, but it is best practice to only provide as many columns as needed for your analysis. As you increase the amount of grouped columns, you are also increasing the amount of compute power and memory needed, which can lead to performance issues.

In order to group multiple columns you can pass a list of column names as a parameter to the `.groupby` method.

```python
grouping_variable = your_data.groupby(["column_one", "column_two", "etc.."])
```

{{% notice blue Example "rocket" %}}
Applying an aggregate function to multipled grouped columns can also be accomplished with method chaining. The following image uses columns from the titanic dataset as an example.

![Creating a new groupby object from the columns "embark_town" and "alone" and applying the sum aggregate function](pictures/grouped-titanic.png?classes=border)

The image below displays the output when only applying the `groupby()` method to only the `embark_town` column.

![Applying a groupby method to only the "embark_town" column within the titanic.csv dataset to view the output](pictures/groupby-embark-town.png?classes=border)

The key thing to note here is that when grouping multiple column(s) together it will provide you a dataset that is specific to that grouping of data. When the`embark_town` column was grouped with the `alone` column, the result is a dataset that provides an aggregate of the entire dataset in relation to those two columns. When `embark_town` was grouped alone, it provided an aggregate of the entire dataset only as it relates to the `embark_town` column.
{{% /notice %}}

## Aggregate Methods

pandas provides a built-in aggregate method: `Data.aggregate()` or `Data.agg()` (both accomplish the same thing, `agg()` is short for `aggregate()`). The benefit of using the `.aggregate()` function is that it allows you to pass aggregate functions as a list.


{{% notice blue Example "rocket" %}}
```python
data.agg(['mean', 'median', 'mode'])
```
{{% /notice %}}

### Aggregation Using a Dictionary

pandas also allows the ability to provide a dictionary with columns as a key and aggregate functions as an associated value.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
aggregate_dictionary_example = {
    "embark_town": ["count"], 
    "age": ["count", "median"]
}

dictionary_aggregate = data.agg(aggregate_dictionary_example)
```

This dictionary object has now become a tempate for the aggregations we want to preform. However, on it's own, it does nothing. Once passed to the agg() method, it will pick out the specific location of data we want to examine. Making a subset table. 
{{% /notice %}}

## Groupby and Multiple Aggregations

A common strategy used when applying multiple aggregations to your group or dataset is to hold them within a variable. The advantage of this being, you will not have to provide the list of functions you need as parameters each and every time.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
aggregate_functions = ["mean", "median", "mode"]

grouping_variable = your_data.groupby(["column_one", "column_two", "etc.."])

grouping_variable.agg(aggregate_functions)
```
{{% /notice %}}