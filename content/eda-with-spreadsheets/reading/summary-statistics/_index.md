+++
title = "Summary Statistics with Google Sheets"
weight = 2
originalAuthorGitHub = "gildedgardenia"
+++

Summary or descriptive statistics are the first step in EDA. This term refers to a collection of statistical values that we, as data analysts, need to begin our exploration.

1. Measures of central tendency also called measures of location
1. Measures of variance also called measures of spread

These statistical values help us start to understand the shape of a dataset. Is it a bell curve or is it something else? Is the dataset widely dispersed along the x axis or is it a tighter bell curve? As we begin to investigate these questions, we will also begin to understand what outliers there may be or take away some observations. Remember, EDA isn't about solving the business issue at hand, it is about approaching the dataset without assumptions and beginning to put together the approach we need to take to solve the business issue.

## Measures of Central Tendency

### Mean

The mean is also called the average. It is the sum of all the values divided by the number of values. For example, if we had a dataset of three values, 1, 2, and 3, the mean would be the sum of those values, 6, divided by 3 so 2.

We can use Google Sheets to quickly find the mean.

### Median

The median is the midpoint of an ordered list of values and is found differently depending on if the list contains an odd number of values or an even number of values.

1, 2, 3 results in the median being 2 because the position of the median can be found by the sum of the number of values and 1 divided by 2. So 3 values + 1 is 4 and 4 divided by 2 is 2 so we need the second number in the list.

If the dataset was 1, 2, 3, and 4, then we would need to take the sum of the values at n/2 and n/2+1 and divide that sum by 2. So 4/2 is 2 and 4/2+1 is 3, and the second and third numbers are 2 and 3. 2+3 is 5 and 5/2 is 2.5 making the median 2.5.

Google Sheets has a quick action that will allow us to do this on a much larger scale.

### Mode

The mode is the most common number in a dataset. We can have multiple modes or no modes.

## Measures of Variance 

### Range

The range is the difference between the highest and lowest values in a dataset.

1, 2, 3, 4 has a range of 3 because the difference between 4 and 1 is 3.

### Interquartile Range

Interquartile range is a way for us to begin the process of identifying outliers. It is the difference between the upper quartile and the lower quartile. The interquartile range is preferred to the range by many statisticians because it increases accuracy.

### Standard Deviation

The standard deviation helps us determine how spread the data is from the mean. It is found by the taking the square root of the sum of a data point - the mean squared divided by the number of data points. This can be a tedious process to do by hand but fortunately Google Sheets has a rapid way for us to do this. The greater the percentage of data points one standard deviation away from the mean, the less dispersed the data set is.

### Variance

Variance is like standard deviation in that it is a measure of dispersion, but it is less often reported. This is another one that can be tricky to calculate by hand.