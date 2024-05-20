+++
title = "Connecting Data"
date = 2024-03-12T15:04:03-05:00
draft = false
weight = 4
+++

Before we connect to a data source to our Tableau workspace we will first look at what types of data there are, and how those data types are interpreted. You can find official documentation on [Tableau Data Types here](https://help.tableau.com/current/pro/desktop/en-us/datafields_typesandroles_datatypes.htm). Below we will relate the types of data in Tableau to previously known data types using `python` or `SQL`.

## Data Types in Tableau

1. **Text**: Similar to string values in python, or varchar type in SQL.
1. **Date** values: 
1. **Date** *and* **Time** values: 
1. **Numerical values**: Similar to numbers or integers in python
1. **Boolean values**: True or False
1. **Geographic values**: Used to create a geographic role. The geographic role is very useful if you are looking to visualize location data from your data source. When you assign a geographic role Tableau is kind enough to auto-generate a latitude and longitude value to the associated field. One thing to keep in mind is that the latitude and longitude values are only applicable to numeric fields or values.
1. **Image role**: field that contains an image
1. **Cluster Group**: 

One of the many great features that Tableau provides is the ability to change a data type within your data source.

{{% notice blue Note "rocket" %}}
Tableau lists the data type as `Text` in the documentation, but when changing the data type of a field it is listed as `string`.
{{% /notice %}}

## Connecting Data

There are many different types of data and file formats that are valid data sources when working with Tableau. Below are some examples:

1. .csv files
1. .json files
1. .tsv files
1. .xml files

We will be mostly working with `.csv` files (comma-separated values)

Click on the `netflix_titles.csv` link below to download the .csv file to your machine:

{{% attachments style="blue" title=".CSV Data" /%}}

One you have downloaded the `netflix_titles.csv` file, click on the `Data` tab in the top left corner and select `New Data Source` within your Tableau workbook. Click  on the `Upload from computer` button and navigate to the `netflix_tites.csv` file on your machine (probably in your downloads folder), and import the file.

Once you have imported the spreadsheet, click on the `Sheet 1` tab in the bottom left hand corner to create a new sheet from the data source.