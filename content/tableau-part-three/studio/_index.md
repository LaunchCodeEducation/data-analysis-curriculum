+++
title = "Studio: Tableau Part 3"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 3
+++

## Getting Started

### Business Issue:

You work for TarMart corporate. TarMart has 45 department stores across the country, of various 
sizes. Between 2010 and 2013, TarMart has tracked weekly sales of each store by department. Your 
supervisors want some insights on which stores and departments are performing the best in weekly 
sales.

### Setting Up the Studio:

Download [Retail Data Analytics data set](https://www.kaggle.com/datasets/manjeetsingh/retaildataset?select=Features+data+set.csv). There are 3 CSV files. To download all CSV files at once, click on the `Download` bubble next to the `New Notebook` bubble.  An orange arrow is pointing to the `Download` bubble in the image below.

1. Open the CSV file in Tableau Public.  
1. When you open this data set, you will want to create a relationship between the 3 CSV files.

   - Each CSV has a `Store` column.
   - Here's some more context for working with relationships in Tableau:

      - Relationships vs Joins <Here's some more context for working with relationships in Tableau:>`__.
      - [Don't Be Scared of Relationships(https://help.tableau.com/current/pro/desktop/en-us/datasource_dont_be_scared.htm).

{{% notice blue Note "rocket" %}}
This dataset has a large amount of rows that Tableau Public might have trouble querying at times. To mitigate this, try using only aggregated measures when dropping `Weekly Sale` into a sheet.
{{% /notice %}}

### EDA

1. What do weekly sales over time look like?
1. Weekly sales by store type?
1. Weekly sales by store?
1. Weekly sales by department?
1. How do sales by store and department change by quarter?

### Calculations

1. Determine a cutoff for constituting a high sale amount.

   - Use your discretion from what you observe in your vizzes. 
   - Use a basic calculation to create a new field indicating your measure for high sales.
   
      -  Use this field in a new chart to display which stores return higher sales than others.

1. TarMart wants to know which of the stores included in this dataset have contributed the most to overall sales in the company. 

   - Create a viz that uses the Quick Table Calculation `Percent of Total` to accomplish this. 

### Parameters

1. Use a filter and parameter to change the number of stores displayed in the viz you created for Calculations Question 2.

   - Make a copy of your viz by right clicking on the sheet tab and selecting `Duplicate`.
   - Add the `Stores` pill to the filter tab in your new viz. Create a `Top` filter from your filter type choices. Note that `Stores` may initially be pulled in as a continuous measure due to its data type. Change it to a discrete dimension. 
   - Create a parameter that shows the `Top Stores`.
   
      - Make the data type an integer.
      - Make the allowable values a range.
      - Set the range to a fixed, setting values from the `Store` column.
      
   1. Return to your Store filter and edit the Top options to use the `Top Store` parameter you have created.
   1. Add your filter parameter to the sheet.

      - Right click on the `Top Store` parameter from the left hand Data pane, select `Show Parameter`. 

1. Return to your viz that displays the average weekly sales by department to use a parameter to display the top department marks in a distinct color. 

   1. Right click on the `Dept` field to convert it to a dimension.
   1. Create a set of top departments using the `Top Stores` parameter.
   1. Drag the department set to the color option in the marks pane.
   1. Right click on the `Top Stores` parameter to show the parameter control in the viz.
   1. Rename the `Top Store` parameter to account for the fact that it's now being used for both store and department dimensions.  
   
### Dashboard and Finesse

1. Present your charts in a dashboard that summarizes your findings. 
1. Now is a good time to update labels and colors for an easily digestible report.

### Finishing Touches

Before you turn in your vizzes:

1. Make sure that they are easy to read. 
1. Review and edit any axes so that they don't contain any file information. 
1. Make sure any filtering, group, or set information is easy to understand. 

   - For example, when using a set the predefined labels may say “In” and “Out”. Would extra context make them easier to understand? 
   - Don't forget to title your charts.  

1. If you want to explore fonts and colors, go right ahead. 

   - Feel free to change the colors of any/all of your charts.  

## Submitting Your Work

When finished make sure to save and publish your work to your Tableau Public account. Copy the URL to your published Tableau project and paste it into the submission box in 
Canvas for **Studio: Visualization with Tableau Part 3** and click *Submit*.
