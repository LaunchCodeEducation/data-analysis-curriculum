+++
title = "Parameters"
date = 2024-05-28T13:45:19-05:00
draft = false
weight = 2
+++

## Parameters

<!-- {{% notice blue Note "rocket" %}}
The examples in this reading will continue to use the `netflix_titles.csv` dataset if you would like to follow along.
{{% /notice %}} -->

**Parameters** allow fo more fine-tuned control over calculations that you would like to apply to any part of your visualization. For example, if you would like to divide multiple measures by a specific amount, you can create a new calculation and then attach or include your parameter within. 

One of the major benefits is that you can change your parameter value on the fly so that your calculations will be updated dynamically wherever they exist. Only having to change one value instead of many to view a different result is extremely convenient.

At it's core a parameter is a variable that can be referenced inside of a calculation, filter, or reference line.

### Creating a Parameter

To create a parameter in Tableau:
1. Select the arrow icon within the Data pane which opens a dropdown.

![Create a new paramater using Tableau public](pictures/create-parameter.png?classes=border)

1. Click on `Create Parameter...`
    - this will open up a menu allowing you to create a brand new parameter.

![Create a parameter in Tableau menu](pictures/parameter-menu.png?classes=border)

{{% notice blue Example "rocket" %}}
The following example would create a parameter named `select_type` allowing the user to select the `Type` (Movie or TV Show) using a dropdown when viewing the visualization.

![select_type paramater using the netflix_titles.csv dataset to allow the user to select either Movie or TV Show from a dropdown menu](pictures/select-type-parameter.png?classes=border)
{{% /notice %}}

### Parameter Settings
When creating a parameter, you can define several properties:

1. `Name`: Provide a descriptive name for your parameter, which will be used to reference it in calculations and filters.
1. `Data Type`: Make sure to select the correct data type for your use case. Usually this is in reference to the field that you will be using within the parameter.
1. `Current value`: Initial or default value
1. `Value when workbook opens`: What value should be displayed when the workbook is first opened.
1. `Allowable values`: Select either All values, a list of values, or a range of values to select from.
1. `Value and Display As`: You can changes how each value is displayed within the visualization itself with the display as option.
1. `Add values from`: Select where you want to add values from for the parameter itself, this is usually a field from your data.

### Using Parameters in Calculations
After creating a parameter, you can reference it in your calculations by using the parameter name enclosed in square brackets:

{{% notice blue Example "rocket" %}}
If you have a parameter called `Discount Rate`, you can create a calculated field like the one below:

```console
Sales * (1 - [Discount Rate])
```

This will apply the `Discount Rate` parameter to your sales data.
{{% /notice %}}

### Using Parameters in Filters

Parameters can also be used in filters to dynamically filter your data based on the parameter's value. In the filter dialog, you can reference the parameter in the same way as in calculations, using square brackets.

{{% notice blue Example "rocket" %}}
If you have a parameter called `Start Date`, you can create a filter with a condition:

```console
Date >= [Start Date]
```

The Date will only be returned if it is greater than or equal to the date specified in the `Start Date` parameter.
{{% /notice %}}