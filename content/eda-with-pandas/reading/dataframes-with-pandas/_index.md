+++
title = "pandas DataFrames"
date = 2024-02-29T09:18:56-06:00
draft = false
weight = 3
+++

A pandas **DataFrame** is the second type of class that is capable of handling data.

Similar to a spreadsheet, a DataFrame can be visualzed as having multiple columns and rows associated with the data inside. The data within can be of any type.

A DataFrame can also be considered a collection or assortment of Series. Similar to a Series there are multiple ways that a DataFrame can be created:
1. Using a multi-dimensional list, dictionary, or tuple
1. Combining or joining multiple Series together
1. From a pre-existing CSV file

{{% notice blue Note "rocket" %}}
The examples above are not the only options you have for creating a DataFrame but they are the ones we will focus on in this section.
{{% /notice %}}

Column values within a DataFrame are referred to as a Series. Below is an example of how multiple Series might be used to build a DataFrame

![diagram of how a pandas Series is used to build a dataframe](pictures/pandas-series.png?classes=border)

The image below provides another visual of the general DataFrame structure. A DataFrame is similar to a Python dictionary in that the column names are like keys and the values are the data for that column.

![A diagram of a pandas dataframe](pictures/pandas-dataframe.png?classes=border)

## Creating a DataFrame

Let's dive in to some different ways you can create a DataFrame.

### Using a Multi-Dimensional List

```python {linenos=table}
# import pandas
import pandas as pd

# Create a pandas DataFrame by providing a list of lists
movie_list_of_lists = pd.DataFrame([["Interstellar", "Pride and Prejudice", "Inception", "Barbie"],["Marley & Me", "Two Weeks Notice", "The Guardian", "Bridesmaids"]])

# Create a pandas Series from a pre-existing list of lists
movies_dataframe_data = [["Interstellar", "Pride and Prejudice", "Inception", "Barbie"],["Marley & Me", "The Proposal", "The Guardian", "Bridesmaids"]]

dataframe_from_existing_list = pd.DataFrame(movies_dataframe_data)
```

The above code block accomplishes the following:
1. imports pandas.
1. Creates a pandas DataFrame called `movie_list_of_lists` by providing a list of lists as a parameter into the `.DataFrame()` function..
1. Creates a pandas DataFrame called `dataframe_from_existing_list` by using the already existing list `movies_dataframe_data` and passing it in as a parameter to the `.DataFrame()` function.

{{% notice blue Note "rocket" %}}
One thing to note about lists when they are added into a DataFrame is that each list represents a *row* not a *column*.
{{% /notice %}}

### Using a Dictionary

```python {linenos=table}
# import pandas
import pandas as pd

# Create a pandas DataFrame by providing a dictionary
movie_dictionary_dataframe = pd.DataFrame(movies = {'Name': ["Interstellar", "Pride and Prejudice", "Inception", "Barbie"],'Release': [2014, 2005, 2010, 2003]})

# Create a pandas DataFrame from a pre-existing dictionary
movies = {'Name': ["Interstellar", "Pride and Prejudice", "Inception", "Barbie"],'Release': [2014, 2005, 2010, 2003]}

dataframe_from_movies_dictionary = pd.DataFrame(movies)
```

The above code block accomplishes the following:
1. imports pandas.
1. Creates a pandas DataFrame called `movie_dictionary_dataframe` by providing a dictionary as a parameter to the `.DataFrame()` function.
1. Creates a pandas DataFrame called `dataframe_from_movies_dictionary` by using the already existing dictionary `movies` and passing it in as a parameter to the `.DataFrame()` function.

### Using a Tuple

```python {linenos=table}
# import pandas
import pandas as pd

# Create a pandas DataFrame by providing a tuple
movies_tuple_dataframe = pd.DataFrame(("Interstellar", "Pride and Prejudice"), ("Inception", "Barbie"))

# Create a pandas DataFrame by providing a pre-existing tuple
movies_data = (("Interstellar", "Pride and Prejudice"), ("Inception", "Barbie"))

dataframe_from_existing_tuple = pd.DataFrame(movies_data)
```

The above code block accomplishes the following:
1. imports pandas.
1. Creates a pandas DataFrame called `movies_tuple_dataframe` by providing a tuple as a parameter to the `.DataFrame()` function.
1. Creates a pandas DataFrame called `dataframe_from_existing_tuple` by using an already existing tuple `movies_data` and passing it in as a parameter to the `.DataFrame()` function.

## Creating a DataFrame from Series

In the following example we will create a DataFrame from two Series using pandas and the `.concat()` function included with the pandas library.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
import pandas as pd

movies = pd.Series(["Interstellar", "Pride and Prejudice", "Inception", "Barbie"], index=['1', '2', '3', '4'], name = 'movies')

genres = pd.Series(["Science Fiction", "Novel", "Science Fiction", "Comedy"], index=['1', '2', '3', '4'], name='genres')

# Using the two series above we can concatenate the two together in order to create a DataFrame.

movies_genres_dataframe = pd.concat([movies, genres], axis=1) # axis 1 specifies that the operations will be performed down each column
```

**Output**

```console
                movies           genres
1         Interstellar  Science Fiction
2  Pride and Prejudice            Novel
3            Inception  Science Fiction
4               Barbie           Comedy
```
{{% /notice %}}

{{% notice blue Note "rocket" %}}
the `axis` parameter specifies whether the data will be joined or combined along the *row* or *column*. Take a look at the table below. If you do not specify `axis=1` it will default to `axis=0`.

| Axis | Represents | Use Case |
|---|---|---|---|
| 0 (default) | **Row** | Operations performed **across rows** |
| 1 | **Column** | Operations performed **down each column** |
{{% /notice %}}

## Column Data

Suppose you want to view data from one particular column or compare specific columns to one another. You can do so by using the *column labels* to pull them aside. Let's take a look at how to do so using the same dictionary we created above.

{{% notice blue Example "rocket" %}}
```python
# import pandas
import pandas as pd

movies = {'Name': ["Interstellar", "Pride and Prejudice", "Inception", "Barbie"],'Release': [2014, 2005, 2010, 2003]}

movies_dataframe = pd.DataFrame(movies)

movie_names = movies_dataframe["Name"]
```
{{% /notice %}}

The above example accomplishes the following:

1. Imports pandas
1. Creates a dictionary called `movies` with the columns `Name` and `Release`.
1. Creates a DataFrame from the `movies` dictionary
1. A new variable called `movie_names` is created to store the values within the `Name` column of the `movies_dataframe`.

### Multiple Column Data

Now that you have seen how to pull aside a single column's data let's take a look at how to grab multiple columns and store them inside of a variable.

{{% notice blue Example "rocket" %}}
```python
# import pandas
import pandas as pd

movies = {'Name': ["Interstellar", "Pride and Prejudice", "Inception", "Barbie"],'Release': [2014, 2005, 2010, 2003], 'Genre': ["Science Fiction", "Novel", "Science Fiction", "Comedy"]}

movies_dataframe = pd.DataFrame(movies)

# Pull aside the Name and Genre columns from the movies_dataframe
movie_names_and_genres = movies_dataframe[["Name", "Genre"]]
```
{{% /notice %}}

{{% notice blue Note "rocket" %}}
Since we are grabbing specific columns from an already existing DataFrame and there are no joins happening we do not need to specify an `axis`.
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
True or False: Column names cannot be changed in a DataFrame.

<!-- Solution: False -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
True or False: A DataFrame column is a Series.

<!-- Solution: True -->
{{% /notice %}}