+++
title = "Creating Visualizations with Google Sheets"
weight = 3
originalAuthorGitHub = "gildedgardenia"
+++

Now that we have covered some statistics, we can cover some of the visualizations available to us in Google Sheets. These visualizations are not meant to be perfect or presented to business leaders, because the visualizations we create as part of EDA are for us to further uncover the shape of the data set, start to pinpoint our outliers, and outline the approach we want to take with our statistical models. We can start wherever we like, whether with scatter plots, bar graphs, and line charts. We will learn more about the best practices around choosing visualizations and how to make them more effective later on in this course when we get closer to Tableau. For now, we want to use visualizations as a tool to help us learn more about our dataset.

However, while Google Sheets has numerous options for visualizations, we need to decide which chart to start with. We can begin to focus our search by determining whether we focus on one variable or multiple. If we work for a big box store, we may have a dataset of sales numbers. Looking at the current inventory numbers for different categories of goods means only considering one variable, the current inventory number, so we need to pick a chart that works best with one variable, such as a column chart. Now if we wanted to map a store location's sales over the course of 5 years, then we have two variables, the sales and the month, which might mean a line graph. If, for all products, we wanted to map the rating of a product versus its sales for the past month, we might find a scatterplot works best because we have two variables that might not actually make a line but rather just a series of dots. However, as you are beginning to learn about visualizations, you might not yet be able to intuit which visualization works for which situation. Just remember that there is no harm in choosing one style and then trying another style and comparing the two to see which visualization helps you better!

To start the process of making some visualizations in Google Sheets, first decide what series you want to visualize on your y-axis, select that series, and click on *Insert Chart*. This action brings up a menu with a lot of choices for different charts you can use. Let's review just the top few.

## Line Graph

A **line graph** is a chart where each point is connected by a line. While this a good place to start when considering two different variables, it only works well if the shape of the data moves in a somewhat linear fashion. If the data is all over the place, the line connecting the points can be distracting and make it more difficult to see what is going on. In the case of Car Info, we might try a line graph to represent how a car is depreciating in value over time.

## Bar or Column Chart

A **bar chart** is a chart where the columns lie horizontally measuring down the x-axis. A **column chart** is a chart where the columns lie vertically along the y axis. Column charts are also oftentimes referred to as bar charts. For Car Info, a bar chart might do well for mapping the current value of each vehicle.

## Scatterplot

A **scatterplot** is a collection of points where x and y are two series. A scatterplot only works if you have two variables you want to analyze. Looking at Car Info, you could use a scatterplot to map the current value of each car to its mileage.

After you have chosen your chart style, you may want to add your second variable on the x-axis. You can do so in the *Chart Editor* panel by selecting the grid icon below *X-Axis* and selecting the range you would like to add. You may also want to add a chart title or label each axis. You can do so by clicking *Chart & axis titles* in the *Chart Editor* Panel. While your visualizations do not need to be ready to present to business leaders, you may find that you can adding titles can help you throughout the process.

When you create a visualization, you may have a better understanding of what the outliers are and where those outliers are.

## Check Your Understanding

{{% notice green Question %}}

What chart would work best for mapping the price of a stock over time?

{{% /notice %}}

{{% notice green Question %}}

What chart would work best for mapping the current price of the stock of 10 major tech companies?

{{% /notice %}}

{{% notice green Question %}}

What chart would work best for mapping the current stock price of a company to its number of employees for all tech companies in the US?

{{% /notice %}}


