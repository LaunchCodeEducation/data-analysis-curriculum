+++
title = "Studio: Cleaning Data"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 3
+++

## Getting Started

For this week's studio, you will be continuing your work on the same spreadsheet you practiced with in the [Exercises: Cleaning Data]({{% relref "../exercises/_index.md" %}}) section and working with a partner.

After spending some time identifying parts of the dataset that need to be cleaned we can begin restructuring our spreadsheet. Some things that were identified during the exercises are as follows:

1. Missing data
1. Invalid email addresses
1. Outliers within the `transaction_total` column
1. Unnecessary and redundant data that can be purged

The primary reason for analyzing this data is to better understand what each user is spending based on current employer and location. Keep this in mind as you begin to work through the prompts below and make decisions related to your dataset.

## Handle Missing Data and Outliers

Looking at the missing data and think about the following before you consider any action steps:
- Should the entire row of data be removed if it only contains one piece of missing data?
- Are there any value types that can be imputed based on existing values?
- Are there any values that can be replaced?

Let us begin by removing rows with missing data that you have decided are not worth keeping.

1. Create a filter for your spreadsheet. You can do so by clicking the top-left corner of your spreadsheet, clicking on `Data` > `Create a filter`.
    - Start by unselecting the "(Blanks)" option using the filter for the columns with missing data. You can see an example below:
    ![View of spreadsheet with the filter option opened ](pictures/unselect-blanks.png?classes=border)

1. Consider the interquartile range:
- What values within the `transaction_total` column should be considered outliers and removed fromthe dataset?
    - Is there any action that can be taken to adjust these values? Consider revisiting the [Summary Statistics with Excel]({{% relref "../../eda-with-spreadsheets/reading/summary-statistics/_index.md" %}}) section.

## Remove Unnecessary and Redundant Data

Is there any other redundant or duplicated data within the spreadsheet? Knowing that email addresses must be unique by nature, check to see if there are any duplicates within column C. You can do so by applying conditional formatting and using a `COUNTIF` formula like so: `=COUNTIF(C:C,C2)>1`. This will check to see if there is more than one occurence within the column.
    - After you have identified whether or not there is duplicate emails, decide on a strategy to remove them from the dataset.

Discuss with your partner on other columns you think can be removed. If there are any columns that you decide are worth dropping consider what to do with the data:
    - Do you remove it compeltely?
    - Should you store it another location for future reference?

## Filter out Inconsistencies

1. Hide or remove all rows that contain invalid emails. This includes emails that start with an `@` sign and emails that do not have an `@` sign.
1. Consider capitalization of names, employers, and locations:
    - Should they be left alone?
    - Would it be worthwhile to convert all values to lowercase?

## Submitting Your Work

When finished make sure to save your changes and add your spreadsheet to your google drive. 

Copy the link to your spreadsheet and paste it into the submission box in Canvas for **Studio: Cleaning Data** and click *Submit*.
