+++
title = "Handling Irregular Data"
draft = false
weight = 3
+++

Irregular data refers to outliers. Outliers are data points that are abnormal. An abnormal data point might be a stock price dropping by over 10x in a day or a heart rate increasing 3x from the resting heart rate while out on a run. As you approach different outliers, you should recognize that abnormalities do happen in real life so while something seems out of the realm of possibility, we should carefully consider what happened before dismissing it and removing it from the dataset. In the case of the heart rate example, if the patient had a resting heart rate of 100 beats per minute, rising to 300 beats per minute even after exercise, could cause disastrous health effects. Is the dataset about people suffering from tachycardia (an increased heart rate) or other cardiovascular health conditions? Or is the dataset concerning healthy adults and the effects of running on their wellbeing? If it is about tachycardia, then while 300 beats per minute seems like an outlier, we might want to keep it in. If the dataset is about healthy adults engaging in running, then 300 beats per minute might mean that the heart rate was not collected properly or a number was mistyped and we might want to remove this outlier.

Let's revisit `etsy_sellers` and see if we have any irregular data we should clean.

```console
   Seller                Sales     Total_Rating     Current_Items
0  Orchid Jewels         17,896    4.5              22
1  Ducky Ducks           5,478     3.8              10
2  Candy Yarns           89,974    4.8              18
3  Parks Pins            6,897     4.9              87
4  Sierra's Stationary   112,988   6.7              347
5  Star Stitchery        53,483    4.2              52
```

Because this dataframe is so small, you might be able to spot some data points that look like outliers, so let's dive in and check out how we can investigate outliers and handle their prescence in our dataset.

## Descriptive Statistics

We have used descriptive statistics a lot so far, but it really is a data analyst's bread and butter! We might notice that the max and min of the `Sales` are pretty far apart, but since Etsy hosts all sorts of sellers from well-established ones to new businesses, it isn't out of the realm of possiblity that all those numbers are actually appropriate.

However, when we use the `descibe()` function and look more closely at `Total_Rating`, we might notice that the max is 6.7 which is an outlier. The highest number of stars a shop can have on Etsy is 5 so something is up here and we need to investigate. We can then drop the row for Sierra's Stationary by using the `drop()` function.

```python

outlier = np.where((etsy_sellers['Total_Rating'] < 0.0) & (etsy_sellers['Total_Rating'] > 5.0))
etsy_sellers.drop(etsy_sellers[outlier])
```

Even though we can visually see where Sierra's Stationary is in the dataframe, if we have one row that is off, we might have others. `np.where()` returns a list of all indices where the condition is met. In this case, the condition is that the rating must be greater than or equal to 0 and less than or equal to 5.

We can also use visualizations to detect outliers. 

## Visualizing Outliers

The two most common visualization types for locating outliers are histograms and scatterplots. Which one you choose depends on what portion of your dataset you want to visualize. In the case of visualizing `Total_Rating`, a histogram might be the better option.

```python
etsy_sellers.plot.hist(column="Total_Rating")
```

We could also use a scatterplot if we wanted to try it out.

```python 
etsy_sellers.plot.scatter(x="Seller",y="Total_Rating")
```

pandas comes with a number of different visualizations, so feel free to explore the different styles when on a mission to detect outliers. 
