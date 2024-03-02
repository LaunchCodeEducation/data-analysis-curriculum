+++
title = "Handling Irregular Data"
draft = false
weight = 3
+++

Irregular data is a term that commonly applies to outliers. 

Let's revisit `etsy_sellers`.

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

We have used descriptive statistics a lot so far, but it really is a data analyst's bread and butter! We might notice that the max and min of the `Sales` are pretty far apart, but since Etsy hosts all sorts of sellers from well-established ones to new businesses so it isn't out of the realm of possiblity that all those numbers are actually appropriate.

However, when we use the `descibe()` function, we might notice that the max is 6.7 which is an outlier. The highest number of stars a shop can have on Etsy is 5 so something is up here and we need to investigate. 

## Visualizing Outliers

The two most common visualization types for locating outliers are histograms and scatterplots.

```python 
etsy_sellers.plot.scatter(x="Seller",y="Total_Rating")
```

In this case, while we actually would find it more helpful to do a histogram.

```python
etsy_sellers.plot.hist(column="Total_Rating")
```

While one plot visualization helps highlight outliers better than others, it entirely depends on what you are working on.