+++
title = "Exercises: Cleaning Data"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

## Getting Started

Now that we have covered what cleaning data is and why its important, the different types of data cleaning techniques, and types of dirty data we can put it into practice!

Download the below dataset to your machine and upload it into Google Sheets.

{{% attachments style="blue" title="Random Data starter set" /%}}

## Code Along

{{% notice blue Note "rocket" %}}
Don't hesitate to reach out to course staff and your fellow students if you want to talk through the data set or a potential spot that needs to be cleaned!
{{% /notice %}}

### Missing Data

Google Sheets has many built-in tools that allow the user to handle missing data. We will explore a few of those options below to help clean a randomly generated dataset that includes the following:
`first_name`, `last_name`, `email`, `employer`, `username`, `password`, `ipv4_address`, `user_agent`, `datetime`, `company`, `city`, `transaction_total`

1. Conditional Formatting: Google Sheets allows you to use conditional formatting to highlight specific cells that meet a certain criteria. Lets start by highlighting cells that do not contain any data.
   - Select columns A - M. Once selected click `Format` > `Conditional Formatting`. Under the `Format cells if...` section select `Is empty`. All cells missing data should now be highlighted. This helps provide an idea of what columns do not contain any data and better helps you visualize as you scan through.

{{% notice green Tip "rocket" %}}
If you would like to differentiate highlight data from your conditional formatting consider color coding each rule and adding a key for reference. This will help visually when viewing your dataset.
{{% /notice %}}

### Irregular Data

Looking at the `transaction_total` column you will may notice there are some possible outliers. In cell M2 there is a total of $8,442,352.95 dollars showing for a transaction. Let's check to see if this or any other data within the column is irregular. In order to do so we need to identify the [interquartile range]({{% relref "../../eda-with-spreadsheets/reading/summary-statistics/_index.md#interquartile-range" %}}).

Select your cells where you want to store your lower, upper, and interquartile ranges and make the necessary calculations using the values within column M.

{{% expand "Check Your Solution" %}}
```console
lower quartile "=QUARTILE(M2:M, 1)"
upper quartile "=QUARTILE(M2:M, 3)"
interquartile "q3-q1"
```
{{% /expand %}}

Now that we have found the interquartile range we can apply some conditional formatting to highlight desired values.

1. Select column M and apply conditonal formatting to highlight any value that is above or greater than the upper quartile.

### Unnecessary Data

1. Further Conditional Formatting:
   - You may have noticed that there are two columns labeled "email". They look similar enough but lets apply conditional formatting so that we know they are identical, meaning duplicated or redundant data.
   - Select column C. Click `Format` > `Conditional Formatting` once more and select `Add another rule`. Since we only want to check the data below our column header change the `Apply to range` section to `C2:C604`.
   - Under `Format rules` select the `Custorm forumla is` and enter `=C2=G2` and click done. You should see that the entire row has been highlighted indicating that the entire column is a duplicate.
   - Are there any other columns within the dataset that seem unnecessary or not important to have?

### Inconsistent Data

1. Not only did we have duplicate emails within the dataset but there are also invalid and inconsistent emails. Apply conditional formatting to ensure that all emails contain an `@`.
   - Also check to make sure emails do not start with an `@` sign as that is also invalid.
1. The `transaction_total` column also has some inconsistencies.
   - All columns contain a `$` sign. This might make analysis difficult later on. These should be removed from all cells within the column. You can do so by selecting column M, clicking on `Format` > `Number` > `Number`.

## Submitting Your Work

When finished store a copy of the spreadsheet within your google drive.

Copy the link to your spreadsheet and paste it into the submission box in Canvas for **Exercises: Cleaning Data** and click *Submit*.
