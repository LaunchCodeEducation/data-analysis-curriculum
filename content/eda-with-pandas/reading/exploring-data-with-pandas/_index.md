+++
title = "Exploring Data with pandas"
date = 2024-02-29T09:18:56-06:00
draft = false
weight = 1
+++

Exploratory Data Analysis or EDA as you already know is a critical step when beginning your analysis work. Similar to the EDA work with spreadsheets we will do the same with Python and **pandas** in order to accomplish the following:

1. Form a hypotheses about what is the underlying forces effecting your data.
1. Challenge previous assumptions that may have been made when discussing the business issue.
1. Guide you on what tools and techniques you should use when working with that dataset.

{{% notice blue Note "rocket" %}}
pandas and other libraries like **NumPy** are not default Python packages. This means that we will need to install and import any external package that we need into our workspace to use their functionality.
{{% /notice %}}

## pandas

The pandas library is incredibly powerful and was built specifically for data analysis work. The library comes with many useful tools and data structures that we will cover more in depth in the upcoming readings.

We will use pandas to create, manipulate, and view data structures based on certain conditions. We will also cover some of the most common functions used when exploring data with pandas that we can use to our advantage during the exploration process.

{{% notice orange Warning "rocket" %}}
Remember to install pandas within your virtual environment! Run the following command to activate it from within your `data-analysis-projects` directory.

```python
source venv/bin/activate
```
{{% /notice %}}

{{% notice blue Note "rocket" %}}
To install pandas, you will need to run the following command within your virtual environment:

```python
pip install pandas
```

If the above command does not work, you may need to specify `pip3` in the command.

Once pandas is installed, it can be imported into your workspace in the following way:

```python
import pandas as pd
```
{{% /notice %}}

## NumPy

The NumPy library will be used in conjuction with pandas so that we can perform mathematical operations on some of our datasets. As we explore our data and in later chapters, begin cleaning and manipulating data we will use the tools it provides to make our life easier.

{{% notice blue Note "rocket" %}}
Once NumPy is installed, it can be imported into your workspace in the following way:

```python
import numpy as np
```
{{% /notice %}}