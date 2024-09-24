+++
title = "Dates and Times"
date = 2024-03-12T15:04:03-05:00
draft = false
weight = 1
+++

The first objective we want to cover is learning about how to work with datetime data in Tableau. As we have already seen throughout this course, SQL and Python handle datetime data, so we want to take a look at how Tableau handles it as well. 

Datetime data can be tricky, but it is vital in an analysis, so we want to prepare you to tackle it.

## Loading Datetime Data into Tableau

The first step in working with datetime data is to review your data before loading it into Tableau. You may have to convert the data from strings to datetime manually if Tableau doesn't load it properly. 

Once your data is loaded, you should see a calendar icon next to the field if the data was loaded in as datetime data. 

If you don't, then the data was loaded as a string. You can convert the data field by clicking on the string icon and selecting *Date & Time* from the resulting menu. 

{{% notice blue Note %}}

If Tableau was unsuccessful in converting the field, then the data will become `Null` values, so you may have to try out the [DATEPARSE function](https://help.tableau.com/current/pro/desktop/en-us/data_dateparse.htm?_gl=1*9plr4*_ga*MTY0NDMzMDU4Mi4xNzE1MTE1NDU0*_ga_8YLN0SNXVS*MTcxODIwODU2NS4zOS4xLjE3MTgyMDkxMzAuMC4wLjA.#dateparse).

{{% /notice %}}

## Continuous versus Discrete

Tableau has two different types of date fields: continuous and discrete. 

**Discrete date fields** are the default in Tableau and can be used to create bar charts or other visualizations where you want to compare the values between dates. You will notice that all dates immediately become dimensions and are blue. 

**Continuous date fields** are used to measure the changes in values over time and are under measures, making them green. To change a date field from discrete to continuous, right-click on the field and click *Convert to Continuous*. You will know the change was successful when the field moves from dimensions to measures and changes color.

{{% notice blue Note %}}

Make sure you convert a field to datetime data before attempting to convert it to continuous! 

{{% /notice %}}

## Date Functions

In [SQL Part 2]({{% relref "../../../sql-part-2/reading/date-time-functions" %}}), we saw how we can use functions to perform important calculations related to dates and times. Tableau has a number of similar functions that allow us to perform different analyses. For all the examples below, we are working for a major corporation analyzing their hiring and employment data.

### DATEADD

`DATEADD` has a similar functionality in Tableau where we can add to a start date. If we are visualizing employee start dates and want to find the end of the 90-day probationary period, we can do the following:

{{% notice blue Example %}}

`DATEADD('day', 90, [start date])`

If the start date was 6/1/2024, the value returned would be:

`8/29/2024`

{{% /notice %}}

### DATEDIFF

`DATEDIFF` tells us the difference between two dates in either days, weeks, months, or years. For example, we could find out an employee's tenure at the company with the following:

{{% notice blue Example %}}

`DATEDIFF('year', [start date], [end date])`

If the start date was 6/1/2019 and the end date was 6/15/2024, the value returned would be:

`4`

{{% /notice %}}

### DATENAME

`DATENAME` returns the name of a component of a date. For example, if we want to return the name of the month an employee started in, we can do the following:

{{% notice blue Example %}}

`DATENAME('month', [start date])`

If the employee started on 6/1/2024, the value returned would be:

`June`

{{% /notice %}}

### DATEPART

`DATEPART` returns the numerical value of a component of a date. For example, if we want to return the number of the month an employee started in, we can do the following:

{{% notice blue Example %}}

`DATEPART('month', [start date])`

If the employee started 6/1/2024, then the value returned would be:

`6`

{{% /notice %}}

{{% notice blue Note %}}

Additional datetime functions in Tableau can be found in this [article](https://help.tableau.com/current/pro/desktop/en-us/functions_functions_date.htm).

{{% /notice %}}

## Check Your Understanding

{{% notice green Question %}}

When working with a relational data source, Tableau defaults dates as ______?

1. Discrete fields
1. Continuous fields

{{% /notice %}}

<!-- discrete fields -->

{{% notice green Question %}}

True or False: Converting a date to a continuous field is very useful when looking at trends.

{{% /notice %}}

<!-- true -->
