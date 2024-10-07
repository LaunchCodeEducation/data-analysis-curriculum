+++
title = "Exercises: Tableau Part 1"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

## Getting Started

We will continue working with the [Netflix Movies and TV Shows](https://www.kaggle.com/datasets/shivamb/netflix-shows) dataset from Kaggle. The goal of these exercises will be to create a basic dashboard and expand on some of the columns of data within the Netflix dataset.

If needed, create a connection to the  `netflix_titles.csv` file.

{{% notice blue Note "rocket" %}}
As you work on each of your sheets, think about a descriptive name that you would want to apply to them. This will help when you add them to your dashboard to better understand what each sheet is meant to visualize.
{{% /notice %}}

### Sheet 1: Total of Movies vs TV Shows

The first worksheet will contain a a total count of Movies and TV Shows. We will display this information in a horiztonal bar chart.

1. Drag and drop the `Show Id` pill into the `Columns` shelf.
    - Convert it to a measure of `Count`
1. Add the `Type` pill to the `Rows` shelf.
1. Add the `Rating` pill as a `Color` within the `Marks` card to provide some additional detail on the Movies and TV Shows.
1. Finally, in the Marks section, click the dropdown and select the `Bar` option to ensure our Viz presents the data as a bar chart.
1. Right click the Sheet tab and use the *Rename* option to rename the sheet to this: `Total Count of Movies and TV Shows`


This provides a visual of how many Movies vs TV Shows there are within the given years, and how many Movies and TV shows exist within all available ratings.

### Sheet 2: Release Year and Type

The second worksheet will contain a line graph displaying how many Movies and TV shows were released in the available years.

1. Drag and drop the `Release Year` pill into the `Columns` shelf.
1. Add the `Show Id` pill into the rows shelf and convert it to a measure of `Count`.
1. Add the `Type` pill as a `Color` within the `Marks` card to display both Movies and TV Shows, and when how many of each were released per year.
1. For this viz, we can stick with the `Automatic` viz option in the Marks section. This should render our data as a multi-line chart.
1. Right click the Sheet tab and use the *Rename* option to rename the sheet to this: `Release Years of Movies and TV Shows`

### Sheet 3: Popular Genres

The third and final worksheet that you will create for your dashboard is going to display popular genres among the Movies and TV Shows.

1. Drag and drop the `Show Id` pill into the Marks card as a `Color` and convert it to a measure of `Count`.
1. Add another `Show Id` pill into the Marks card as a `Size` and convert it to a measure of `Count`.
1. Add the `Listed In` pill into the Marks card as a `Label`.

This is a bit too granular for a dashboard as there are many boxes that do not display a label for the associated genre. Let's apply some minor conditional filtering to the `Listed In` pill.

4. Right click on the `Listed In` pill
    - Click on filter
    - Click on the *Condition* section
    - Click *By Field*
    - For the `Field`, select `Listed In`. For the `Aggregation`, select `Count`
    - Under the *Comparison* section select the `>=` option and add `128` as the *Value*.
5. Right click the Sheet tab and use the *Rename* option to rename the sheet to this: `Popular Genres`

   {{% notice blue Note "rocket" %}}
   You will learn more about filtering in the next Tableau lesson, but this serves a brief introduction!
   {{% /notice %}}

### Create a Dashboard

We are introducing dashboards to you now so that you can easily publish your work. 

But, you should know that there are best practices for dashboards that we will cover in a later chapter.

Click on the `Dashboard` tab at the top of your workbook and click `New Dashboard` or click on the `New Dashboard` button on the bottom of your workspace.

1. From inside the `Dashboard` view pane on the left side of the window, under the `Sheets` section, drag and drop your existing `Sheets` into the dashboard view.

{{% notice blue Note "rocket" %}}
Feel free to customize this any way you like!
{{% /notice %}}

## End Result

If you didn't make any customizations after these steps, your dashboard should look similar to the following image:

![Completed dashboard for intro to tableau exercises](pictures/dashboard-example.png?classes=border)

## Submitting Your Work

When finished make sure to save and publish your work to your Tableau Public account. Copy the URL to your published Tableau project and paste it into the submission box in Canvas for **Exercises: Visualization with Tableau Part 1** and click *Submit*.
