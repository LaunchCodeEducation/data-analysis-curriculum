+++
title = "Relationships"
date = 2024-05-28T13:45:19-05:00
draft = false
weight = 3
+++

Tableau allows you to create **relationships** between data sources. The relationship itself is based on a column(s) that the two tables you are trying to relate have in common. A relationship must have at least one matching pair of fields in order to be created, meaning they must be of the same data type.

One of the great things about relationships with Tableau is that you do not need to specify the join type for the relationship, Tableau takes care of that query behind the scenes for you.

## Creating a Relationship

When creating a new relationship and populating a new sheet within your workbook using the newly related data. In order to create a new relationship you can simply drag to existing data sources onto the canvas and select the appropriate columns to relate.

Once the relationship is established, you can add fields from both data sources to your worksheets and visualizations. Tableau will automatically use the relationship to combine and display the data correctly.

<!-- TODO: Add Image of creating a relationship below -->
