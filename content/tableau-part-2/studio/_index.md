+++
title = "Studio: Data Preparation"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 3
+++

## Getting Started

### Background

This dataset used in this studio was created by the Institute of Museums and Library Services (IMLS).  We 
will be exploring data from the Fiscal Year 2014.  Documentation of this survey can be found [here](https://www.imls.gov/sites/default/files/fy2014_pls_data_file_documentation.pdf) if you would like to learn more about the survey.  The survey collected data for each state and the District of Columbia.

### Working Through the Studio

You will be placed into one of eight groups.  The group number reflects the region you have been assigned in the table below.  As a team, one group member can be in charge of Tableau and screen share while other group members provide direction and suggestions.  At the end of the studio, you will present your favorite chart or final dashboard to the class as a whole.

While this is a group assignment, for your own portfolio it is recommended that you make your own version of this studio.

### Setting Up the Studio

Download the [library data set](https://www.kaggle.com/imls/public-libraries?select=libraries.csv%C2%A0). There are 2 CSV files. To download all CSV files at once, click on the "Download" bubble next to the "New Notebook" bubble.  An orange arrow is pointing to the "Download" bubble in the image below.

1. Open the CSV file in Tableau Public.  

   1. It is a larger file than we have previously used and may take a few minutes to open. 

1. When you open this data set, you will want to create a relationship between the `libraries.csv` file and the `states.csv` file using branch libraries.
1. Part A invites you to briefly explore the data set.  You will explore all the regions of the US.
1. In Part B, using your assigned region, you will be asked to answer questions using the collection type of your choice: a set or group.  
1. In Part C,  you will select 2 (or more) of your favorite charts and create a dashboard that highlights results from your selected region.
1. Final outcome of this studio will include 9 worksheets (10 if you do the bonus) and 1 dashboard.
  
| **US Regional Codes Table** | **State Names and Abbreviations** |
|-----------------------------|-----------------------------------|
| Region Code 1 - New England | Maine (ME), New Hampshire (NH), Vermont (VT), Massachusetts (MA), Connecticut (CT), Rhode Island (RI) |
| Region Code 2 - Mideast | New York (NY), Pennsylvania (PA), Maryland (MD), New Jersey (NJ), Delaware (DE), Washington DC (DC) |
| Region Code 3 - Great Lakes | Wisconsin (WI), Illinois (IL), Indiana (IN), Michigan (MI), Ohio (OH) |
| Region Code 4 - Plains | Missouri (MO), Kansas (KS), North Dakota (ND), South Dakota (SD), Minnesota (MN), Iowa (IA), Nebraska (NE) |
| Region Code 5 - Southeast | Virginia (VA), West Virginia (WV), North Carolina (NC), South Carolina (SC), Georgia (GA), Florida (FL), Alabama (AL), Mississippi (MS), Louisiana (LA), Arkansas (AK), Tennessee (TN), Kentucky (KY) |
| Region Code 6 - Southwest | Arizona (AZ), New Mexico (NM), Oklahoma (OK), Texas (TX) |
| Region Code 7 - Rocky Mountain | Idaho (ID), Montana (MT), Wyoming (WY), Colorado (CO), Utah (UT) |
| Region Code 8 - Far West | Alaska (AK), Washington (WI), Oregon (OR), California (CA), Nevada (NV), Hawaii (HI) |

[Source](https://www.bea.gov/news/2015/gross-domestic-product-state-advance-2014-and-revised-1997-2013/regional-maps)

## Part 1: EDA

 Use data from the states.csv table unless otherwise noted.  

 In this section, we are looking nationwide.

 Create a viz for each of the following questions: 

1. How many visits occurred in each region?  
   
   1. How does that compare to circulation transactions?

1. Compare Library Programs against State Population.

   1. Try something other than a bar chart.
   1. Explore the marks card.  Add at least one feature.

1. How many visits in each region compared to the End Date?

   1. Hint: Use the End date from the `libraries.csv` file.

      1. Pull other elements from the `states.csv` file.
      1. Hide the `Null` values in your final viz.
      
   1. Use the US Regional Codes Table above to create aliases for each region. 
   
      1. Hint: Rename the Region only at this time. 
      1. Don't worry about states right now.

## Part 2: Collect Your Data

Begin working with your assigned region. Remember to use the table above to help with managing and organizing your data and use data from the `states.csv` table unless otherwise noted.

Create collections to hold your data:

1. Set Your Data.

   1. Select your region as a set.  

      1. We are going to compare your region to the rest of the US. 
      1. Give this set a name so that you can easily find and use it.
 
1. Group Your Data.

   1. Group the states within your region as a whole.
    
      1. Give this group a name.  
      1. If you used the “State Code” field for your group, you will need to create aliases for the state number to either the name or abbreviation.
      1. For example, “51” becomes “Virginia” or “VA”.
      1. See [document page D-44](https://www.imls.gov/sites/default/files/fy2014_pls_data_file_documentation.pdf) for the state codes.

   1. Group the states individually.
   
      1. Give this group a name.

1. Organizing Your Collections.

   1. If you want to create a hierarchy to better organize your data or drill down at some point, this is your choice.  
   
      1. You can create vizzes with or without hierarchies.  
      1. It is your choice. 

**Questions to Answer with a Viz**

Now that you have organized your data, you are ready to explore your region.

Create a new worksheet for each question using either your sets or groups.

1. How many Central Libraries vs Branch Libraries are in each state within your region?

   1. How many bookmobiles?
   1. Add a tooltip or make an interactive filter card.

1. How many Young Adult (YA) library programs does each state in your region host and how many individuals attend?

   1. Add a detail and a label to this viz. 

1. Between Central Libraries and Branch Libraries in your region, how many employees are Librarians?

   1. Use the marks card to show data about Librarians.

1. How many Librarians hold an MLS degree in your region compared to the rest of the US?

   1. Compared to how many Total Staff?
   1. Use a new chart format (if possible).

1. How do circulation transactions compare between your region and the rest of the US over 2013-2014?

   1. Hint: Use the End Date pill.  Hide any Null values, we only want reported values at this time. 
   1. Add a label.

## Part 3: Create a Dashboard

Create a dashboard that highlights at least 2 of your favorite charts from the studio.  (The bonus can be one of these).

## Bonus Mission

Using the spacial files to create a map, create a viz to answer the following question:

1. Within your region, how many children's programs were distributed by a state by county?

   1. Hint: Drag the State (`states.csv`) file into the central plane, and use the `Marks` card.  
   
      1. Be sure to filter.
      
   1. Hint: County is a dimension found in the libraries.csv table.
 

## Finishing Touches

Before you turn in your vizzes:

1. Make sure that they are easy to read. 
1. Review and edit any axes so that they don't contain any file information. 
1. Make sure any filtering, group, or set information is easy to understand. 

   1. For example, when using a set the predefined labels may say “In” and “Out”. Would extra context make them easier to understand? 
   1. Don't forget to title your charts.  

1. If you want to explore fonts and colors, go right ahead. 

   1. Feel free to change the colors of any/all of your charts.  


## Submitting Your Work

When finished make sure to save and publish your work to your Tableau Public account. Copy the URL to your published Tableau project and paste it into the submission box in 
Canvas for **Studio: Visualization with Tableau Part 2** and click *Submit*.
