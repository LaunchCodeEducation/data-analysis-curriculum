+++
title = "Spreadsheet Mastery Project: Part 1 - Expanded Order Summary Report"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 1
+++

## Scenario

The initial review of your Order Summary Report from the Spreadsheet Mastery Exercises is completed and, as your director promised, additional metrics need to be included in the report. The feedback was positive, with stakeholders particularly appreciating the comprehensive analysis and professional presentation from your original exercise work.

However, they identified several gaps in the analysis that need to be addressed for the report to fully meet their decision-making needs. Your director has compiled the feedback into clear additional requirements and asked you to enhance the existing report while maintaining the established template structure for future use.

## Requirements

Building on your existing Order Summary Report from the Spreadsheet Mastery Exercises, add the following enhancements:
1. Total Sales $ and Total Units for a new category that combines Fulfillment Entity and Shipping Status (Example: Amazon-Shipped)
1. The Total Order Count, Total Sales $, and Total Units for all cancelled orders greater than or equal to the AOV and all cancelled orders less than the AOV
1. The AOV for the Top Destination Zip Code
1. A count of distinct Zip Codes, Cities, and States
1. Sort the Shipping Status section of the report descending by $ Amt
1. We will be reporting this data at a standardized cadence going forward, so please keep your template and submit a static version of the Excel workbook. Include a PDF of the report pages to provide to external departments.

## Learning Objectives

By completing this project, you will:

- Create calculated columns using CONCAT function for data transformation
- Apply nested functions (COUNTA/UNIQUE, COUNT/UNIQUE) for advanced data analysis
- Use conditional counting and summing functions (COUNTIFS, SUMIFS) with logical operators
- Implement custom sorting for professional report presentation
- Export workbooks to multiple formats (template, static, PDF) for different stakeholder needs
- Validate complex calculations across multiple report sections

## Tasks

**Starting Point:** Use your completed Order Summary Report workbook from the Spreadsheet Mastery Exercises as the foundation.

### 1. Data preparation and enhancement:

   - Create a new Fulfillment_Status column (Column M) using the CONCAT function to combine Fulfillment Entity and Shipping Status with a dash separator
   - Apply the formula to all dataset rows using fill option
   - Convert formulas to static values using copy and paste values-only to optimize workbook performance
   - Generate a list of new Fulfillment Status categories using the UNIQUE function

### 2. Update report templates:
   - Modify the Summary Report and Sample Order Data templates to accommodate the new requirements
   - Follow these updated mock-ups for the enhanced layout:

![Order report template updated](pictures/report-template-updated.png?classes=border)

![Shipping report updated](pictures/shipping-info-updated.png?classes=border)

### 3. Calculate distinct location counts:
   - Use nested COUNTA and UNIQUE functions to populate Total Cities and Total States cells

   - Use nested COUNT and UNIQUE functions to populate the Total Zip Codes cell (use COUNT for numeric zip codes)

### 4. Analyze cancelled orders by value:
   - Calculate Order Count for cancelled orders using COUNTIFS with absolute cell reference to AOV and logical operators (>= and <)
   - Use ampersand (&) to join logical operators with cell references: (">="&$P$53)
   - Calculate Sales $ and Units using SUMIFS with the same logical approach
   - Fill formulas down and modify operators as needed

### 5. Calculate fulfillment status metrics:
   - Populate Sales $ and Units in the By Fulfillment Status section using SUMIF with cell references
   - Use appropriate absolute references to enable formula fill-down functionality
   - Leverage the new Fulfillment_Status column to simplify calculations

### 6. Apply professional sorting and formatting:
   - Sort the Shipping Status section descending by Sales $ using Custom Sort
   - Apply consistent sorting to the By Fulfillment Status section for uniformity
   - Calculate Top Destination Postal Code AOV using AVERAGEIF function on the Sample Order Data worksheet

### 7. Validate and finalize:
   - Verify all calculations return accurate results
   - Check text and number formatting consistency
   - Confirm all shading and border formatting is retained
   - Validate that original report functions remain accurate alongside new requirements

### 8. Create multiple deliverable formats:

Since this report will be used at a standardized cadence going forward, create multiple versions for different purposes:

**Template Workbook (for future use):**
- Keep your original workbook with all formulas intact
- Save as "Order Summary Report Template_Your Name"

**Static Report Workbook:**
- File > Save As > "Order Summary Report_mm.dd.yyyy" using today's date
- Select entire Summary Report worksheet (click upper left corner where columns and rows intersect)
- Copy and paste values only to remove formulas while keeping calculated results
- Repeat for Order Sample Data worksheet
- Delete the Data worksheet since formulas are now static values

**Professional PDF Export:**
- Set Print Area to include surrounding borders for both worksheets
- Set orientation to Landscape and fit to one page
- Export to PDF: File > Export > Create PDF/XPS > Options > Entire Workbook > OK > Publish
- Verify PDF formatting matches your print layout expectations
- Ensure PDF is named "Order Summary Report_mm.dd.yyyy"

## Submission

Upload three documents to Canvas under *Spreadsheet Mastery Project: Part 1*:

1. **Template workbook** (with formulas intact for future data refreshes)
2. **Static report workbook** (with calculated values only, named with date)
3. **PDF report** (for external department distribution)

**Before submitting, confirm:**
- All enhanced calculations are accurate and properly formatted
- Static workbook contains values only (no formulas)
- PDF displays correctly with professional layout
- All three files are properly named and formatted
