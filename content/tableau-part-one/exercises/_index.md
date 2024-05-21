+++
title = "Exercises: Tableau Part 1"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

## Getting Started

The following exercise steps are based on the following [World Happiness Dashboard](https://towardsdatascience.com/world-happiness-dashboard-in-tableau-4dc504212288) Medium article to create a Tableau dashboard. This walkthrough uses the [World Happiness Dataset](https://www.kaggle.com/unsdsn/world-happiness?select=2019.csv) on Kaggle.

## Step-by-step Guide for this Walkthrough

As you work through the steps below, do not hesitate to experiement and try things out!

### Download the Dataset

1. Download the `2019.csv` file from the Kaggle dataset.

### Viz 1: Happiness Score of Countries — 2019

1. Create a Map.   
    - Drop the **Latitude** pill into the *Rows* shelf.
    - Drop **Longitude** pill into *Columns* shelf.
    - Drop **Country or region** onto the *Marks Card* as a *Detail*.
    - Select **Score** and drag it onto the *Color* box contained in the *Marks* card.
    - Rename your sheet: either double click on “Sheet 1” in the View or right click on the Sheet tab to update the name.
        - If only updating the view, the sheet tab name will not change. 
      
### Viz 2: Happiness Score vs GDP and Healthy Life Expectancy

1. Add a new worksheet to your workbook
1. Within the new worksheet, drag **Score** onto the *Row* shelf.  
   - It will automatically aggregate as a SUM of Score.
   - To remove that, find the drop down menu on the right side of the pill and select “Dimension”.
1. Drag **GDP per capita** onto the *Columns* shelf.  
   - Convert this into a “Dimension”, too.   
1. Drag the **Healthy Life Expectancy** into the *Color* box found in the *Marks* card.
1. Rename your sheet.

### Viz 3: Freedom and Social Support vs Score

1. Add another new worksheet to your workbook.
1. Within the new worksheet, drop **Score** into the *Columns* shelf.  
   - Within the **Score** pill, find the drop down menu and select “Dimension”.
1. Drag the **Freedom to make life choices** pill onto the *Rows* shelf.
   - Notice that it changed to a SUM - keep it this way.
1. Drag the **Social Support** pill onto the *Row* shelf.
   - Notice that is also now a SUM - keep it this way.
1. To rename an axis, double-click on it and make the changes desired.
1. Rename your sheet.

### Make a Dashboard

1. Use the tab to create a new dashboard.
1. Drag your sheets onto the dashboard.
   
{{% notice blue Note "rocket" %}}
If you only renamed the sheets within your view, the tabs will not have changed.  This is okay.  You can either update the tab names now or work with Sheet 1, Sheet 2, and Sheet 3.  
{{% /notice %}}

## End Result

![Dashboard result from exercise walkthrough](pictures/tableau-dashboard.png?classes=border)

## Submitting Your Work

When finished make sure to save and publish your work to your Tableau Public account. Copy the URL to your published Tableau project and paste it into the submission box in Canvas for **Exercises: Visualization with Tableau Part 1** and click *Submit*.