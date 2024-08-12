+++
title = "Introduction to NumPy"
date = 2024-08-07T09:00:00-06:00
draft = false
weight = 2
+++

NumPy, or Numerical Python, provides additional flexibility in working with data than standard Python lists. The foundational element of NumPy are arrays, and the main structure found in NumPy is the `ndarray`.

Arrays can hold a collection of the same data type and can be one-dimesional, also called a vector, or multi-dimensional, such as a matrix. The benefits of NumPy arrays are efficient element access and data manipulation / transformation.

### The basics of NumPy arrays

At its most straightforward level, arrays can be created using a Python list, such as

```python {linenos=table}
import numpy as np

# Create a NumPy array from a list
array1 = np.array([8, 5, 3, 2, 1, 1])
print(array1)
```
**Output**

```console
[8 5 3 2 1 1]
```

Multi-dimensional arrays can be created applying the same method using mutiple nested lists, such as the following two-dimensional array (or matrix)

```python {linenos=table}
# import numpy as np

# Create a NumPy multi-dimensional array from nested lists
array2 = np.array([[5, 1, 3], [1, 8, 7], [3, 7, 9]])
print(array2)
```
**Output**

```console
[[5 1 3]
 [1 8 7]
 [3 7 9]]
```

### Basic array operations

Many functions can be performed on arrays, such as determing attributes of the array, sorting, spliting or combining arrays, and, of course, numerical operations.

We will introduce a brief selection of the broad array (no pun intended) of functions which provide useful insights into NumPy arrays.

To start, we can determine the number of dimensions and the number of elements per dimension of an array using the `ndim` and `shape` attributes.

```python {linenos=table}
# import numpy as np

# Create a NumPy multi-dimensional array from nested lists
# array2 = np.array([[5, 1, 3], [1, 8, 7], [3, 7, 9]])
# Number of dimensions of array2
print(array2.ndim)
# Number of elemets (rows & columns in this instance) of array2
print(array2.shape)
```
**Output**

```console
 2
 (3, 3)
```

Sorting is performed using the `sort` function, such as

```python {linenos=table}
# import numpy as np

# Create a NumPy array from a list
# array1 = np.array([8, 5, 3, 2, 1, 1])
# Sort array1
print(np.sort(array1))
```
**Output**

```console
[1 1 2 3 5 8]
```

An array can be broken into multiple arrays using `array_split` or multiple arrays can be merged using `concatenate`. Let's review examples of these

```python {linenos=table}
# import numpy as np

# Create a NumPy array from a list
# array1 = np.array([8, 5, 3, 2, 1, 1])
# Split array1 into three separate arrays
newarray1 = np.array_split(array1, 3)
print(newarray1)
```
**Output**

```console
[array([8, 5]), array([3, 2]), array([1, 1])]
```

```python {linenos=table}
# import numpy as np

# Starting with two distinct arrays
array3 = np.array([[5, 1, 3], [1, 8, 7]])
array4 = np.array([[3, 7, 9]])
array5 = np.concatenate((array3, array4), axis=0)
print(array5)
```
**Output**

```console
[[5 1 3]
 [1 8 7]
 [3 7 9]]
```

Lastly for this introduction, arthimetic functions can be performed on an array as a whole, or for a specific dimension.

```python {linenos=table}
# import numpy as np

# Create a NumPy multi-dimensional array from nested lists
# array2 = np.array([[5, 1, 3], [1, 8, 7], [3, 7, 9]])
print('Mean of array2:', np.mean(array2))
print('Standard Deviation of array2:', np.std(array2))
print('Sum of array2:', np.sum(array2))
```
**Output**

```console
Mean of array2: 4.888888888888889
Standard Deviation of array2: 2.8458329944145997
Sum of array2: 44
```

```python {linenos=table}
# import numpy as np

# Create a NumPy multi-dimensional array from nested lists
# array2 = np.array([[5, 1, 3], [1, 8, 7], [3, 7, 9]])
print('Mean of elements in axis 0 of array2:', np.mean(array2, axis=0))
print('Mean of elements in axis 1 of array2:', np.mean(array2, axis=1))
```
**Output**

```console
Mean of elements in axis 0 of array2: [3.         5.33333333 6.33333333]
Mean of elements in axis 1 of array2: [3.         5.33333333 6.33333333]
```

## Check Your Understanding

{{% notice green Question "rocket" %}}
True or False: Numerical analyses can only be performed on NumPy arrays as a whole.

<!-- Solution: False -->
{{% /notice %}}
