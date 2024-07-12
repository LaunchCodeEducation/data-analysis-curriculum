+++
title = "Task 4: Subqueries, Unions, Derived Tables, Oh My!"
date = 2023-05-25T12:55:09-05:00
draft = false
weight = 4
+++

You can answer the following questions after [Chapter 10: SQL Part 4]({{% relref "../../../sql-part-4/_index.md" %}}).

{{% notice green Question %}}

Write a query that returns the `series_id`, `industry_code`, `industry_name`, and `value` from the `january_2017` table but only if that value is greater than the average value for `annual_2016` of `data_type_code` 82.

{{% /notice %}}

{{% notice green Question %}}

Create a union table comparing average weekly earnings of production and nonsupervisory employees between `annual_2016` and `january_2017` using the data type 30.  Round to the nearest penny.  You should have a column for the average earnings and a column for the year, and the period.

{{% /notice %}}

Once you have completed all four tasks, make sure to answer the questions in the "Summarize Your Results" section before going on to [Submitting Your Work]({{% relref "../_index.md#submitting-your-work" %}})
