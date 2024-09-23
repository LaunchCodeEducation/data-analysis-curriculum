+++
title = "Groups and Sets"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 3
+++


## Grouping Data Together

When we create a **group** in Tableau, we are combining multiple fields into one. For example, if we are trying to visualize different recipes, we can combine fields for pasta and chicken into a new group called Entrees. 

To create a group, you need to start in the Data Pane.

1. Right-click on the field you want to group and click *Create* > *Group*.
1. In the dialog box that appears, you can select other fields that you want to add to the group and click *Group*.

Unlike hierarchies, Tableau creates a name for your group automatically. To rename it to something that makes more sense to you, you simply have to select it and click *Rename*.

With your group set up, you can begin to work with it. Tableau considers fields that are not a part of the group to be the "Other". If you want to add new fields to your group, you can right-click on the group in the Data Pane and click *Edit Group*. From the dialog box that appears, you can select new fields to add to the group. You can also opt to *Include Other* in the dialog box if that is helpful to your analysis. Finally, you can start removing members of the group in the same dialog box.

## Setting Data Aside

Whereas a group allows us to combine fields, a **set** allows us to assemble data from one field that meets a specific condition. For example, if we have one field called `Fiscal Year`, we can create a set for the data from the 2019 fiscal year.

If we are analyzing earrings sales for the past five years, we could use a set for each of the five years. While it is helpful for us to have an overarching look at the whole five years, having a set for 2019, for example, allows us to drill down and provide additional analysis and calculations. All rows that are for 2019 are called "In" and all rows that are for other years are called "Out".

### Dynamic Sets

A **dynamic set** is one where the set changes as the data changes. If we created a set for the current fiscal year of sales, we might want to use a dynamic set so as more sales data comes in, the set automatically updates.

To create a dynamic set, right-click on the dimension you are interested in. Select *Create* > *Set*. The dialog box that appears has three tabs. The *General* tab is where you can choose what to include. The *Condition* tab is where you can specify the condition that the members must meet to be included in the set. Finally, the *Top* tab allows you to place limits on the members to be included in the set. When you have everything configured how you wish, click *OK* and your new set can be found in the Data pane under "Sets".

You can add or remove data points later when you visualize the set by right-clicking on the data points and clciking on the Set icon. This action opens up the set dropdown menu where you can choose to either add the point(s) or remove them from the set.

{{% notice blue Note %}}

The above method also works for a fixed set, which we will talk more about now!

{{% /notice %}}

### Fixed Sets

A **fixed set** is a set of data where the members stay the same even if the data changes. You may want a fixed set for datasets that you know are stable such as the 2019 fiscal year set or if you are concerned that any change in the set could result in an invalid analysis.

You can create a fixed set by selecting a group of data points on your visualization and right-clicking on them. Click *Create Set* and give your new set a name.

### In/Out

When visualizing sets, Tableau defaults to visualizing the set in **In/Out** mode. One of the benefits of creating a set is easily comparing what is going on within the set and the rest of the dataset. If you want to see just the members of the set, you can right-click on the set name and choose *Show Members in Set*. If you want to go back to In/Out mode, you can right-click and choose *Show In/Out*.

The names **In/Out** may be modified when added to a visualization in Tableau. You can directly right click on the field name **In/Out**, then click "Edit alias". The dialog box which opens provides the ability to create "Alias" names for **In** and **Out** which will appear in your visualization, and may often be more beneficial and understandable for the audience of your data visualization.

## Check Your Understanding

{{% notice green Question %}}

Groups can be used for all of the following except:

1. Combine related members in a field 
1. Correct errors 
1. Answer "What if" questions 
1. Organize data by what is "In" and what is "Out" 

{{% /notice %}}

<!-- Organize data by what is In and what is Out -->

{{% notice green Question %}}

What other term is used to describe non-grouped members?

1. Out 
1. Not part of the group 
1. Other 
1. Set 

{{% /notice %}}

<!-- Other -->

{{% notice green Question %}}

Match the two types of sets:

|  |  |
|--|--|
| Dynamic | Sets that change when the data changes |
| Fixed | Sets that do not change, even if the data changes |

{{% /notice %}}

<!-- Dynamic sets are sets that update as data changes and fixed sets are sets that do not change even when the data changes -->

{{% notice green Question %}}

Match the members of a set:

|  |  |
|--|--|
| In | Members not in the set |
| Out | Members within the set |

{{% /notice %}}

<!-- In refers to members within the set and out refers to members not in the set -->
