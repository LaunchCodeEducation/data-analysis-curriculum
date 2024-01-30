+++
title = "Summary Statistics with Google Sheets"
weight = 2
originalAuthorGitHub = "gildedgardenia"
+++

**Summary statistics** (also sometimes referred to as **descriptive statistics**) are the first step in EDA. This term refers to a collection of statistical values that we, as data analysts, need to start uncovering the shape of a dataset. Summary statistics fall into two main categories.

1. **Measures of Central Tendency** also called **Measures of Location**
1. **Measures of Variance** also called **Measures of Spread**

When we are looking for the shape of a dataset, we want to understand whether or not it is symmetrical or asymmetric and how it generally appears in visualizations. Is it a bell curve or is it something else? Is the dataset widely dispersed along the x axis or is it so tightly dispersed it looks like a vertical line? As we begin to investigate these questions, we will also begin to understand what outliers there may be or take away some observations as to what statistical approaches we need to take with this dataset. Remember, EDA isn't about solving the business issue at hand, it is about approaching the dataset without assumptions and beginning to put together the approach we need to take to solve the business issue.

Before we dive into a dataset, let's briefly review what these statistical values are and how to calculate them in Google Sheets.

## Measures of Central Tendency

Measures of central tendency help us understand what value(s) the dataset is grouped around. Statisticians have multiple ways to uncover a dataset's central tendency, but we are going to focus on the top three for now: mean, median, and mode.

### Mean

The **mean** is also called the **average**. It is the sum of all the values divided by the number of values. We can use Google Sheets to find the mean with these steps:

1. Decide what cell you want the mean to be in and click on it.
1. Type `=AVERAGE()` and in the parantheses, put the cell or range of cells you would like to average. To select a range of cells, click and hold on the first cell you want in your range and drag your mouse to the end cell in your range. Alternatively, you can enter `first cell:last cell` in the parantheses for a range of cells.

### Median

The **median** is the midpoint of an ordered list of values and is found differently depending on if the list contains an odd number of values or an even number of values.

1, 2, 3 results in the median being 2 because the position of the median can be found by the sum of the number of values and 1 divided by 2. So 3 values + 1 is 4 and 4 divided by 2 is 2 so we need the second number in the list.

If the dataset was 1, 2, 3, and 4, then we would need to take the sum of the values at n/2 and n/2+1 and divide that sum by 2. So 4/2 is 2 and 4/2+1 is 3, and the second and third numbers are 2 and 3. 2+3 is 5 and 5/2 is 2.5 making the median 2.5.

Google Sheets has a way for us to do this on a larger scale.

1. Select which cell you want to display the median in.
1. Type `=MEDIAN()` and enter the cell or range of cells you would like to know the median of inside the parantheses.

### Mode

The **mode** is the most commonly occurring number in a dataset. If every number only appears once, then we have no mode and that is okay! If there are two numbers that appear at the same frequency and those two numbers are the most commonly occurring numbers in the set, then we have two modes and that is also okay!

To find the mode with Google Sheets, select the cell you want to display the mode in and type `=MODE()` and enter the cell or range of cells you want inside the parantheses.

{{% notice blue Note %}}

If you ever forget how to type out one of these functions, you can also click *Insert* > *Function* > *Statistical* to get the full menu of statistical functions Google Sheets can perform.

{{% /notice %}}

## Measures of Variance 

Measures of central tendency help us understand what value(s) a dataset is grouped around and measures of variance understand how tight that grouping is. Just as with measures of central tendency, statisticians have many ways to discern how widely dispersed a dataset is, but we are going to focus on three ways for now.

### Range

The **range** is the difference between the maximum and minimum values in a dataset. There isn't a range function in Google Sheets so to find the range, we need to type `=MAX()-MIN()` with the cells we need inside both sets of parantheses.

### Interquartile Range

**Interquartile range** or **IQR** is the difference between the upper quartile and the lower quartile in a dataset. A quartile represents the division point between quarters of the dataset when the numbers are ordered in increasing order. The lower quartile is the value where less than 25% of the data lies. The upper quartile is the value where less than 75% of the data lies. The interquartile range is preferred to the range by many statisticians because it increases accuracy, since most outliers can be found below the lower quartile or above the upper quartile. Just like with range, Google Sheets doesn't have an interquartile range function, so we are going to have to take some additional steps.

1. We need to find the lower quartile or Q1. Select which cell you want to display Q1 in and type `=QUARTILE(cells, 1)` with cells being the cells you need for this calculation.
1. Now we need the upper quartile or Q3. Select which cell you want to display Q3 in and type `=QUARTILE(cells, 3)`.
1. We are ready to find the IQR in a third cell by entering the formula `=Q3-cell - Q1-cell` with `Q3-cell` being the cell you chose in step 2 and `Q1-cell` being the cell you chose in step 1.

### Standard Deviation

The **standard deviation** helps us determine how spread the data is from the mean because it is the amount of dispersion of a variable from the dataset's mean. The greater the percentage of data points one standard deviation away from the mean, the less dispersed the data set is. It is found by taking the square root of the sum of a data point minus the mean squared divided by the number of data points. This can be a tedious process to do by hand but fortunately Google Sheets has a rapid way for us to do this. We can just type `=STDDEV(cells)` with the cells we need in parantheses.

Summary statistics are just the beginning of EDA. Time to create some visualizations!

## Check Your Understanding

{{% notice green Question %}}

Measures of _____________ determine what value a dataset is grouped around and measures of _______________ determine how close that grouping is. 

{{% /notice %}}

{{% notice green Question %}}

What is the difference between range and interquartile range?

{{% /notice %}}