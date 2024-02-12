+++
title = "Data Cleaning Techniques"
date = 2024-01-31T13:01:06-06:00
draft = false
weight = 1
+++

Data cleaning techniques aim to address issues and fix errors within the dataset before you begin to analyze the actual. This might sound odd because you initially analyze the data before deciding on what techniques you might need to utilize to clean it up. However, cleaning data usually helps get it to a more analysis-friendly or readable state even if it includes some analysis to get there. 

Below we will cover some common techniques that are used to "clean" data sets.

## Common Data Cleaning and Formatting Techniques

### Filtering
**Filtering** will solve many issues as it pertains to cleaning data. With filters you can hide specific rows, only have columns display data that meets the user-provided criteria like dates, test scores, or locations.

Google sheets allows you to create a filter that will assist in handling data within each column. To create a filter select one or multiple columns, click on the `Data` button >> `Create a filter`. 

Once you have created the filter, click on the icon next to the column name as shown in the image below:

![Image showing the icon next to a colum with a filter created to help organize data](pictures/filter-icon.png?classes=border)

### Sorting
**Sorting** your data might involve moving rows or columns around to be more in-line with their numeric characters or names. This will help you identify a duplicate column or row within your dataset.

You can sort an entire spreadsheet or multiple columns at once. Select the column you would like to sort and click on `Data` > `Sort sheet` or `Sort range` for a specific range of columns or cells. You can also select the advanced sorting option to apply the option that the column includes a header row if you have one. This will keep the header row in the top cell.

{{% notice green Tip "rocket" %}}
If you have a header row a very useful option is to freeze the entire row. That way your header row will remain in place as you clean your data. In order to freeze an entire row, highlight the entirety of row 1, click on `View` > `Freeze` > `1 row`.
{{% /notice %}}

### Remove Trailing Whitespace
Often times when cleaning data a common practice is to remove **trailing whitespace** from the end of a value.If you have an additional space at the end of any value it could cause an unwanted result when searching through your data in the future.

Google sheets has a built in option that allows you to trim whitespace. In order to do so, select the column or columns that need whitespace trimmed and click on `Data` > `Data cleanup` > `Trim Whitespace`.

### Number and Date formats
Numbers are often formatted in different ways when data is first received. If you have a column containing just numbers ensure that they are all formatted the same. This often helps when working with a specific currency, or data with decimals. One mistake that is made when cleaning datasets is to not apply formatting to all columns and rows containing numeric data instead of only columns and rows used in your calculations or forumla.

When listing a date it can be stored in multiple ways - `dd/mm/yyyy` for day/month/year, or `mm/dd/yyyy` for month/date/year. Make sure that your dates are in sync across your entire dataset.

### Use functions
**Functions** help keep things consistent across your data set. Using functions has many advantages like matching specific patterns within your data using **REGEX**, automating processes like calculations and handling specific edge cases throughout your data set.

Some common functions that you might find helpful include the following:
1. `SUM`: Adds total values within the provided range
1. `AVERAGE`: Calculates an average value from the provided range of cells
1. `COUNT`: Returns total number of cells in provided range
1. `COUNTIF`: Returns a count based on the provided
1. `COUNTBLANK`: Counts the total number of blanks or empty cells within the provided range
1. `COUNTUNIQUE`: Counts the total number of unique values within the provided range
1. `UNIQUE`: Returns only unique rows in the provided range, removing duplicate data.
1. `LOWER`: Converts a string of text to lowercase
1. `UPPER`: Converts a string of text to uppercase

{{% notice blue Note "rocket" %}}
If you would like to view the entire list of functions available within google sheets you can find them here: [Google Sheets function list](https://support.google.com/docs/table/25273?hl=en) 
{{% /notice %}}

### Remove Redundant data
Removing duplicated or **redundant data** will help not only shrink your dataset down but also remove any piece of data from being recorded twice. If redundant data is not removed it can slow down queries made to the dataset. Datasets will often times include data that is not necessary and can be removed to reduce bloat and required storage space. This practice might not seem critical on smaller sized datasets but as the size of the dataset increases it will have a much bigger impact.

Fortunately google sheets has a tool to remove duplicates! Select the column you would like to clean up and click on `Data` > `Data cleanup` > `Remove duplicates`.

{{% notice red Warning "rocket" %}}
Use the `Remove duplicates` option with care! Sometimes a column may have duplicate values that is intended! For example if you have a `first_name` column you may not want to remove all duplicates as there may be multiple people with the same first name.
{{% /notice %}}

### Use Lists
A great way to standardize data entry and remove the possiblity of user error is to provide a pre-selected list of possible values. This will allow the user to only select between a small list of values when recording data so that the need to enter data manually is removed.

Google sheets allows you to add data validation but creating a drop down menu. Select the column or cells that you would like to add a drop-down list to and click on `Data` > `Data validation` > under `Criteria` select `Dropdown` and add any options you want included in the list.

![Image of a dropdown list created within google sheets](pictures/dropdown-list.png?classes=border)

### Rename Columns
When working with a dataset it is very helpful to have proper naming conventions for your columns. This not only helps you understand the data you are working with but it also makes things a bit more clear for your stakeholders. For example when working with a column full of birth dates named "DOB" might be a confusing acronym, a better name would be "DateOfBirth".