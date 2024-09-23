+++
title = "Task 3: Data Manipulation"
date = 2023-05-25T12:55:09-05:00
draft = false
weight = 3
+++

This third task of this assignment involves manipulating your data. You should feel comfortable beginning this task after you have completed [Chapter 21: Data Manipulation]({{% relref "../../../data-manipulation/_index.md" %}})

Before you begin answering any questions, combine the two existing datasets together within your notebook to create a third dataframe called df. You can use this third dataframe to compare the two call centers to company-wide trends.

{{% notice green Question "rocket" %}}
Group by Rep ID and sum the resulting structure. Sort by calls to determine which rep in each branch has the highest number of calls.
{{% /notice %}}

{{% notice green Question "rocket" %}}
The average call abandonment rate is a KPI when it comes to determining call center efficiency. As you may recall, abandoned calls are calls where the customer hangs up due to long call times. What is the average call abandonment rate for each branch and the whole company? Do any of these fall out of the optimal range of 2-5%?
{{% /notice %}}

{{% notice green Question "rocket" %}}
Service level is another KPI when it comes to measuring call center efficiency. Service level is the percentage of calls answered within a specific number of seconds. In the case of your employer, their ideal time frame is 2 seconds. What is the percentage of calls answered within 2 seconds for each branch and the entire company?
{{% /notice %}}

{{% notice green Question "rocket" %}}
For each branch and the entire company, what is the average speed of answer?
{{% /notice %}}