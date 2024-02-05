+++
title = "Data Cleaning Techniques"
date = 2024-01-31T13:01:06-06:00
draft = false
weight = 1
+++

Data cleaning techniques aim to address issues and fix errors within the dataset before you begin to analyze the actual. This might sound odd because you initially analyze the data before deciding on what techniques you might need to utilize to clean it up. However, cleaning data usually helps get it to a more analysis-friendly or readable state even if it includes some analysis to get there. 

Below we will cover some common techniques that are used to "clean" data sets.

## Common Data Cleaning and Formatting Techniques

1. **Filtering** - Using a filter will solve many issues as it pertains to cleaning data. With filters you can hide specific rows, only have columns display data that meets the user-provided criteria like dates, test scores, or locations.
1. **Sorting** - Sorting your data might involve moving rows or columns around to be more in-line with their numeric characters or names. This might help you identify a duplicate column or row within your dataset.
1. Removing **Trailing Whitespace** - Often times when cleaning data a common practice is to remove trailing whitespace from the end of a value.If you have an additional space at the end of any value it could cause an unwanted result when searching through your data in the future.
1. Number formats - Numbers are often formatted in different ways when data is first received. If you have a column containing just numbers ensure that they are all formatted the same. This often helps when working with a specific currency, or data with decimals. One mistake that is made when cleaning datasets is to not apply formatting to all columns and rows containing numeric data instead of only columns and rows used in your calculations or forumla.
1. Date formatting - When listing a date it can be stored in multiple ways - `dd/mm/yyyy` for day/month/year, or `mm/dd/yyyy` for month/date/year. Make sure that your dates are in sync across your entire dataset.
1. Use **functions** to help keep things consistent across your data set. Using functions has many advantages like matching specific patterns within your data using **REGEX**, automating processes like calculations and handling specific edge cases throughout your data set.
1. Remove **Redundant data** - Removing duplicated data will help not only shrink your dataset down but also remove any piece of data from being recorded twice. If redundant data is not removed it can slow down queries made to the dataset. Datasets will often times include data that is not necessary and can be removed to reduce bloat and required storage space. This practice might not seem critical on smaller sized datasets but as the size of the dataset increases it will have a much bigger impact.
1. Use Lists - A great way to standardize data entry and remove the possiblity of user error is to provide a pre-selected list of possible values. This will allow the user to only select between a small list of values when recording data so that the need to enter data manually is removed.
1. Rename Columns - When working with a dataset it is very helpful to have proper naming conventions for your columns. This not only helps you understand the data you are working with but it also makes things a bit more clear for your stakeholders. For example when working with a column full of birth dates named "DOB" might be a confusing acronym, a better name would be "DateOfBirth".