+++
title = "Task 2: Hello, Google Sheets!"
date = 2023-05-25T12:55:09-05:00
draft = false
weight = 1
+++

Once you have the Google Sheet open in your browser window, have a look around the various tabs and familiarize yourself with each spreadsheet. Don't be afraid to look - just don't edit anything just yet.

## Car Info Tab

Below, you will find a screenshot of what the `Car Info` spreadsheet currently looks like:

![Image of car info spreadsheet tab within the Hello, Google Sheets! google sheet](pictures/car-info-spreadsheet.png?classes=border)

As mentioned in the [Project Introduction]({{% relref "../project-introduction/_index.md#car-info" %}}) section, the `Car Info` tab contains a monthly and yearly estimate for a total of four cars. In cell K11, you will see that the insurance cost for the 2023 year was $1400. However, insurace premiums have been raised by 12%. Complete the following steps in order to update the insurance costs to the new 2024 price:

1. Within cell J12, type in "Insurance Rate Increase".
1. In cell K12, type in 1.12 to represent the 12% rate increase.
1. In cell J13, type in "2024 Insurance Cost".
1. In cell K13, multiple cell K11 by K12. This will give you an updated cost for your monthly insurance.
1. Now that the insurance rate has been updated, change the forumla within cell I2 to reference the updated 2024 insurance cost.

## Grocery Info Tab

Below you will find a screenshot of what the `Grocery Info` spreadsheet currently looks like:

![Image of the grocery info spreadsheet tab within the Hello, Google Sheets! google sheet](pictures/grocery-info-spreadsheet.png?classes=border)

As mentioned in the [Project Introduction]({{% relref "../project-introduction/_index.md#grocery-info" %}}) section, the `Grocery Info` tab contains categories for groceries purchased at the store, including a weekly cost breakdown for each category. You will notice in cells J12 and K12 the 2023 inflation rates are referenced. In this scenario, inflation had risen by 5% for the 2023 year. However, in 2024 inflation is now at 8%. You will need to adjust the monthly grocery estimate so that it matches the new rates of inflation.

1. Within cell J9, type in "2024 Inflation Rates"
1. In cell K9, type in "0.08" to represent the 8% inflation rate.
1. Cell H2 uses a formula that still references the 2023 inflation rates. Update this formula to match the new rates.

{{% notice green Bonus "rocket" %}}
Cells J1 - M1 provide a budget for the 2023 year. This helped ensure that the monthly spend was within the appropriate range. Create a budget for the 2024 year within the J2 - M2 cell range, referencing the new 2024 inflation rates.
{{% /notice %}}

## Overview Tab

Below is an image of the `Overview` spreadsheet. 

![Image of the overview spreadsheet tab within the Hello, Google Sheets! google sheet](pictures/overview-spreadsheet.png?classes=border)

Now that the data within the `Car Info` tab and the `Grocery Info` tab has been updated we can calculate the monthly and yearly estimates in the `Overview` tab.

1. Within cell B2, reference the Total Monthly Estimate from the `Car Info` spreadsheet using the appropriate forumla.
1. In cell B3, reference the Monthly Grocery Estimate from the `Grocery Info` spreadsheet using the appropriate forumla.
1. Do the same for the yearly car and grocery totals.
1. In cells B10, and B11, use the `SUM` of the monthly car and grocery, and yearly car and grocery to get a combined total for each category.