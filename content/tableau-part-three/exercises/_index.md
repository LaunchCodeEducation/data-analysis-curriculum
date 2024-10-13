+++
title = "Exercises: Tableau Part 3"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

## Getting Started

1. Download this [Bike Sharing in Washington D.C. Dataset](https://www.kaggle.com/marklvl/bike-sharing-dataset).
   - 2 CSV files total (`day.csv` and `hour.csv`). 
  
1. Please read the context and content about this dataset to better understand how and why data was collected.
1. Open the downloaded dataset in Tableau Public. Create a relationship between the CSV files using the `Dteday` field.
   
1. Create a new Tableau Public project to answer the questions in this exercise.
1. We are going to explore dates and create calculations and parameters with our data that answer our business issue.
1. Your final output will be a dashboard with at least 3 of your charts that provides useful data that addresses the business issue.
1. Here are some [other fun facts about the DC Bike sharing program](https://en.wikipedia.org/wiki/Capital_Bikeshare)

### Business Issue: 

The Bike Sharing program did very well in DC and is still popular today.  Your city is interested in 
creating its own bike sharing program.  You have been tasked to see how the first 2 years went in DC to 
anticipate any factors that might affect usability such as weather, seasons, or holidays when implementing the program.

A few questions have been provided to help guide your thoughts in this exercise. 

Remember, sometimes we may want to report on a field as a Measure AND a Dimension. 

**We can do this by creating a duplicate of the original field and renaming it to be either `field name - measure`, `field name - dimension`, or your own custom name depending on your use case.**

### EDA

1. What hours are these bikes most popular with casual riders? What about registered riders?

1. What daily trends do you see between casual riders and registered riders from 2011-2012? Feel free to create multiple sheets to investigate different aspects of the data. Use the `Dteday` field and drill down to investigate.

### Basic Calculation: 

1. Create these calculated fields and give them relevant names:
   1. Use a calculation to rename `Holiday` field values from numbers to the strings below:
      - 0 = Holiday
      - 1 = Non-Holiday
   1. Use a calculation to rename the `Season` field values from numbers to the strings below:  
      - 1 = Spring
      - 2 = Summer
      - 3 = Fall
      - 4 = Winter
   1. Use a calculation to rename the `Weathersit` field values from numbers to the strings below:
      - 1 = Clear
      - 2 = Fog or Mist
      - 3 = Light precipitation
      - 4 = Heavy precipitation


2. Then answer these questions:
   1. Do holidays impact casual rentals? What about registered rentals?  
   1. How does the season affect the usage of the program? How is usage affected by the day's average weather?
   1. Does the average daily temperature (°F) impact average riders? Use a single calculated field to convert the `Temp` from a “Normalized” scale of 0-1 to °C, then finally to °F.
      - Convert from 0-1 to Celsius using the following formula: **celsius = 47 * temp - 8**
      - Then, convert the new Celsius value to Fahrenheit using this formula: **(celsius × 9/5) + 32 = fahrenheit**
         - [Formula source](https://www.andrew.cmu.edu/user/achoulde/94842/homework/homework5.html).
         - Quick Check:  The average temp of Jan 1, 2011 is 46.72°F and the average temp of Feb 1, 2011 is 33.86°F

### Table Calculation:

1. How many total bike rentals (`cnt` field) occurred in the city between Jan 2011 to Dec 2012? Then, what is the running total for bike rides between 2011-2012?
   - Hint: You can use a table calculation for this.

### Parameter: 

1. Duplicate EDA question 1 and create a parameter that will allow a user to choose between the total of casual or registered user usage, grouped by the `Hr` field.
   - Hint: You are changing a field with a parameter.

### Dashboard & Finesse:

1. Make sure your final dashboard has:
   - Informative titles, axes, and other text elements.

1. Before submitting your work, reflect on these questions. You don't need to submit any answers for these questions.
   - Is there any other data that you wish you had as you worked with this dataset?
   - Are you happy with your data visualizations?
   - Is there any Tableau features you would like to learn more about for your future projects?

## Submitting Your Work

When finished make sure to save and publish your work to your Tableau Public account. Copy the URL to your published Tableau project and paste it into the submission box in 
Canvas for **Exercises: Visualization with Tableau Part 3** and click *Submit*.
