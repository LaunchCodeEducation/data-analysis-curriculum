+++
title = "Exercises: Tableau Part Two"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

## Getting Started

1. Download this [Hotel Data Set](https://www.kaggle.com/jessemostipak/hotel-booking-demand).  
1. Open the downloaded dataset in Tableau Public.
1. Create a new Tableau Public project to answer the below questions.
1. You should have **8 worksheets** in your project by the time you complete the exercises.
1. For more context and information about the data collected, check out this [article about the data](https://www.sciencedirect.com/science/article/pii/S2352340918315191).

## Part A: Hierarchy

1. What is the total number of adult hotel bookings according to the Reservation Status Date dimension?
   
   1. Drill down to the Months level.

1. What is the average daily rate by customer type for booking hotels compared to the arrival day of the month, week number, and year?

   1. Create a hierarchy using:
   
      1. Arrival Day of the Month.
      1. Arrival Date of the Week Number.
      1. Arrival Date Year Measures.
      
## Part B: Filtering

1. How many total adults and children booked hotel rooms between 2015-2017?

   1. Create a filter for “Arrival Date Year” using the either DD or Filter card.

1. What countries had a total of 1,000 total adult hotel bookings in 2016?

   1. Hint: set the conditions of your filters.
 
## Part C: Grouping

1. What months were the most popular for adult hotel bookings only in South America?
   
   1. Create a group of South American countries and place the group on the shelf.

1. Which country in South America had the highest number of adult hotel bookings total?

## Part D: Sets

1. What countries have hotel bookings that occurred within 10 days or less of arrival?
   
   1. Hint: Create a conditional.  

      1. You can do this by filtering your set.  
      1. You should see the options: “General”, “Conditional”, and “Top”.
      1. Select “Conditional”, by field and then select the desired field and the operator and the value.

1. Student Choice: Create a hierarchy of sets to explore the ADR of a country you would like to visit.

   1. Start with the continent.
   1. Then a region.
   1. Then the country.  
 
## Submitting Your Work

When finished make sure to save and publish your work to your Tableau Public account. Copy the URL to your published Tableau project and paste it into the submission box in 
Canvas for **Exercises: Visualization with Tableau Part 2** and click *Submit*.

