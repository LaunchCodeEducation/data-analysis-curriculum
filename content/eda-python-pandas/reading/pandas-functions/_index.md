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
| `df.head(n)` | Returns the first `n` rows of a DataFrame. |
| `df.tail(n)` | Returns the last `n` rows of a DataFrame. |
| `df.info()` | Prints a concise summary of a DataFrame, including column data types and non-null values. |
| `df.describe()` | Generates descriptive statistics of a DataFrame, such as mean, standard deviation, min, max, and quartile values. |
| `df.columns` | Accesses the column labels of a DataFrame as a list. |
| `df[column_name]` | Selects a single column from a DataFrame by its column label. |
| `df.loc[row_label]` | Selects a single row from a DataFrame by its row label. |
| `df.iloc[row_index]` | Selects a single row from a DataFrame by its row index. |
| `df.sort_values(by='column_name')` | Sorts a DataFrame by the values in the specified column. |
| `df.isnull().sum()` | Counts the number of null (missing) values in each column of a DataFrame. |
| `df.dropna()` | Removes rows containing null values from a DataFrame. |
| `df.fillna(desired_value)` | Fills null values in a DataFrame with the specified value. |
| `df.groupby('column_name')` | Groups a DataFrame by the unique values in the specified column. |
| `df.value_counts()` | Computes the value counts for each element in a DataFrame. |