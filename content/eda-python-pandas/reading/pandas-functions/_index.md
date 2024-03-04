+++
title = "pandas Functions"
date = 2024-02-29T09:18:56-06:00
draft = false
weight = 3
+++

Now that we have a basic understanding of `pandas` data structures lets take a look at some functions that are included with the library and how they are used. The functions included below are a small portion of those included with the library but are some of the more common ones used for exploratory data analysis.

## Commonly Used Functions

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

## Statistics with `pandas`

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