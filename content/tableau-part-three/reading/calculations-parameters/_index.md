+++
title = "Calculations and Parameters"
date = 2024-05-28T13:45:19-05:00
draft = false
weight = 1
+++

## Calculations

Applying calculations to your visualization helps further customize, filter, and aggregate data. Calculations can be something as simple as applying an `AVG` or any other aggregate function. Others may be more complex and have an aggregate function within a condition:

```console
IF condition..
THEN do this
ELSE do this
END
```

Regardless of what type calculation you are applying to your visualization it is considered a **calculated field**.

When a new calculation is created, a new pill will be added into your data pane under with the name you provided to the calculation.

### Calculation Components

When you are creating a new calculation there are some multiple components to familiarize yourself with:
1. Fields: You are able to include existing fields from your data inside of a calculation
1. Operators: (`>`, `<`, `=`, `>=`, `<=` etc..)
1. Literal expressions: Specific values (`23`, `"String"`, `true`, `false`, null, `#Date`)
1. Functions: Similar to Python and SQL functions you can also create functions for any task that you may need to repeat often.

Fortunately, Tableau comes with a lot of functions included that you will be able to make use of. You can find a list of all [functions included here](https://help.tableau.com/current/pro/desktop/en-us/functions_all_categories.htm).

You can also select a pre-built function from a list when you are creating a new calculated field.

1. Click on `Analysis`.
1. Then click on `Create Calculated Field...`.
1. Click on the arrow to expand the list of available functions.

![Creation of a new calculated field within Tableau public, expanding the list of available functions](pictures/tableau-available-functions.png?classes=border)

### Basic Calculations



### Table Calculations

**Table calculations** are applied to any value that is already visualized. 

## Parameters

**Parameters** allow fo more fine-tuned control over calculations that you would like to apply to any part of your visualization. For example, if you would like to divide multiple measures by a specific amount, you can create a new calculation and then attach or include your parameter within. 

One of the major benefits is that you can change your parameter value on the fly so that your calculations will be updated dynamically wherever they exist. Only having to change one value instead of many to view a different result is extremely convenient.

At it's core a parameter is a variable that can be referenced inside of a calculation, filter, or reference line.

### Creating a Parameter
