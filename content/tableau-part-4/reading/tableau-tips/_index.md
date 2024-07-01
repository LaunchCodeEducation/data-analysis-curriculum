+++
title = "Tips for Making the Most of Tableau"
date = 2024-03-12T15:04:03-05:00
draft = false
weight = 2
+++

Our second objective is to revisit the best practices we have already seen and learn how to implement these best practices in Tableau.

## Revisiting Best Practices

In [Data Visualization with Python](https://education.launchcode.org/data-analysis-curriculum/data-visualization/index.html), we introduced some best practices for building effective visualizations and tips for choosing a chart style. 

To start with creating an effective visualization, we need to follow three rules:

1. Make sure that we have textual context
1. Use a color palette that helps us stand out
1. Keep it simple

Let's see how we can ensure that we follow these three rules with Tableau.

### Adding Textual Context 

We cannot guarantee that we will get the opportunity to walk every user through our visualizations so we need to add guiding text such as labels, titles, and captions.

Tableau names the axes of a visualization after the fields that the visualization uses so you may not have the label you really want. To change it, right-click on the axis and select *Edit Axis*. In the resulting menu, you can change a number of characteristics of the axis such as the range, including the actual label text. Remember to add the dimensions of your axis in parentheses after the label text to make sure that the dimensions are clear to your users. If you right-click on the field label, you can click *Format Field* and change the font, font size, and color to better fit your visualization needs. Tableau defaults to field labels being a very dark gray which may not work with the colors chosen for your visualization or be easily readable by members of your team. 

To edit the title, right-click on the title and select *Edit*. The resulting dialog box will also have lots of options for re-formatting the title if you are already satisfied with the text. 

To edit a caption, you can find the *Edit Caption* option under the context menu that appears when you select the arrow on the right-hand side of the title.

### Picking the Right Color Palette

Oftentimes your company will dictate the color palette for you, but you can follow a few simple rules to get the right color palette down pat.

Picking complementary colors with a color wheel can be a good place to start.

Checking color contrast can also help make sure that your vizzes shine. Accessibility is vital to ensuring that your audience understands your visualizations.

You can edit your color palette for the marks of your visualization by right-clicking on the legend and selecting *Edit Colors*. If just one item is out of sync with the rest of the color palette, then you can click *Select Data Item* and change it. If the whole color palette needs to be changed, then you select a new color palette in the *Select Color Palette* dropdown menu.

### Keep It Simple

The principle of keeping it simple means making sure that all the data on the viz is relevant and that we aren't including too much. The more data we have on one viz, the harder it becomes for the reader to comprehend without you there. This isn't to say that including multiple lines on a line chart is a bad idea. You can however use filters on your Tableau vizzes to help clarify what exactly you need and help users select specific groups.

## Selecting Chart Styles in Tableau

Finally, we want to think about what we are displaying before selecting a chart style. Here is a refresher on the four chart styles we introduced in [Data Visualization in Python]({{% relref "../../../data-visualization/reading/chart-styles/" %}}):

1. Comparison
1. Relationship
1. Distribution
1. Composition

Tableau has many chart styles that fit each of these categories beyond the initial ones introduced to you earlier. When you are changing the chart style in the upper right hand corner of Tableau, some chart styles will be unavailable. Tableau marks some chart styles as unavailable due to what is in the columns and rows to help narrow down your chart style choices.

{{% notice blue Example %}}

A spatial chart can only be created with latitude and longitude data and latitude has to be in rows and longitude in columns. Until you have the data in this configuration, Tableau will not assemble a spatial chart for you.

{{% /notice %}}

{{% notice blue Note %}}

Tableau has a great article on [choosing the right chart type for your data](https://help.tableau.com/current/pro/desktop/en-us/what_chart_example.htm).

{{% /notice %}}

## Check Your Understanding

{{% notice green Question %}}

   Based on your explorations of Tableau, is there a chart style you have not previously encountered throughout this course?

{{% /notice %}}

<!-- sample answer could be a gantt chart -->
