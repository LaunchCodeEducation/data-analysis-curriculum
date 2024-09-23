+++
title = "Calculations"
date = 2024-05-28T13:45:19-05:00
draft = false
weight = 1
+++

## Calculations

Applying calculations to your visualization helps further customize, filter, and aggregate data. Calculations can be something as simple as applying an `AVG` or any other aggregate function.

Regardless of what type of calculation you apply to your visualization, we consider the result a **calculated field**.

When a new calculation is created, a new pill will be added to your data pane under the name you provided the calculation. We will cover **basic calculations** and **table calculations** below.

## Basic Calculations

Basic calculations in Tableau revolve around using arithmetic operators and functions to manipulate and transform your data as you see fit. Calculations can be applied to an individual field or multiple fields, allowing you to create new extracted fields based on your analysis requirements.

Take a look at the example below:

{{% notice blue Example "rocket" %}}
```python
AVG([Transaction Total])
```

This would provide you a calculated field pill that would store the `AVG` of the `Transaction Total` field.
{{% /notice %}}

### Calculation Components

When you are creating a new calculation there are some multiple components to familiarize yourself with:
1. Fields: You are able to include existing fields from your data inside of a calculation like in the example above referencing the `Transaction Total` field.
1. Operators: (`>`, `<`, `=`, `>=`, `<=` etc..)
1. Literal expressions: Specific values (`23`, `"String"`, `true`, `false`, null, `#Date`)
1. Functions: Tableau provides a numerous amount of functions that you can apply within your calculated fields. The functions available include aggregate functions, number functions, logical functions, etc..

{{% notice blue Note "rocket" %}}
Tableau documentation provides an exhaustive list available functions included that you will be able to make use of. You can find a list of all [functions included here](https://help.tableau.com/current/pro/desktop/en-us/functions_all_categories.htm).
{{% /notice %}}

You can select or include a function from a list during the process of creating a new calculated field.

1. Click on `Analysis`.
1. Then click on `Create Calculated Field...`.
1. Click on the arrow to expand the list of available functions.

![Creation of a new calculated field within Tableau public, expanding the list of available functions](pictures/tableau-available-functions.png?classes=border)

## Table Calculations

Table calculations in Tableau are a powerful tool for performing calculations on data within a visualization, based on the context of the table or chart. They allow you to create dynamic and informative visualizations which provide insights into your data that would be difficult or impossible to achieve with simple calculations.

Here are a few key concepts to be familiar with in creating table calculations:

* Addressing: Determines the direction in which the calculation is performed. For example, across rows, down columns, or across a specific dimension.
* Partitioning: Defines the groups or subsets of data within which the calculation is applied. This allows you to perform calculations on specific segments of your data.
* Compute Using: Specifies the field or fields that determine the calculation's scope and direction.

Ther are severak common table calculation functions immediate available within Tableau:

* Running Totals: Accumulate values over time or across categories.
* Differences: Calculate the difference between values in adjacent rows or columns.
* Percentages: Calculate percentages of totals or grand totals.
* Moving Averages: Calculate averages over a specific window of data.
* Rank: Rank values within a group or partition.
* Custom Calculations: Create your own calculations using Tableau's built-in functions and operators.

To add a table calculation to a visualization within Tableau:

1. Build your basic visualization using your desired dimension(s) and measure(s).
2. Right-click on the measure you want to calculate and select "Quick Table Calculation" or "Edit Table Calculation."
3. Select the desired calculation type from the options provided.
4. Adjust the addressing, partitioning, and compute using settings to customize the calculation.

<Add the Pluralsight videos Introduction to Calculations in Tableau https://app.pluralsight.com/ilx/video-courses/clips/05067e65-e111-4207-ba59-6067d6edcd1e and Numerical Calculations and Quick Table Functions https://app.pluralsight.com/ilx/video-courses/clips/05067e65-e111-4207-ba59-6067d6edcd1e here>

### Partitioning Fields

When working with table calculations, you can optionally specify one or more **partitioning fields**. Partitioning fields are used to define subsets or partitions of your data, and the table calculation will be performed independently for each partition.

{{% notice blue Example "rocket" %}}
If you have a sales data set with fields like Region, Product, and Sales, you could partition your table calculation by Region to calculate running totals or percentages of totals for each region independently. 

This allows you to analyze and compare values within specific partitions of your data.
{{% /notice %}}

### Addressing Fields

In addition to partitioning fields, table calculations also require you to specify one or more **addressing fields**. Addressing fields determine the order or direction in which the calculation is performed within each partition.

{{% notice blue Example "rocket" %}}
If you have a time-based data set with a `Date` field, you could use `Date` as the addressing field to calculate a running total or moving average over time. The addressing field dictates the order in which the calculation is applied to the values within each partition.

By combining partitioning fields and addressing fields, you can create highly customized and insightful table calculations that provide valuable context and enable deeper analysis of your data.
{{% /notice %}}

<!-- TODO: Add image below of creating table calculation -->

## Conditional Statements

You can utilize a few types of conditional statements within calculated fields. The three types of conditional statements we will cover are `IF` and `IIF` and `CASE` statements.

{{% notice blue Note "rocket" %}}
Each conditional statement has it's own use cases. When comparing the `IIF` to the `IF` statement, the `IIF` statement allows you to specify how unknown values are treated, otherwise they are quite similar.

The `CASE` statement is especially useful if you would like to rename values within a given field. Similar to `IF` statements `CASE` statements are often used to format and filter data. Let's look at a few examples below.
{{% /notice %}}

{{% notice blue Example %}}
`IF` statement syntax:

```python
IF some condition
THEN do this
## ELSE statement is optional
ELSE do this
END
```
{{% /notice %}}

{{% notice blue Example %}}
`IIF` statement syntax

```console
IIF (some condition, do this if true, else this if false, handle unknown)
```
{{% /notice %}}

{{% notice blue Example "rocket" %}}
You have a field named `Operating Systems` that contains the three major types of operating systems (`Linux`, `Windows`, and `MacOS`) but they were represented by numbers within the field instead of the string values. You could create a calculated field like the one below to provide more descript value names:

```python
CASE[Operating Systems]
WHEN 1 THEN "Linux"
WHEN 2 THEN "Windows"
WHEN 3 THEN "MacOs"
END
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Which of the following is NOT one of the four basic components of a Tableau calculation?

1. Functions
1. Level of Detail
1. Fields
1. Operations
<!-- Solution: Level of Detail -->
{{% /notice %}}
