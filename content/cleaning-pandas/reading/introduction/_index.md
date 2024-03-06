+++
title = "Revisiting Cleaning Data"
draft = false
weight = 1
+++

As we discussed in the [previous chapter]({{< relref "../../../cleaning-spreadsheets" >}}) on cleaning data, we need to clean our data to ensure that our analysis is accurate. For example, if we want to project the price of a stock several months from now, then we would need to use as much data as possible for our analysis. If the data is not clean, then our analysis could be thrown off and depending on how unclean the data is, the predicted price could end up hundreds off. This is why we clean our data before diving into further analysuis. By cleaning our data first, we can ensure that the data points being used in the analysis are what we need. 

As we previously covered, there are four types of dirty data:

1. missing data
1. irregular data
1. unnecessary data
1. inconsistent data

While we learned lots of different ways to use spreadsheets to clean data, let's see how we can use pandas to clean data. Because pandas is built for data analysis, the library comes with different ways of handling all four dirty data types. Let's examine each dirty data type and how we can clean it in pandas.
