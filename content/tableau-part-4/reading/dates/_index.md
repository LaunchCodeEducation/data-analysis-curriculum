+++
title = "Dates and Times"
date = 2024-03-12T15:04:03-05:00
draft = false
weight = 1
+++

The first objective we have to cover is learning about how to work with dates in Tableau. As we have already seen throughout this course, dates and times can be stored in a variety of different ways. Dates and times are vital data points and we do want to make sure that we understand how to work with that data type in Tableau.

## Loading Datetime Data into Tableau

Before you load any datetime data into Tableau, review what you are loading. You may have to convert the data to datetime if Tableau doesn't load it properly so you need to know what you have to properly convert the data. 

Once your data is loaded, you should see a calendar icon if the data loaded properly. If you have an icon that looks like "Abc", then the data was loaded as a string. You can convert the data field by clicking on the string icon and selecting *Date & Time* from the resulting menu. If Tableau was unsuccessful in converting the field, then the data will become null values so you may have to try out the [DATEPARSE function](https://help.tableau.com/current/pro/desktop/en-us/data_dateparse.htm?_gl=1*9plr4*_ga*MTY0NDMzMDU4Mi4xNzE1MTE1NDU0*_ga_8YLN0SNXVS*MTcxODIwODU2NS4zOS4xLjE3MTgyMDkxMzAuMC4wLjA.#dateparse).

## Continuous versus Discrete

Tableau has two different types of date fields: continuous and discrete. **Discrete date fields** are the default in Tableau and can be used to create bar charts or other visualizations where you want to compare the values between dates. **Continuous date fields** are used to measure the changes in values over time. To change a date field from discrete to continuous by right-clicking on the field and clicking *Convert to Continuous*. Continuous date fields are highlighted in green while discrete ones are blue so the color may change after you have selected this option. 

## Date Functions

In [SQL Part 2]({{% relref "../../../sql-part-2/reading/date-time-functions" %}}), we saw how we can use functions to perform important calculations related to dates and times. Tableau has a number of similar functions that allow us to perform different analyses.

### DATEADD

`DATEADD` has a similar functionality in Tableau where we can add to a start date. For example, if we are visualizing employee start dates and want to find the end of their 90-day probabtionary period, we can do the following:

`DATEADD('day', 90, [start date])`

### DATEDIFF

`DATEDIFF` tells us the difference between two dates in either days, weeks, months, or years. For example, we could find out an employee's tenure at the company with the following:

`DATEDIFF('year', [start date], [end date])`

### DATENAME

`DATENAME` returns the name of a component of a date. For example, if we want to return the name of the month an employee started in, we can do the following:

`DATENAME('month', [start date])`

### DATEPART

`DATEPART` returns the numerial value of a component of a date. For example, if we want to return the number of the month an employee started in, we can do the following:

`DATEPART('month', [start date])`

{{% notice blue Note %}}

Additional datetime functions in Tableau can be found in this [article](https://help.tableau.com/current/pro/desktop/en-us/functions_functions_date.htm).

{{% /notice %}}

## Check Your Understanding

{{% notice green Question %}}

Dates cannot be changed once you have connected your data set to Tableau

   a. True 
   b. False 

{{% /notice %}}

{{% notice green Question %}}

When working with a relational data source, Tableau defaults dates as ______?

   a. Dimensions 
   #. Continuous fields

{{% /notice %}}

{{% notice green Question %}}

Converting a date to a continuous field is very useful when looking at trends.
   
   a. True
   b. False

{{% /notice %}}