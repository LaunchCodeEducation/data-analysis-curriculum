+++
title = "Types of Dirty Data"
date = 2024-01-31T13:01:06-06:00
draft = false
weight = 1
+++

There are four different types of "dirty" data. Understanding and being able to differentiate between them will help you categorize your data and decide what technique or practice would work best for cleaning a dataset.

## Missing Data
Identifying missing data is straight forward. If you see that a row or column is blank or void of a data entry then that can be classified as missing data. 

A common example would be a survey that has questions which are optional. If the user decides not to answer the question it may result in an empty cell within your dataset. 

There are of course ways to combat missing data that usually involves deleting the entire entry or imputing data based on existing knowledge of the dataset or a substitute value like `N/A` or `NaN`. Another approach is to use column means or regression values based on the data that you do have. 

You can also revisit the place the data was first collected to see if it exists there and was lost in transit.

{{% notice blue Example "rocket" %}}
The table below has numerous examples of missing data within the `last_name`, `email`, `employer`, `phone_number`, and `favorite_hobby` columns.

| first_name | last_name | email                    | employer            | phone_number   | favorite_hobby    |
|-|-|-|-|-|-|
| Amy        | Williams  | amorris@example.net      | Emerson Electric    | 379-012-0298   | hiking            |  
| Robert     | Marshal   |                           | Edward Jones        | 288-085-0092   | reading           |
| Kimberly   | Stephen   | ptaylor@example.net      |                     | 126-015-0765   | yoga              |
| Rachel     | Vincent   | rodneythomas@example.net | Neuroflow           |                | painting          |   
| Brian      | Salinas   | iperez@example.net       | Edward Jones        | 914-555-4392   |                   |
| Wesley     |           | stephen94@example.net    | Emerson Electtic    | 504-326-2719   | gaming       |
{{% /notice %}}

In relation to the above examples it is important to understand whether or not the missing data was due to user error or the means of collecting the data itself. This will help when deciding on what strategy can be used to alleviate the problem.

## Irregular Data
**Irregular** data is usually related to finding outliers within the dataset. Outliers must first be detected before deciding on a strategy to handle them. An outlier can be something like an email that does not contain an `@` symbol, or a number that is not within an appropriate range for the expected results.

{{% notice blue Example "rocket" %}}
In the below table you will notice that the `email` column contains emails without an `@` symbol and phone numbers without 9 characters.

| first_name | last_name | email                    | employer           | phone_number     | favorite_hobby |
|-|-|-|-|-|-|
| Amy        | Williams  | amorris@example.net      | Emerson Electric   | 37-012-0298     | hiking |
| Robert     | Marshal  | christopher84example.org| Edward Jones       | 288-05-0092     | reading |
| Kimberly   | Stevens   | ptaylor@example.net      | Centene            | 126-015-0765     | yoga |
| Rachel     | Vincent   | rodneythomas@example.net | Nueroflow          | 857-203-034     | painting |
| Brian      | Salinas   | iperez@example.net       | Edward Jones       | 914-555-4392     | cooking |
| Wesley     | Boone     | stephen94example.net    | Emerson Electric   | 504-326-2719     | gaming |
{{% /notice %}}

## Unnecessary Data
Unnecessary data could be duplicates, irrelevant, or any uninformative data. This typically involves a dataset with values that are either not useful or will cause issues during analysis. Removing unncessary and redundant data will help with query and compute speeds which improves performance and will also simplify the dataset.

Common examples of unnecessary data are duplicated rows and columns or old or outdated data that is inaccurate. Another piece of unnecessary data would be data entered for testing purposes that were not removed and were left inside of the dataset.

{{% notice blue Example "rocket" %}}
The table below represents an example of redundant or unnecessary data. The primary purpose of this data is to store contact information for different users, making the `favorite_hobby` category unnecessary within this dataset.

| first_name | last_name | email                    | employer            | phone_number   | favorite_hobby    |
|-|-|-|-|-|-|  
| Amy        | Williams  | amorris@example.net      | Emerson Electric    | 379-012-0298   | hiking            |
| Robert     | Marshal   | christopher84@example.org| Edward Jones        | 288-085-0092   | reading           |
| Kimberly   | Stephen   | ptaylor@example.net      | Centene             | 126-015-0765   | yoga              |
| Rachel     | Vincent   | rodneythomas@example.net | Neuroflow           | 857-203-0334   | painting          |
| Brian      | Salinas   | iperez@example.net       | Edward Jones        | 914-555-4392   | cooking           |
| Wesley     | Boone     | stephen94@example.net    | Emerson Electtic    | 504-326-2719   | gaming       |
{{% /notice %}}

## Inconsistent Data
Inconsistent data is anything that messes with your model. This is likely due to inconsistent formatting and can be addressed by re-formatting all values in a column or row.

{{% notice blue Example "rocket" %}}
Here is a table containing inconsistencies using the provided data. The `employer` column contains different spellings for the same name and the `favorite_hobby` column has different data types contained within.

| first_name | last_name | email                    | employer            | phone_number   | favorite_hobby    |
|-|-|-|-|-|-|  
| Amy        | Williams  | amorris@example.net      | Emerson Electic    | 379-012-0298   | 2            |
| Robert     | Marshal   | christopher84@example.org| Edward Jones        | 288-085-0092   | reading           |
| Kimberly   | Stephen   | ptaylor@example.net      | Centene             | 126-015-0765   | 3              |
| Rachel     | Vincent   | rodneythomas@example.net | Neuroflow           | 857-203-0334   | painting          |
| Brian      | Salinas   | iperez@example.net       | Edwards Jones        | 914-555-4392   | cooking           |
| Wesley     | Boone     | stephen94@example.net    | Emerson Electtic    | 504-326-2719   | gaming       |
{{% /notice %}}
