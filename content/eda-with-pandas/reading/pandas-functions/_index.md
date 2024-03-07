+++
title = "pandas Functions"
date = 2024-02-29T09:18:56-06:00
draft = false
weight = 4
+++

Now that we have a basic understanding of the `.Series()` and `.DataFrame()` classes and how they are used as constructor functions, lets take a look at some other functions that are included with the library and how they are used. 

The functions included below are a small portion of those included with the library but are some of the more common ones used for exploratory data analysis.

## Commonly Used Functions

Below you will find some of the most common functions used when exploring data. Things like reading a `.csv` file and referencing it using a variable is extremely useful. It allows you to parse through an entire dataset and grab the bits and pieces you are most interested in observing and analyzing in order to help you make key decisions during the process.

Two functions below that may stick out to you might be the `.info()` and the `.describe()` functions. Upon initial exploration of your dataset these two built-in functions are extremely powerful when trying to get a high-level understanding of what your DataFrame holds.

| Function | Description |
|-----------|-------------|
| `pd.read_csv(path_to_file)` | Reads a CSV (Comma-Separated Values) file into a pandas DataFrame. |
| `.head(n)` | Returns the first `n` rows of a DataFrame. |
| `.tail(n)` | Returns the last `n` rows of a DataFrame. |
| `.info()` | Prints a concise summary of a DataFrame, including column data types and non-null values. |
| `.describe()` | Generates descriptive statistics of a DataFrame, such as mean, standard deviation, min, max, and quartile values. |
| `.columns` | Accesses the column labels of a DataFrame as a list. |
| `.sort_values(by='column_name')` | Sorts a DataFrame by the values in the specified column. |
| `.isnull().sum()` | Counts the number of null (missing) values in each column of a DataFrame. |
| `.dropna()` | Removes rows containing null values from a DataFrame. |
| `.fillna(desired_value)` | Fills null values in a DataFrame with the specified value. |
| `.groupby('column_name')` | Groups a DataFrame by the unique values in the specified column. |
| `.value_counts()` | Computes the value counts for each element in a DataFrame. |
| `.shape()` | Returns a tuple representing the dimensions of your data structure (`Series` or `DataFrame`) |

{{% notice blue Note "rocket" %}}
When using the `.shape()` function for a `DataFrame` it will show the number of rows and columns `(rows, columns)`. 

When using the `.shape()` function for a `Series` it will only return the number of rows and the column will be empty `(rows, )`
{{% /notice %}}

## Statistics with `pandas`

A lot of the functions below may look familiar to you as you have already practiced some of them during your time spent with Google sheets. Refer back to [Summary Statistics with Google Sheets]({{% relref "../../../eda-with-spreadsheets/reading/summary-statistics/_index.md" %}}) if you need a refresher on basic statistics. While the functions might look different, conceptually they are the same.

| Function | Description |
|-----------|-------------|
| `.mean()` | Calculates the mean (average) of all the values in the DataFrame. |
| `.median()` | Calculates the median (midpoint) of all the values in the DataFrame. |
| `.mode()` | Calculates the mode (most commonly occuring) of all the values in the DataFrame. |
| `.std()` | Calculates the standard deviation of all the values in the DataFrame. |
| `.var()` | Calculates the variance of all the values in the DataFrame. |
| `.min()` | Finds the minimum value in the DataFrame. |
| `.max()` | Finds the maximum value in the DataFrame. |
| `.sum()` | Calculates the sum of all the values in the DataFrame. |
| `.skew()` | Calculates the skewness (measure of asymmetry) of all the values in the DataFrame. |

{{% notice blue Note "rocket" %}}
All of the above statistical functions are able to reference specific rows or columns.
{{% /notice %}}

## Examples

```python
import pandas as pd

# read a data file and assign to variable
data_file = pd.read_csv('path-to-file.csv')

# print out various info within the DataFrame
## first 10 rows of the DataFrame
print(data_file.head(10))

## last 15 rows of the DataFrame
print(data_file.tail(15))

## list out all columns within the DataFrame
print(data_file.columns)
```