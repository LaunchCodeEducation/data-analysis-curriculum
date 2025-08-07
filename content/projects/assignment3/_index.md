+++
title = "Call Center Cleanup"
date = 2023-05-25T12:55:09-05:00
draft = false
weight = 4
hidden = false
+++

## Learning Objectives

By completing this assignment, students will be able to:

1. **Exploratory Data Analysis (EDA)**: Conduct thorough exploratory analysis on call center datasets to understand data structure, identify patterns, and extract basic statistics about call center performance metrics.

2. **Data Cleaning with Pandas**: Identify and resolve data quality issues including missing data, duplicates, inconsistent values, and unnecessary information using systematic data cleaning techniques.

3. **Data Manipulation and Transformation**: Combine datasets, perform grouping operations, calculate key performance indicators (KPIs), and create new derived metrics for business analysis.

4. **Data Visualization**: Create effective visualizations using Python libraries to communicate call center performance insights, choosing appropriate chart types for different data relationships and business questions.

5. **Business Analytics Problem-Solving**: Apply data analysis skills to real-world business scenarios, specifically evaluating call center efficiency to inform resource allocation decisions and operational improvements.

For this assignment, we will be working with call center data. You can start 
working on the assignment after the first lesson on Exploratory Data Analysis. 
Make sure to read the whole assignment before starting anything! As you code 
along in the Jupyter notebook, you are asked to make note of the results of 
your analysis. Do so by clicking on the results box and adding your notes 
beside each question.

## Business Issue and Understanding

You are working for a company that has two call centers: the North Call 
Center and the South Call Center. The company is looking to possibly hire five 
additional reps to enhance customer experience. Your task is to explore how 
efficient the current reps are in each branch to determine which branch would 
benefit from additional assistance.

### How the Call Center Works

Call center representatives are assigned queues. When calls are assigned to a 
queue, the call is assigned to the next person in line in the queue. After a call 
is assigned to a representative, the amount of time between assignment and the 
call starting is divided into busy minutes and not ready minutes. If the call is 
incoming and a customer is waiting on the phone for a rep, the time is split into 
three categories: busy minutes, not ready minutes, and incoming call wait time. 
Once the rep has the customer on the phone, there might be during call wait time, 
where the call is put on hold while the rep gets an answer for the customer.

## Getting Started

Fork [this GitHub repository](https://github.com/LaunchCodeEducation/call-center-cleanup-assignment), clone it to your computer, and open it inside of a new notebook.

## Submitting Your Work

When you are finished, make sure to push your changes up to GitHub. Copy the link to your GitHub 
repository and paste it into the submission box in Canvas for Graded Assignment #3: Call Center Cleanup and click *Submit*.

{{% notice blue Note "rocket" %}}
The following tasks and questions in the textbook for this assignment are also located within the notebook from the above GitHub repository. You must save the answers to the questions within your notebook for grading.
{{% /notice %}}

{{% children %}}
