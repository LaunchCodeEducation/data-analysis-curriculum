+++
title = "Build a Chart"
date = 2024-03-12T15:04:03-05:00
draft = false
weight = 5
+++

Now that we have covered some of the basics we will create a chart with our imported data.

{{% notice blue Note "rocket" %}}
If you have closed out the data connection to the `netflix_titles.csv` file, reopen the connection!
{{% /notice %}}

Using the `netflix_titles.csv` data, we will create a bar chart that shows the `Type` (Movie or TV Show), the `Date Added` (What year the Movie or TV show was added to Netflix), and we will use the `Show Id` as a unique identifier to provide a `CNT` measure. The result will be a bar chart that displays how many `Movies` and `TV Shows` were added to Netflix and in what year they were added.

## Creating the Chart

1. Let's first start out by adding the `Type` pill to the `Columns` shelf.
1. Next, add the `Show Id` pill to the `Rows` shelf.
    - Right click on the `Show Id` pill and change from a dimension to a measure, selecting the `count` as the measure.

![Visual of a tableau workbook with the Type as a column, and Show Id as a measure of count as a row](pictures/type-show-id-checkpoint.png?classes=border)

1. Now we can add `Date Added` pill to the `Columns` shelf.

![Visual of tableau workbook with the Type and Date Added as columns, and Show ID as a measure of count as a row](pictures/date-added-checkpoint.png?classes=border)

{{% notice blue Note "rocket" %}}
You may notice in the above image that the name of the sheet has been changed to `netflix_titles`. You can also do this if you would like! Right click on either the `Sheet 1` name within the view and the tab in the bottom left corner to change the name.
{{% /notice %}}