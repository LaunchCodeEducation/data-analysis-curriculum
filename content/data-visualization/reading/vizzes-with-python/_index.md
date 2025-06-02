+++
title = "Matplotlib"
date = 2024-03-11T13:58:38-05:00
draft = false
weight = 3
+++

Armed with visualization best practices, we can dive into Matplotlib, the Python library is oftentimes used with pandas to create beautiful visualizations. 
 
Matplotlib might show up more as a tool for EDA, where the visualizations are mainly tools for us as analysts as opposed to visualizations to present to business leaders. 

To import Matplotlib, we can use the following common syntax:

```python
import matplotlib.pyplot as plt
```

{{% notice blue Note %}}

Throughout your career, you may notice that sometimes you need to use `plot.show()` to get your visualization to actually appear on the screen. This depends on what environment you are running your code in. If you are running your code in the terminal, you need to add `plot.show()`. 

However, if you are running your code in an environment like a Jupyter notebook, you do not need `plot.show()`.

{{% /notice %}}

## Bar Charts and Column Charts

### Matplotlib

For column charts, you will need to use `bar()` method and for bar charts, you will need to use the `barh()` method. Both methods have similar parameters so once you master one, it will be simpler to master the other one. 

Let's revisit the plant nursery.

```python {linenos=table}
plants = ["Lemon", "Lime", "Orange"]
fruit_yield = [89, 43, 12]

plt.bar(plants, fruit_yield)
```

The above code would create a column chart that has three different citrus trees on the x-axis and their respective fruit yields for the year on the y-axis.

## Scatterplots

### Matplotlib

We can use the `scatter()` method to put together a scatterplot in Matplotlib and finally see if there is a relationship between the butterfly population and the number of participants in the pollinator planting program.

```python {linenos=table}
butterflies=[12,34,89]
pollinator_participants=[10,56,102]

plt.scatter(pollinator_participants, butterflies)
```

## Histograms

### Matplotlib

Let's use histograms to better understand the butterfly population at the nursery. When we chart a histogram, we need to decide on the bin size. **Bins** are the columns in a histogram. If someone counted the number of butterflies every week for 8 weeks, then it makes sense for us to have 8 bins.

```python {linenos=table}
butterflies=[2,6,17,28,59,112,56,24]

plt.hist(butterflies, bins=8)
```

## Pie Charts

### MatplotLib

Finally, let's explore how we can use these Python libraries to make pie charts. If we needed to create a visualization breaking down the nursery sales by plant category, we could use the `pie()` method in Matplotlib.

```python {linenos=table}
categories = ["annuals", "perenials", "trees", "houseplants"]
sales = [678, 1894, 1234, 768]

plt.pie(sales,labels=categories)
```

The `labels` parameter specifies what each slice of the pie chart should be called.

### Seaborn

As we mentioned on the previous page, not everyone likes pie charts and Seaborn is no exception. Seaborn does not come with a pie chart method. 

As you explore making visualizations in Python, we suggest bookmarking both the [Matplotlib documentation](https://matplotlib.org/stable/index.html) This documentation comes with lots of examples of how you can properly use the multitude of parameters that come with each of the above methods.
