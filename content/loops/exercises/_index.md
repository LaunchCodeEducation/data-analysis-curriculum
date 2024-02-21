+++
title = "Exercises"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

## For Loop Practice

Open up `for-loop-exercises.py` in `data-analysis-projects/loops/exercises`.

1. Construct `for` loops that accomplish the following tasks:

   1. Print the numbers 0 - 20, one number per line.
   1. Print only the ODD values from 3 - 29, one number per line.
   1. Print the EVEN numbers 12 down to -14 in descending order, one number
      per line.
   1. Print the numbers 50 down to 20 in descending order, but only
      if the numbers are multiples of 3.

   {{% expand "Check your solution" %}}
   For part 1:
   ```python {linenos=table}
   for i in range(21):
   print(i)
   ```

   For part 3:
   ```python {linenos=table}
   for i in range(12, -15, -2):
   print(i)
   ```
   {{% /expand %}} 

## While Loop Practice

Open up `while-loop-exercises.py` in `data-analysis-projects/loops/exercises`.

Define three variables for the LaunchCode shuttle---one for the starting
fuel level, another for the number of astronauts aboard, and the third for
the altitude the shuttle reaches.

1. Construct `while` loops to do the following:

   1. Prompt the user to enter the starting fuel level. The loop should continue until
      the user enters a positive value greater than 5000 but less than 30000. 
   1. Use a second loop to query the user for the number of astronauts
      (up to a maximum of 7). Validate the entry by having the loop continue
      until the user enters an integer from 1 - 7.
   1. Use a final loop to monitor the fuel status and the altitude of the
      shuttle. Each iteration, decrease the fuel level by 100 units for each
      astronaut aboard. Also, increase the altitude by 50 kilometers. (Hint:
      The loop should end when there is not enough fuel to boost the crew
      another 50 km, so the fuel level might not reach 0).

   {{% expand "Check your solution" %}}
   For part 1,

   ```python {linenos=table}
   fuel_level = 0
   num_astronauts = 0
   altitude = 0

   while fuel_level <= 5000 or fuel_level > 30000:
      fuel_level = int(input("Enter the starting fuel level: "))
   ```

   For part 3,

   ```python {linenos=table}
   while fuel_level-100*num_astronauts >= 0:
      altitude += 50
      fuel_level -= 100*num_astronauts
   ```
   {{% /expand %}}

1. After the loops complete, print the result with the phrase, `The shuttle gained an altitude of ___ km and has ___ kg of fuel left.` Fill in the blanks with the altitude and fuel level values.

   1. If the altitude is 2000 km or higher, add "Orbit achieved!"
   1. Otherwise add, "Failed to reach orbit."

   {{% expand "Check your solution" %}}
   ```python {linenos=table}
   if altitude >= 2000:
      ending = 'Orbit achieved!'
   else:
      ending = 'Failed to reach orbit.'

   print('The shuttle gained an altitude of', altitude, 'km and has', fuel_level,'kg of fuel left.', ending)
   ```
   {{% /expand %}} 

## Submitting Your Work

When finished, commit and push your work to GitHub. Copy the URL to your repository and paste it in the submission box on the Canvas assignment page.