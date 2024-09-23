+++
title = "Hierarchies"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

Data is oftentimes arranged in a pecking order, mirroring what we see in the outside world. We can rank data just as we would a family tree, starting with great grandparents and moving down through the generations. 

In data, we call this a hierarchical structure. A **hierarchy** in Tableau is the mechanism Tableau uses to allow you to organize your data this way.

When you load your data into a worksheet, Tableau will automatically assemble a **hierarchy**. If you see something that is off or the organization of the data looks wrong, then you may want to create a custom hierarchy. 

To do so, you can start in the Data pane. Drag a field that you want in your hierarchy and you will be prompted to give the new hierarchy a name. You can then continue to add new items to your hierarchy or can drag fields to different positions in the hierarchy to re-order it as necessary.

{{% notice blue Note %}}

When you are looking at all your measures and dimensions in the Data pane, your hierarchy is designated by the icon that looks like a family tree. You can collapse the hierarchy view by clicking on the arrow next to the hierarchy name.

{{% /notice %}}

If we still work for an online retailer, but are instead focusing on all sales within the accessories department, we might need to establish a custom hierarchy. 

We might start with a label for accessory type, then move on to a sub style then to an additional descriptor field. In the case of hoop earrings, the accessory type would be 'jewelry', the sub style would be 'earrings', and then the additional descriptor would be 'hoops'.

Organizing your data in this manner comes into play with visualizations too. While best practices dictate that you keep it simple, you want to make sure that your visualization still properly shows trends and other key takeaways from your analysis. 

If you have a field from a hierarchy in a visualization, you can click on the plus sign or the minus sign to add or remove layers of your hierarchy as necessary. You can always remove a custom hierarchy later on by right-clicking on the hierarchy and selecting *Remove Hierarchy*.

## Check Your Understanding

{{% notice green Question %}}

True or False: Creating a hierarchy of related fields, such as State, County, School District, will allow you to “drill down” between each level of the hierarchy in Tableau.

{{% /notice %}}

<!-- True -->

{{% notice green Question %}}

True or False: Only Tableau can create hierarchies based on its internal algorithms.

{{% /notice %}}

<!-- False -->