+++
title = "Exercises: Data and Variables"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

The following exercises can be worked on within the `data-analysis-projects/data-and-variables/exercises/exercises.py` file!

## The Data

Use the information given below about your space shuttle to complete the
exercises:

| Data | Value |
|-|-|
| Name of the space shuttle | Determination |
| Shuttle Speed (mph) | 17,500 |
| Distance to Mars (km) | 225,000,000 |
| Distance to the Moon (km) | 384,400 |
| Miles per kilometer | 0.621 |

## The Exercises

1. **Declare and assign variables**

   Declare and assign a variable for each item in the list above.
   
   {{% notice blue Note "rocket" %}}
   When declaring and assigning your variables, remember that you will
   need to use that variable throughout the rest of the exercises. Make sure
   that you are using the correct data type!
   {{% /notice %}}

   {{% expand "Check Your Solution" %}}
   ```python {linenos=table}
   shuttle_name = 'Determination'
   shuttle_speed_mph = 17500
   distance_to_mars_km = 225000000
   distance_to_moon_km = 38400
   MILES_PER_KM = 0.621
   ```
   {{% /expand %}}

1. **Print out the type of each variable**

   For each variable you declared in part A, use `type()` to print its type to the console, one item per line.
   
1. **Calculate a space mission!**

   We need to determine how many days it will take to reach Mars.
   
   1. Create and assign a miles to Mars variable. You can get the miles to Mars
   by multiplying the distance to Mars in kilometers by the miles per
   kilometer.

   {{% expand "Check Your Solution" %}}
   ```python
   miles_to_mars = kilometers_to_mars * MILES_PER_KM
   ```
   {{% /expand %}}
   
   1. Next, we need a variable to hold the hours it would take to get to Mars.
   To get the hours, you need to divide the miles to Mars by the
   shuttle's speed.
   
   {{% expand "Check Your Solution" %}}
   ```python
   hours_to_mars = miles_to_mars / shuttle_speed_mph
   ```
   {{% /expand %}}
   
   1. Finally, declare a variable and assign it the value of days to Mars. In
   order to get the days it will take to reach Mars, you need to divide the
   hours it will take to reach Mars by 24.
   
   {{% expand "Check Your Solution" %}}
   ```python
   days_to_mars = hours_to_mars / 24
   ```
   {{% /expand %}}

1. **Print out the results of your calculations**

   Using variables from above, print to the screen a sentence that
   says `"_____ will take ___ days to reach Mars."` Fill in the blanks with 
   the shuttle name and the calculated time.

1. **Now calculate a trip to the Moon**

   Repeat the calculations, but this time determine the number of days it would
   take to travel to the Moon and print to the screen a sentence that says
   `"_____ will take ___ days to reach the Moon."`.

   {{% expand "Check Your Solution" %}}
   ```python {linenos=table}
   miles_to_moon = kilometers_to_moon * MILES_PER_KM
   hours_to_moon = miles_to_moon / shuttle_speed_mph
   days_to_moon = hours_to_moon / 24
   print(shuttle_name + " will take " + days_to_moon + " days to reach the Moon.")
   ```
   {{% /expand %}}

## Submitting Your Work

When finished copy the URL to your GitHub repository for the exercises and paste it into the submission box in Canvas for **Exercises: Data and Variables** and click *Submit*.
