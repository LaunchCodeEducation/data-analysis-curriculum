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

The first worksheet will contain a a total count of Movies and TV Shows.

1. Drag and drop the `Show Id` pill into the `Rows` shelf.
    - Convert it to a measure of `Count`
1. Add the `Type` pill to the columns shelf.
1. Lastly, add the `Rating` pill as a `Color` within the `Marks` card to provide some additional detail on the Movies and TV Shows.

This provides a visual of how many Movies vs TV Shows there are within the given years, and how many Movies and TV shows exist within all available ratings.

### Sheet 2: Release Year and Type

The second worksheet will contain a line graph displaying how many Movies and TV shows were released in the available years.

1. Drag and drop the `Release Year` pill into the columns shelf.
1. Add the `Show Id` pill into the rows shelf and convert it to a measure of `Count`.
1. Add the `Type` pill as a `Color` within the `Marks` card to display both Movies and TV Shows, and when how many of each were released per year.

### Sheet 3: Popular Genres

The third and final worksheet that you will create for your dashboard is going to display popular genres among the Movies and TV Shows.

1. Drag and drop the `Show Id` pill into the Marks card as a `Color`.
1. Add another `Show Id` pill into the Marks card as a `Size`.
1. Add the `Listed In` pill into the Marks card as a `Label`.

This is a bit too granular for a dashboard as there are many boxes that do not display a label for the associated genre. Let's apply some minor conditional filtering to the `Listed In` pill.

4. Right click on the `Listed In` pill
    - Click on filter
    - Click on the *Condition* section
    - Click *By Field*
    - Under the *Comparison* section select the `>=` option and add `128` as the *Value*.

   {{% notice blue Note "rocket" %}}
   You will learn more about filtering in the next Tableau lesson, but this serves a brief introduction!
   {{% /notice %}}

### Create a Dashboard

Click on the `Dashboard` tab at the top of your workbook and click `New Dashboard` or click on the `New Dashboard` button on the bottom of your workspace.

1. Drag and drop your existing `Sheets` into the dashboard view.

{{% notice blue Note "rocket" %}}
Feel free to customize this any way you like!
{{% /notice %}}

## End Result

Your dashboard will most likely look similar to the following image:

![Completed dashboard for intro to tableau exercises](pictures/dashboard-example.png?classes=border)

## Submitting Your Work

When finished make sure to save and publish your work to your Tableau Public account. Copy the URL to your published Tableau project and paste it into the submission box in Canvas for **Exercises: Visualization with Tableau Part 1** and click *Submit*.