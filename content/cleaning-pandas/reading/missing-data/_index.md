+++
title = "Handling Missing Data"
draft = false
weight = 2
+++

Missing data is when a value for either a row or column is not actually there. pandas has different data types for missing data so when you print out a row of a dataframe where data is missing you will see one of these data types. pandas has a number of built-in methods that can handle missing data. `None` and `NaN` both hold missing values, however, the two are not actually equivalent. The boolean expression `None == nan` evaluates to `False`. This is because `None` is a Python object and `NaN` is a floating point value. If you find yourself needing to code a custom solution to handle an issue related to missing data, you might need to keep this in mind!

{{% notice blue Note %}}

pandas has even more types to represent a missing value, such as a data type to represent a missing datetime value. For now, we will focus on `None` and `NaN`.

{{% /notice %}}

pandas can account for missing values when doing summary statistics, so we cannot count on summary statistics to detect our missing values. We need to use built-in functionality to locate these values and handle them. pandas comes with a built-in function called `isna()` to help us here.

{{% notice blue Note %}}

pandas also has a function called `isnull()` which is an alias for `isna()`. You may see this one used frequently online so keep an eye out!

{{% /notice %}}

`isna()` can be run on either a series or a dataframe. Let's first take a look at how this could be used for a series.

```python {linenos=table}
my_series = pd.Series([1,2,np.nan,4,np.nan])
my_series.isna()
```

**Console Output**

```console
0   False
1   False
2   True
3   False
4   True
```

When you use `isna()` on a series, you get a series in return. Each value in the returned series is either `True` or `False` depending on whether the value in the series was missing or not.

You will get a similar outcome with a dataframe when locating missing values. `isna()` returns a dataframe filled with `True` or `False` depending on whether a value was missing. Now that we have located the missing data, we need to handle it. Depending on what data is missing and why, you can either replace it, remove rows or columns, or further uncover the potential impact of the missing data through interpolation.

## Removing Rows or Columns with Missing Data

This is possibly the simplest option to start with. To remove a column or row that contains missing data, pandas comes with the `dropna()` function.

Throughout this chapter, we will use the variations on the following dataframe, called `etsy_sellers`, to examine how we can use pandas to clean data.

```console
   Seller                Sales     Total_Rating     Current_Items
0  Orchid Jewels         17,896    4.5              22
1  Ducky Ducks           5,478     NaN              10
2  Candy Yarns           89,974    4.8              18
3  Parks Pins            NaN       4.9              NaN
4  Sierra's Stationary   112,988   4.3              347     
5  Star Stitchery        53,483    4.2              52 
6  NaN                   NaN       NaN              NaN
```

This dataframe has several missing data points. Let's first examine row 6, which is entirely blank. Assuming this dataset came directly from Etsy, that may indicate a shop in their records that no longer exists. If we are studying currently active Etsy sellers for our analysis, then we don't need this data so we can drop the whole row. `dropna()` removes all rows that have a missing value, so just runnning `dropna()` would remove rows 1 and 3 in addition to row 6. pandas functions come with so many different options and with every pandas function, we encourage you to always double check the documentation to see the full scope of those options. The [documentation](https://pandas.pydata.org/docs/dev/reference/api/pandas.DataFrame.dropna.html) specifies how we can drop a row where all the data is missing.

```python
etsy_sellers.dropna(how="all")
```

The above code would drop just row 6 because it is the only row with all null values. `dropna()` defaults to dropping rows, but by changing one parameter we could specify that it should drop any column that contains all missing values.

```python
etsy_sellers.dropna(axis="columns", how="all")
```

## Replacing Missing Values

```console
   Seller                Sales     Total_Rating     Current_Items
0  Orchid Jewels         17,896    4.5              22
1  Ducky Ducks           5,478     NaN              10
2  Candy Yarns           89,974    4.8              18
3  Parks Pins            NaN       4.9              NaN
4  Sierra's Stationary   112,988   4.3              347     
5  Star Stitchery        53,483    4.2              52 
```

Now that we removed row 6, we might not want to drop any more columns and/or rows. We can then look at replacing the missing values. Whether or not this is a wise decision, depends entirely on the situation at hand. Items can be missing for any number of reasons, so before replacing a missing value, you should look into why that item is missing. In the case of `etsy_sellers`, we dove in and discovered that if a shop is currently on a break, then the system returns `NaN` for the number of current items. Parks Pins is currently on a break so none of the items on their shop are actually available for sale. In the case of our analysis, we then decide to replace all the missing values with 0. In our hypothetical situation, when a shop sells out of their items, their shop is put on a break until they add new items so 0 makes logical sense to replace our missing values with.

pandas comes with a function called `fillna()` that will help us do this. If we run the following code, we would have a problem though.

```python
etsy_sellers.fillna(0)
```

This code would actually replace every single missing value in the dataframe with 0. But we decided to be a little more intentional and want to just replace the missing values in the `Current_Items` column.

```python 
cols = {"Current_Items": 0}
etsy_sellers.fillna(value=cols)
```

We can specify using a dictionary what column we want to fill and with what we want to fill it. This gives us so much more flexibility!

## Interpolating Missing Values

Because pandas can account for missing values, we can also interpolate what the missing values might be. **Interpolation** means inserting values into a dataset based on exisiting trends in the data. The `interpolate()` function includes a parameter that can specify how you want pandas to interpolate the data. The `method` parameter defaults to a linear interpolation meaning that pandas will fill in the missing values with the assumption that everything is equally spaced like a line.

```console
   Seller                Sales     Total_Rating     Current_Items
0  Orchid Jewels         17,896    4.5              22
1  Ducky Ducks           5,478     NaN              10
2  Candy Yarns           89,974    4.8              18
3  Parks Pins            NaN       4.9              0
4  Sierra's Stationary   112,988   4.3              347     
5  Star Stitchery        53,483    4.2              52 
```

The last remaining values are in the `Total_Rating` column and the `Sales` column. Linear interpolation makes sense in neither case. We might want to interpolate what the missing rating is for Ducky Ducks based on what other values in the column are so in that case we can use the pad method.

```python
etsy_sellers.interpolate(method="pad")
```

Interpolation can be a bit of a gamble if you don't understand the underlying trends of the dataset, so you may not see it very often.

## Check Your Understanding

{{% notice green Question %}}

True or False: pandas can account for missing values when performing certain calculations such as summary statistics

{{% /notice %}}

<!-- True -->

{{% notice green Question %}}

Which pandas function detects missing values? Select all that apply.

1. `dropna()`
1. `isna()`
1. `interpolate()`
1. `fillna()`
1. `isnull()`

{{% /notice %}}

<!-- 2 and 5 -->