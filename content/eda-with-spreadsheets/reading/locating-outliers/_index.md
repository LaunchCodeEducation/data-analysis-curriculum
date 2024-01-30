+++
title = "Locating Outliers"
weight = 4
originalAuthorGitHub = "gildedgardenia"
+++


EDA is oftentimes done in conjunction with cleaning data. While exploring the dataset, you may notice that something about the dataset appears to be off. Maybe some data points seem to be missing or something is inaccurate (such as the number of apples stocked in a grocery store is -5 or the number of horses in a barn is 0.7). These are all things that we would actually want to deal with during the process of cleaning our data, but in EDA, we can begin to identify these anomalies.

An **outlier** is a datapoint that skews the dataset and introduces bias into our analysis and is also sometimes referred to as **anomalies**. By locating these outliers as part of EDA, we can begin to form our approach to what type of statistical approaches our dataset requires and what visualizations may help our convey our findings later on.

So how do we know what is an outlier and what isn't? We need to dive into outliers and research. The first thing to ask ourselves is is it possible? In the examples above, we cannot have 0.7 horses in a barn because there is no such thing as 0.7 horses. We cannot have -5 apples in an inventory system because once the apples sold out, the number should have remained at 0. If something seems impossible, we should revisit our data source and documentation to first figure out what that is data point supposed to be. Maybe the data source is actually storing the average number of horses in a barn over the course of a year. If the barn rarely had any horse residents, then maybe the average number over the course of a year could be 0.7. Maybe someone mistyped 7 and we ended up with 0.7. Before you go about discarding outliers, you need to dig into each one.

If we are looking at a stock market price for an oil company, we might notice a time where the stock price drops suddenly. We can research the company itself to determine what is happening at that time. Maybe the stock price is inaccurate. Alternatively, maybe something happened that day, such as an environmental catastrophe, and the stock price crashed. This is where research comes to EDA. We cannot make note of what we need to discard until we understand the circumstances that led to the outlier. Sometimes that datapoint does belong there and needs to stay so we can have a more accurate analysis.



