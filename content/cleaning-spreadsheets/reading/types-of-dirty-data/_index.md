+++
title = "Types of Dirty Data"
date = 2024-01-31T13:01:06-06:00
draft = false
weight = 1
+++

There are four different types of "dirty" data. Understanding and being able to differentiate between them will help you categorize your data and decide what technique or practice would work best for cleaning a dataset.

## Missing Data
Identifying missing data is straight forward. If you see that a row or column is blank or void of a data entry then that can be classified as missing data. 

{{% notice blue Example "rocket" %}}
A common example would be a survey that has questions which are optional. If the user decides not to answer the question it may result in an empty cell within your dataset. 

There are of course ways to combat missing data that usually involves deleting the entire entry or imputing data based on existing knowledge of the dataset or a substitute value like `N/A` or `NaN`. 

Another approach is to use column means or regression values based on the data that you do have. You can also revisit the place the data was first collected to see if it exists there and was lost in transit.
{{% /notice %}}

In relation to the above example it is important to understand whether or not the missing data was due to user error or the means of collecting the data itself. This will help when deciding on what strategy can be used to alleviate the problem.

## Irregular Data
Irregular data is usually identified as data that is not uniform across the dataset. If you have dates that are not formatted the same or contact numbers that do not use the same separators like dashes or spaces this will cause issues later on. Another example would be strings of text that are all capitalized or numbers with many leading zeros.

The goal of identifying irregular data is to help understand what approach or changes can be made so that you can properly structure and format the data while cleaning it.

## Unnecessary Data

## Inconsistent Data