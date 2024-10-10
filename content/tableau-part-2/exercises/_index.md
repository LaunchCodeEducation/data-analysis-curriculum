+++
title = "Exercises: Tableau Part Two"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

## Getting Started

**Due to the size of the dataset we are using, please use the Desktop version of Tableau Public for these exercises**

1. Download this [Hotel Data Set](https://www.kaggle.com/jessemostipak/hotel-booking-demand).  
1. Open the downloaded dataset in Tableau Public. Then, click on Sheet 1 to begin the Extract Creation process.
1. Create a new Tableau Public project to answer the below questions.
   - You should have **8 worksheets** in your project by the time you complete the exercises.
   - For more context and information about the data collected, check out this [article about the data](https://www.sciencedirect.com/science/article/pii/S2352340918315191).

## Part A: Hierarchy

1. What is the total number of adult occupants for all hotel bookings organized by the Reservation Status Date dimension?
   
   1. Drill down to the Months level.

1. What is the average daily rate (Adr) for hotel bookings by customer type compared by the arrival day of the month, week number, and year?

   1. Create a hierarchy using:
      1. Arrival Date Day of Month.
      1. Arrival Date Week Number. 
         - This field may auto import as a dimension. If it does, you will need to convert it to a Measure and change the Data Type to 'Number' 
      1. Arrival Date Year.
      
## Part B: Filtering

1. How many total adult and child occupants were there for bookings between 2015-2017?

   1. Create a filter for “Arrival Date Year” using the either DD or Filter card.

1. What countries had a total of 1,000 or more adult occupants for bookings in 2016?

   1. Hint: set the conditions of your filters.
 
## Part C: Grouping

1. What months had the most number of adult occupants for South American bookings?
   
   1. Create a group of South American countries and place the group on the shelf.
      - The country codes you need for the group are as follows:
         -  ARG, BOL, BRA, CHL, COL, ECU, GUY, PER, PRY, SUR, URY, VEN

1. Which country in South America had the highest number of adult occupants across all bookings?

## Part D: Sets

1. Create a viz that displays the number of bookings that ended up being a 'No-Show', broken down by Deposit Type and Customer Type. 
   1. You will need to create a set using the 'Reservation Status' field

1. Student Choice: Create a hierarchy of sets to explore the ADR of a country you would like to visit.
   1. Start with the continent.
   1. Then a region.
   1. Then the country.  
 
## Submitting Your Work

When finished make sure to save and publish your work to your Tableau Public account. Copy the URL to your published Tableau project and paste it into the submission box in 
Canvas for **Exercises: Visualization with Tableau Part 2** and click *Submit*.

