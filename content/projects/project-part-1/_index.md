+++
title = "Spreadsheet Mastery Project: Part 1"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 1
+++

The initial review of the Order Summary Report is completed and, as your director promised, additional metrics need to be included in the report. The requirements are clear, so you outline a plan for how to proceed.

## Additional Requirements:
1. Total Sales $ and Total Units for a new category that combines Fulfillment Entity and Shipping Status (Example: Amazon-Shipped)
1. The Total Order Count, Total Sales $, and Total Units for all cancelled orders greater than or equal to the AOV and all cancelled orders less than the AOV
1. The AOV for the Top Destination Zip Code
1. A count of distinct Zip Codes, Cities, and States
1. Sort the Shipping Status section of the report descending by $ Amt
1. We will be reporting this data at a standardized cadence going forward, so please keep your template and submit a static version of the Excel workbook. Include a PDF of the report pages to provide to external departments.

## Your Plan:

1. Use the `CONCAT` function to create a new variable in Column M of the dataset titled Fulfillment_Status. Separate the two variables using a single dash and use the fill option to populate every row in the dataset. Copy the column and paste over it using values-only to keep the data but remove the formulas from the dataset.
1. Use the `UNIQUE` function to return a list of the new Fulfillment Status categories
1. Update the Report Templates to include the additional requirements – it should look like these mock-ups

![Order report template updated](pictures/report-template-updated.png?classes=border)

![Shipping report updated](pictures/shipping-info-updated.png?classes=border)

4. Combine the `COUNTA` and `UNIQUE` functions into a nested function to populate the Total Cities and Total States cells

{{% notice blue Note "rocket" %}}
You need to use `COUNTA` instead of `COUNT` on these non-numeric columns
{{% /notice %}}

5. Combine the `COUNT` and `UNIQUE` functions into a nested function to populate the Total Zip Codes cell
6. Populate the Order Count in the Cancelled By Order Value section of the report using an absolute cell reference to the AOV, the `COUNTIFS` function, and the logical operators `>=` and `<`

{{% notice blue Note "rocket" %}}
Remember to use the & (ampersand) to join the logical operator and the cell reference within the formula like this so that Excel will accept the syntax (">="&$P$53). Also, fill the formula down and simply change the logical operator within the formula bar.
{{% /notice %}}

7. Populate the Sales $ and Units cells using the `SUMIFS` function and the same approach as step 6
8. Populate the Sales $ and Units in the By Fulfillment Status section of the report using the `SUMIF` function and cell references to the Fulfillment Status. Use absolute references where appropriate to allow a fill down of the formula.

{{% notice blue Note "rocket" %}}
Creating a new variable column in the dataset will save a lot of time – would have to use `SUMIFS` for each category as an alternative approach.
{{% /notice %}}

9. Using the Custom Sort option from the tool bar, sort the Shipping Status section of the report Descending by Sales $
10. Even though it isn’t specified but to maintain consistency, apply the same sort to the By Fulfillment Status section
11. On the Order Sample Data worksheet, populate the Top Destination Postal Code AOV using the `AVERAGEIF` function
12. Validate that all calculations returned correct results and double check all text and number formats. Also, double check that all shading and border formatting has been retained. Make any necessary adjustments before submission.

{{% notice blue Note "rocket" %}}
Confirm that all functions from the initial report were retained accurately as you continued to program the added requirements.
{{% /notice %}}

You have confirmed that all data and formatting is correct, and you are ready to submit the report. You know from the added requirements outline that you will need to keep a copy of this template to be used with refreshed data in the future, so you decide to proceed as follows:
- File > Save As > Order Summary Report_mm.dd.yyyy using today’s date in the file name
- Select the entire Summary Report worksheet by clicking the upper left corner of worksheet where the Columns and Rows intersect
- Copy the entire worksheet and paste values only to keep a static copy of the report but remove the functions from within the cells
- Do the same with the Order Sample Data worksheet
- Now that you’ve removed the formulas from the workbook, delete the Data worksheet
- Using the Page Layout menu option and the additional buttons on the ribbon, format each report page by Setting the Print Area to include the surrounding borders, setting the orientation to Landscape and fitting each to one-page
- Export both worksheets to a PDF by navigating to File > Export > Create PDF/XPS > Options > Entire Workbook > OK > Publish
- Verify that your PDF look as you’d expect based on your print and page layout sections
- Verify that your Excel workbook and PDF are both named Order Summary Report_mm.dd.yyyy

## Submission

Upload three documents (template workbook, static report workbook, PDF) to Canvas under *Spreadsheet Mastery Project: Part 1* and click Submit.
