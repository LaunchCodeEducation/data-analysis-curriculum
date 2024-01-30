+++
title = "An Introduction to Exploratory Data Analysis"
weight = 1
originalAuthorGitHub = "gildedgardenia"
+++

**Exploratory Data Analysis** or **EDA** is a vital step for us to begin our work with. EDA is a process where we attempt to find patterns and connections, locate outliers, and begin to uncover the structure of our dataset. We cannot do this process with any assumptions or end goals. We just want to understand what we have access to. The main reason we do EDA is so that we can determine the best path forward. After EDA, you may go back and pull more numbers because you realized that you do not have the information you need or you may decide that you will use a different regression model than the one you previously thought would work for the data.

The EDA process should do the following for you:

1. Help you form hypotheses about what is the underlying forces effecting your data.
1. Challenge previous assumptions you may have made when discussing the business issue.
1. Guide you on what tools and techniques you should use when working with that dataset. 

The technical steps we will take to begin this process are summary statistics and creating visualizations. By the end of these two steps, you should be able to begin the process of locating outliers in your dataset. We will cover how to handle these outliers in the next chapter. Outliers can skew your results so analysts want to locate outliers as early as possible in the project to remove the possibility of inaccuracies as they continue their work.

Summary statistics include measures of variance, such as standard deviation and measures of central tendancy, such as mean, median, and mode. We will be using these summary statistics to get a sense of the shape of our dataset. As we begin to understand the shape of our dataset, we can more easily select visualizations we want to start with.

Creating visualizations help us further understand what we are seeing in the summary statistics. Some visualizations work well when we want to learn more about one variable within our dataset while others work better when we are working with 2 or more variables in the dataset. While these visualizations may not be part of the final presentation, creating visualizations are integral to beginning the data analysis project and understanding the general shape and behavior of the data within our dataset.

While you are beginning to understand the shape of the dataset you are working on, you may come to realize that something is off. An anomaly or outlier in your dataset may be distorting the shape and thus interfering with your ability to decide on your next steps. As you will learn in the next chapter, data cleaning goes hand in hand with EDA and helps you handle outliers and other things that may need to be removed from the dataset. While doing EDA, you will find it immensely helpful to make note of these discoveries so that you can more efficiently clean the dataset.

{{% notice blue Note %}}

EDA continues beyond these initial steps and is oftentimes done on larger datasets with Python. For now, we want to introduce you to the process with spreadsheets so you can focus on learning more about how EDA works and then we will dive back into EDA once we learn more about Python.

{{% /notice %}}