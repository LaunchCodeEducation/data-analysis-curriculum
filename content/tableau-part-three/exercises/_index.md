+++
title = "Exercises: Tableau Part 3"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

## Getting Started

1. Download this [Bike Sharing in Washington D.C. Dataset](https://www.kaggle.com/marklvl/bike-sharing-dataset).
   
   1. 2 CSV files total. 
  
1. Be sure to read the context and content about this dataset to better understand how and why data was collected.
1. Open the downloaded dataset in Tableau Public.

   1. Create a relationship between the CSV files.
   1. `Dteday` is a shared column between the two tables.
   
1. Create a new Tableau Public project to answer the below questions.
1. We are going to explore dates and create calculations and parameters with our data that answer our business issue.
1. Your final output will be a dashboard with at least 3 of your charts that provides data useful to the business issue.
1. Here are some [other fun facts about the DC Bike sharing program](https://en.wikipedia.org/wiki/Capital_Bikeshare)

### Business Issue: 

The Bike Sharing program did very well in DC and is still popular today.  Your city is interested in 
creating its own bike sharing program.  You have been tasked to see how the first 2 years went in DC to 
anticipate any factors that might affect usability such as weather, seasons, or holidays.

A few questions have been provided to help guide your thoughts in this exercise.

### EDA


1. What hours are these bikes most popular with casual riders?  

   1. What about registered riders?

1. What daily trends do you see between casual riders and registered riders from 2011-2012.

   1. Use `Dteday` and drill down.

### Basic Calculation: 

1. Do holidays impact casual rentals?  
1. What about registered rentals?

   1. Rename `Holidays` from 0 and 1 to “Holiday” and “Non-Holiday” using a calculated field.

1. Does the season increase or decrease usage?  

   1. How does that compare with weather?

1. Use a calculation to rename the `Seasons` that is more useful than a number.  

   1. 1 = Spring
   1. 2 = Summer
   1. 3 = Fall
   1. 4 = Winter

1. Use a calculation to rename the `Weather` so that it is useful to us humans.

   1. 1 = Clear
   1. 2 = Fog or Mist
   1. 3 = Light precipitation
   1. 4 = Heavy precipitation

1. Does the average temp (°F) impact all riders? 1. Use calculations to convert the `Temp` from a “Normalized” scale of 0-1, to °C then finally to °F.
   1. Convert from 0-1 to Celsius using the following formula: **temp = 47 * temp - 8**

      - [Formula source](https://www.andrew.cmu.edu/user/achoulde/94842/homework/homework5.html).

      - Quick Check:  The average temp of Jan 1, 2011 is 46.72°F and the average temp of Feb 1, 2011 is 33.86°F.


### Table Calculation:

1. How many total bike rentals occurred in the city between Jan 2011 to Dec 2012?

   1. What are the running totals of bike rides between 2011-2012?

      a. Hint: You can use a quick calculation for this.

### Parameter: 

1. Duplicate EDA question 1 and create a parameter that will allow a user to choose between hourly casual or registered user usage.

   1. Hint: You are changing a field with a parameter.

### Dashboard & Finesse:

1. Make sure your final dashboard has:

   1. Informative titles, axes, and other text elements.

1. Before submitting your work, reflect on these questions. You don't need to submit any answers for these questions.

   1. Would there be any other data that you wish you had as you worked with this data?
   1. Are you happy with your data visualizations?
   1. Is there anything you would like to learn more about for your future projects?

## Submitting Your Work

When finished make sure to save and publish your work to your Tableau Public account. Copy the URL to your published Tableau project and paste it into the submission box in 
Canvas for **Exercises: Visualization with Tableau Part 3** and click *Submit*.
