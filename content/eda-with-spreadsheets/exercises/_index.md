+++
title = "Exercises"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

Go to Kaggle and download the [Walmart Dataset](https://www.kaggle.com/datasets/yasserh/walmart-dataset). 

Before beginning your analysis, review the Kaggle page to make sure that you understand what each column is about. Do you know what a CPI is? What is a holiday week and what isn't? Once you feel like you have a general understanding of each column you can start working in a spreadsheet.

{{% notice green Tip %}}

This dataset includes over 5,000 rows! To save yourself time, if you want to select the entire column to include in a calculation, click on the column's letter.

{{% /notice %}}

We can import a CSV into Excel with the following steps:

1. Create a new workbook.
1. Click *File* > *Import*.
1. This will result in a popup. Click on *Upload* and drag your downloaded CSV into the box or select *Browse* and find it in your computer's file system.
1. Once Excel is ready, a popup will appear with different options. You want the *Import Location* to be "Replace current sheet", *Separator type* to be "Detect automatically", and to make sure that "Convert text to numbers, dates, and formulas" is checked. Click *Import data* when you are ready.

With your dataset imported, we can begin EDA. Focusing on just the `Fuel_Price` column answer the following questions:

1. What is the mean, median, and mode fuel price?
1. What is the range?
1. What is Q1, Q3, and IQR?
1. What chart works best for comparing the temperature to the fuel price? What about the fuel price over time?
1. Are there any observations you can make about the data so far?
