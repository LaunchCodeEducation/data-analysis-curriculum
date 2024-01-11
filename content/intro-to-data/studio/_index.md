+++
title = "Studio: Introduction to Data"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 3
+++

## Getting Started

You will be working in a small group to discuss a potential data analysis project. Your course staff 
will give each group a scenario which outlines the business issue and what data you have at your 
disposal. Before you dive in, give everyone in your group time to read through the scenario and 
discuss it so that everyone is on the same page. Don't hesitate to ask course staff any questions you 
may have about your scenario! Use the Exercises as a guide for the discussion and make sure to leave 
yourselves time to put together a small presentation reviewing your discussion for the class.


In your presentation, make sure to include:

1. The problem the business owner is trying to solve.

1. Available data sources? What kind of information do we need?

1. What would you need/do to prepare the data? Problems with the data?

1. Talk about exploratory analysis and KPIs.

1. Discuss what would make your results valid/invalid.

1. Who are the stakeholders and how would you present your findings?

## Scenarios

### Scenario 1: Knitting Influencer

Cierra is a young woman in her 20s. She has over 250,000 followers on her knitting instagram, @cierraknits. She and her manager want to take a closer look at where she is earning money and how much. They are tasking you with figuring out if Cierra makes more money writing and selling her knitting patterns herself on Ravelry or writing knitting patterns for sponsors, such as Yarniverse, which are offered through their site. Cierra and her manager are also wondering if factors such as time it takes her to finish a project and whether or not a sponsor gifts her the yarn have an impact. At the end of the project, you will be presenting your findings to Cierra and her manager. 

#### Data Sets

1. Yarn Stash:
    - `Columns:` Brand, Yarn name, Color Name, Dye Lot, Credit
    - `Example:` Red Heart, Super Saver,  Pool, NULL, Gifted By Red Heart

1. Patterns Written
    - `Columns:` Name, Category, Published, Downloads, Location, Yarn Used, Quantity Used, Total Profit
    - `Example:` Fall Afternoon, Scarf, 9/24/2020, 5001, Ravelry, Caron Simply Soft, 2 balls, $25,000

1. Sponsors
    - `Columns:` Name, Relationship Start Date, Relationship End Date, Total Income
    -`Example:` Yarniverse, 5/6/2018, N/A, $10,000

1. Knitting Log
    - `Columns:` Project Name, Type, Yarn Used, Start Date, End Date, Notes
    - `Example:` Funky Sweater, Sweater, Lost the label :(, 6/8/2019, 6/19/2019, Still mad that I lost the yarn label

1. Posts
    - `Columns:` Post Number, Sponsored?, Current Likes, Current Comments, Notes
    - `Example:` 256, Yes, 67890, 720, This post did really well! Posted at 8 AM and got tons of activity in the first hour

### Scenario 2: Farmer's Market

Shelley is in her mid-50s and owns a stall at her local farmer's market selling produce. Beng a small business owner, Shelley is handling everything herself and is hoping to better allocate her remaining resources this year to make the most profit. She is enlisting you to help predict the demand for next year’s crops so she knows what to expect. At the end of the project, you will be presenting to Shelley.

#### Data Sets

1. Sales
    - `Columns:` Date, Customer Name, Items Sold, Total Sale
    - `Example:` 7/28/2021, Bill, 6, $14.75

1. Seed Log
    - `Columns:` Company, Crop, Variety, Quantity, Notes
    - `Example:` Heirloom Seeds Co, Tomatoes, Red, 6, This grew really well last year

1. Time to Grow
    - `Columns:`  Crop, Variety, Time to Grow
    - `Example:` Tomatoes, Red, 3 months

1. Resources Used
    - `Columns:` Crop, Variety, Water Used, Fertilizer Used
    - `Example:` Tomatoes, Red, 10 gallons, 2 oz.

1. Yield per Year
    - `Columns:` Crop, Variety, Year, Crop Yield
    - `Example:` Tomatoes, Red, 2020, 10 lbs

### Scenario 3: Department Chair

Dr. Jacobsen recently became the head of her department at a prestigious university. She is trying to get more students interested in her department and has asked you to run the numbers so she can figure out what courses to offer next year. At the end of the project, you will be presenting to Dr. Jacobsen and her department. 

#### Data Sets

1. Past Enrollments
    - `Columns:` Course Name, Section Number, Professor, TA, Students Enrolled, Students Withdrawn, Students Dropped, Students Completed
    - `Example:` Ecosystems, 2, Dr. Crispin, Ms. Moon, 54, 3, 2, 49

1. Past Course Offerings
    - `Columns:` Course Name, Sections Offered, Notes 
    - `Example:` Agriculture, 1, Students did not enroll when offered at 8 AM

1. Current Staff
    - `Columns:` Name, Level, Specialty
    - `Example:` James Crispin, Tenured Professor, Ecology

### Scenario 4: Local Zoo and Utility Company

Dan is a representative for a local utility company who has been working with Erin at the local zoo. Erin is head of the elephant department and has been giving the elephants tree boughs removed by Dan and their team. The elephants love the treats and it has helped the zoo save a few dollars! Dan and Erin are trying to plan for next year so Erin can begin to put together her budget for elephant care. They have asked you to assist! At the end of the project, you will be presenting to Erin, Dan, and the boards of both the utility company and the zoo. 

### Data Sets

1. Elephants 
    - `Columns:` Name, Age, Weight, Height, Sex, Species, Dietary Notes
    - `Example:` Ruthie, 1, 13,000 lbs, 10 ft., F, Loxodonta africana, Loves tree boughs!

1. Vegetation removed per year
    - `Columns:` Species, Quantity Removed
    - `Example:` C. illinoinensis, 500 lbs.

1. Utility Tree Trimmers
    - `Columns:` Name, Time at Company, Vegetation Removed each Year
    - `Example:` Cynthia, 5 years, 300 lbs.

### Scenario 5: Butterfly Gardens

Butterfly garden activist, Summer, took over leadership of a small nonprofit during her retirement. She and her staff are hoping to encourage the migration of 3 endangered butterfly species through the area by planting and maintaining gardens on the migratory path. At the end of your work, you will be presenting to Summer and her staff.

#### Data Sets

1. Butterfly Species
    - `Columns:` Name, Lifespan, Seen Last Year?, Season, Notes
    - `Example:` Monarch Butterfly, 2-6 weeks, Yes, August, Loves milkweed!

1. Flowers
    - `Columns:` Name, Did Well Last Year?, Notes
    - `Example:` Milkweed, Yes, Didn't grow as well at the 5th avenue location

1. Current Garden Locations
    - `Columns:` Address, Flowers, Butterflies Seen, Notes
    - `Example:` 123 5th avenue, Milkweed and Daisies, Monarchs, Renting the space from current landowner

1. Potential locations
    - `Columns:` Address, Site Notes
    - `Example:` 123 4th avenue, Would be a great spot for more milkweed!

1. Volunteers/staff
    - `Columns:` Name, Time Spent, Level, Hours Worked
    - `Example:` Juanita Rodriguez, 6 years, senior volunteer, 500 hours

## Submitting Your Work

When finished with the studio, upload the document you created into the submission box in Canvas for **Studio: Intro To Data** and click *Submit*.