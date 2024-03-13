+++
title = "Visualize Data with pandas"
date = 2024-02-29T09:18:56-06:00
draft = false
weight = 4
hidden = true
+++

The `pandas` library works in conjuction and is able to integrate other libraries very easily. One of those libraries is **Matplotlib**, which is a library used to visalize the data that you are working with.

## Installation

```console
pip install matplotlib
```

### Importing

```python
# best practice is to import matplotlib as mpl
import matplotlib as mpl
```

```python
# best practice when is to import matplotlib.pyplot as plt
import matplotlib.pyplot as plt
```

{{% notice blue Note "rocket" %}}
**Pyplot** is a submodule of the `matplotlib` library for Python. Often times importing `pyplot` is enough and the need to import the entire `matplotlib` library is not necessary.

When importing matplotlib you are also importing `pyplot` as well. You could reference pyplot as such: `mpl.pyplot.function_here()`

Often times pyplot is used to generate 2-D graphics and since it is referenced often importing it separately and assigning it it's own alias is helpful and may save some time!
{{% /notice %}}

## Example

1. `numpy` is imported as `np`
1. `pyplot` is imported as `plt`
1. Created a variable to hold the csv data
1. Plot the data
1. Show the data

```python {linenos=table}
import numpy as np
import matplotlib.pyplot as plt

# Create a variable and read a csv data file
example_data_variable = pd.read_csv('path-to-file.csv')

# Create a plot graph
example_data_variable.plot()
# Show the graph
plt.show()
```

{{% notice blue Note "rocket" %}}
When using tools like Jupyter Notebooks you may not need to include the `plt.show()` line of code shown on line 11 in the above code block. 

The `plt.show()` when used within a terminal emulator environment will create a separate pop-out of the graph. Tools like Jupyter Notebooks will include the visual within the notebook itself, eliminating the need for the pop out window.
{{% /notice %}}