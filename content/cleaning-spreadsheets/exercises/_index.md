+++
title = "Exercises: Cleaning Data"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

## Getting Started

Now that we have covered what cleaning data is and why its important, the different types of data cleaning techniques, and types of dirty data we can put it into practice!

Fork this [GitHub repository](https://github.com/launchcodeeducation/cleaning-data/blob/main/Cleaning%20Data%20Exercises.ipynb) and clone to your computer. 

## Code Along

{{% notice blue Note "rocket" %}}
Don't hesitate to reach out to course staff and your fellow students if you want to talk through the data set or a potential spot that needs to be cleaned!
{{% /notice %}}

### Missing Data

Google sheets has many built in tools that allow the user to handle missing data. We will explore a few of those options below.

1. Conditional Formatting: Google Sheets allows you to use conditional formatting to highlight specific cells that meet a certain criteria. Lets start by highlighting cells that do not contain any data.
   - Select columns A - D. Once selected click `Format` > `Conditional Formatting`. Under the `Format cells if...` section select `Is empty`. All cells missing data should now be highlighted.
   - Let's take it a step further and highlight rows within the email column that do not contain an `@` symbol. Select column `C` and click on `Format` > `Conditional Formatting` once more. Click on `Add Another rule`, select the `Text does not contain` under the `Format cells if..` dropdown and insert an `@` symbol into the Value or formula box. Be sure not to include cell `C1` in this rule!
      - You might also notice that some values within the `email` column start with an `@` symbol and do not have any text before it. Create a filter that checks if the text in column `C` starts with an `@` symbol.

## Submitting Your Work

When finished make sure to push your changes up to GitHub. 

Copy the link to your GitHub repository and paste it into the submission box in Canvas for **Exercises: Cleaning Data** and click *Submit*.
