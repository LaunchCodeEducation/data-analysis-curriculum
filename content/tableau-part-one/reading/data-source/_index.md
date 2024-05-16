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
1. **Numerical values**
1. **Boolean values**: True or False as you are already familiar with
1. **Geographic values**: 
1. **Image role**: field that contains an image
1. **Cluster Group**: 

One of the many great features that Tableau provides is the ability to change a data type within your data source.

{{% notice blue Note "rocket" %}}
Tableau lists the data type as `Text` in the documentation, but when changing the data type of a field it is listed as `string`.
{{% /notice %}}