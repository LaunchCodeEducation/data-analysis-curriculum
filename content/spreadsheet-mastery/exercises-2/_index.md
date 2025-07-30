+++
title = "Spreadsheet Mastery: Exercises Part 2"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 3
+++

The Order Summary Report that you submitted last week was well received by your department director and the key stakeholders in external departments.

The stakeholders have requested a set of interactive PivotTables in addition to the static report, so you schedule a meeting with your department director and the interested parties to gather requirements for the build.

## Requirements
1. In Microsoft Excel
1. Focuses on Shipping Status categories
1. One workbook with multiple worksheets, including:
   1. Summary Report for Total Reporting Period (as currently exists)
   1. PivotTables by previously defined categories 
   1. All KPI calculations included
   1. Category slicers
   1. Date timeline selector
   1. Related Charts and Graphs

The specifications are simple. The stakeholders know the information they want to access and how they would like to interact with the data, but they are not particular about the overall design. This leaves the design and build almost entirely to your professional opinion.

You decide to create a mockup of several PivotTable options to review with your department director before you finalize the components that will be included in the final deliverable.

## Your Plan

Use the template file that you kept from last week’s Order Summary Report, add a new worksheet and name it Mockup. Be sure to build all components in this worksheet to keep your template workbook organized. Number formats and field header naming conventions should align with the Summary Report when possible.

Create the following PivotTables:

1. `Order Count`, `Sales $`, `% TTL Orders`, `% TTL Sales $`, `AOV`, `Total Units`, `% TTL
Units`, and `UPT by Status`. Status in rows and values in columns. It should look
like this:

   ![pivot tables required](./pictures/pivot-tables-required.png)

1. Create the same PivotTable with both the status and the values in the rows. Drag values before status and status before values. Decide which view you like best and keep this component. Note to Self: Copy/Paste previous PivotTable and edit pasted copy where applicable to save time.
1. Create the same PivotTable with the values in the rows and the status in the columns.
1. `Order Count by Status`. Status in rows and values in columns.
1. `Sales $ by Status`. Status in rows and values in columns.
1. `Unit Count by Status`. Status in rows and values in columns.
1. `AOV by Date`. Date in rows and values in columns.
1. `UPT by Status`. Status in rows and values in columns.
1. `% Total Orders`, `% Total Sales $`, and `% Total Units` for each status. Status in rows and values in columns.
1. Create another PivotTable identical to Step 1 but replace `Status` with `Fulfillment_Status`.
1. Create another identical PivotTable and add `ship-service-level` as the first category, appearing before `Fulfillment_Status` in the rows. Reorder the categories. Decide which view you like best and keep this component.
1. Create another PivotTable that displays `Order Count by Sales Channel` and then by `Status`. Categories in rows and values in columns.
1. Create another PivotTable that displays `Sales $` and the numerical rank of the `Sales` volume by `Status`. Category in rows and values in columns. Sort this table by `Rank`, largest to smallest.
1. To conceptualize different style options that you might consider for your final dashboard solution, apply different formatting options to each PivotTable using the PivotTable Styles and PivotTable Options menus.
1. As you continue to develop and format components, you realize that you want to use one worksheet per component to make additional room to add Slicers, Timelines, and Charts. Use the Move PivotTable action from the ribbon to move your components to new worksheets, renaming the worksheets to numbers that align with these Step numbers (1,2,3, etc.).
1. Add Category Slicers and Timeline Selectors to each PivotTable. Adjust slicer connections to control only the PivotTable on the related worksheet. Use the formatting menus for the slicers and timelines to design each one differently, aligning these controls with the aesthetic of the PivotTable. Notice how your PivotTables update when different slicer and timeline options are selected.
1. Create PivotCharts for the following PivotTables. Spend time updating the formatting options to best display your visualization, Axis Title, Axis Labels, data labels, etc. Charts should be visually appealing and easy to read. Remember that these charts will update dynamically based on the slicer and timeline selections, so be sure to test the appearance of each before you finalize.
   1. 2-D Pie Chart for PivotTable 4 displaying the `Order Count per Category`. Sort by `Orders`, largest to smallest, and update slicer to only display the top 5 categories.
   1. Column Chart for PivotTable 5 displaying the `Sales $ per Category`. Sort by `Sales $` from largest to smallest.
   1. Line Chart for PivotTable 7 displaying the `AOV` over time. Add a trend line.

Your department director asked that you provide a status update as you build out different component and style options, so you decide to stop here to send the workbook for review.

Upload the Microsoft Excel Workbook to Canvas under *Exercises: Spreadsheet Mastery Part 2*. 
