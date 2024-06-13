+++
title = "Tips for Making the Most of Tableau"
date = 2024-03-12T15:04:03-05:00
draft = false
weight = 2
+++

## Revisiting Best Practices

In [Data Visualization with Python](https://education.launchcode.org/data-analysis-curriculum/data-visualization/index.html), we introduced some best practices for building effective visualizations and tips for choosing a chart style. 

To start with creating an effective visualization, we need to follow three simple :

1. Make sure that we have labels
1. Use a color palette that helps you stand out
1. Keep it simple

Let's see how we can ensure that we follow these three rules with Tableau.

### Adding Textual Context 

Beyond labels and titles, we can also add captions to visualizations to give our users additional context. We cannot guarantee that we will get the opportunity to walk every user through our visualizations so we need to add guiding text such as labels, titles, and captions.

Tableau names the axes of a visualization after the fields that the visualization uses so if you want to rename a label, you need to rename the field itself. If you right-click on the field label, you can click *Format Field* and change the font, font size, and color to better fit your visualization needs. Tableau defaults to field labels being a very dark gray which may not work with the colors chosen for your visualization or be easily readable by members of your team. 

### Picking the Right Color Palette

Oftentimes your company will dictate the color palette for you, but you can follow a few simple rules to get the right color palette down pat.

Picking complementary colors with a color wheel can be a good place to start.

Checking color contrast can also help make sure that your vizzes shine. Accessibility is vital to ensuring that your audience understands your visualizations.

You can edit your color palette for the marks of your visualization by right-clicking on the legend and selecting *Edit Colors*. If just one item is out of sync with the rest of the color palette, then you can click *Select Data Item* and change it. If the whole color palette needs to be changed, then you select a new color palette in the *Select Color Palette* dropdown menu.

### Keep It Simple

The principle of keeping it simple means making sure that all the data on the viz is relevant and that we aren't including too much. The more data we have on one viz, the harder it becomes for the reader to comprehend without you there. This isn't to say that including multiple lines on a line chart is a bad idea. You can however use filters on your Tableau vizzes to help clarify what exactly you need and help users select specific groups.

## Selecting Chart Styles in Tableau

Just as before, we want to think about what we are displaying before selecting a chart style. Here is a refresher on the four chart styles:

1. Comparison
1. Relationship
1. Distribution
1. Composition

Tableau has many chart styles that fit each of these categories beyond the initial ones introduced to you earlier. When you are changing the chart style in the upper right hand corner of Tableau, some chart styles will be unavailable. This may be due to the chart style you chose.

{{% notice blue Example %}}

A spatial chart can only be created with latitude and longitude data and latitude has to be in one location and longitude in the other. Even then your marks won't show up until you add a hierarchy with the city, state, and country.

{{% /notice %}}

{{% notice blue Note %}}

Tableau has a great article on [choosing the right chart type for your data](https://help.tableau.com/current/pro/desktop/en-us/what_chart_example.htm).

{{% /notice %}}

## Check Your Understanding

{{% notice green Question %}}

   What type of viz is best for showing correlations?
   
   a. Line Chart
   #. Pie Chart
   #. Scatter Plot 
   #. Flow Chart 

{{% /notice %}}