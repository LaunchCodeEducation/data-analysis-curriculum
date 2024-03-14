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

The `.groupby()` function groups data together from one or more columns. As we group the data together, it forms a new **GroupBy** object. One major advantage of the `.groupby()` function is that it allows the use of method chaining for additional filtering and manipulation.

### Syntax

The basic syntax for creating a grouping of data with just a single column is as follows:

```python
grouping_variable = data.groupby("column-name")
```

{{% notice blue Example "rocket" %}}
Let's take things a step further and aggregate the data within the grouped column name using the `.sum()` function through method chaining:

```python
grouping_variable = data.groupby(["column_name"]).sum()
```

The above code will return the sum of all values within the provided column, giving you a count of each unique value inside.
{{% /notice %}}

## Aggregate Methods

pandas provides a built-in aggregate method: `Data.aggregate()` or `Data.agg()` (both accomplish the same thing, `agg()` is short for `aggregate()`). The benefit of using the `.aggregate()` function is that it allows you to pass aggregate functions as a list.

{{% notice blue Example "rocket" %}}
```python
data.agg(['mean', 'median', 'mode'])
```
{{% /notice %}}

## Groupby and Basic Math

## Groupby and Multiple Aggregations