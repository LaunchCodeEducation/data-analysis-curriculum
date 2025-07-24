+++
title = "Lists within Lists"
date = 2024-02-20T09:31:05-06:00
draft = false
weight = 5
+++

Earlier we learned that lists can store values of any data type. Does this mean
we can store lists inside of lists? Well, yes we can...

A **multi-dimensional list** is a list of lists, meaning that the values inside
the list are also lists.

A **nested list** is a list that appears as an element inside another list.
Nested lists can store strings, numbers, and even more lists.

```python
multidim_list = ['a', 'b', [1, 2, 3], 'rutabaga']
```

In `multidim_list`, the element at index 2 is a nested list. If we
`print(multidim_list[2])`, we see `[1, 2, 3]` appear in the console.

The figure below shows a `courses` list that holds lists at each index
position. Each *nested* list contains classes from the same subject area.
Notice that each nested list has its own set of index values.

![A label, 'courses', pointing to a list that contains lists at it's three indexes. Each nested list contains classes from the same subject area.](pictures/multi-dim-list.png?classes=border)

## Two Dimensional Lists

The simplest form of a multi-dimensional list is a two dimensional list. Each
element is a nested list, which contains multiple data values.

{{% notice blue Example "rocket" %}}
```python
two_dim_list = [['a', 'b', 'c'], [90, 101], [True, False, False, True]]

print(len(two_dim_list))
```

**Console Output**

```console
3
```
{{% /notice %}}

`two_dim_list` holds three elements, each of which is a list. Note that the
`len()` function only counts these three elements and NOT the total number of
items inside of the nested lists.

To access the values from a nested list, use two sets of square brackets and
two index values. The indexes evaluate from left to right. The first index
selects one of the nested lists, and the second index selects an element from
that nested list.

{{% notice blue Example "rocket" %}}
Use one set of brackets to access a nested list, and add a second set of
brackets to access the values inside that list.

```python {linenos=table}
two_dim_list = [['a', 'b', 'c'], [90, 101], [True, False, False, True]]

print(two_dim_list[0])     # Print the lists at indexes 0, 1, and 2
print(two_dim_list[1])
print(two_dim_list[2])

print(two_dim_list[0][2])  # Print the element from list 0, index 2
print(two_dim_list[1][1])  # Print the element from list 1, index 1
print(two_dim_list[2][3])  # Print the element from list 2, index 3
```

**Console Output**

```console
['a', 'b', 'c']
[90, 101]
[True, False, False, True]

c
101
True
```
{{% /notice %}}

## Applying Methods to Nested Lists

We can apply list methods to either the nested or outer lists. However,
we must use bracket notation carefully.

To apply a method to the outer list, the syntax is:

```python
list_name.method()
```

To apply a method to one of the nested lists, the syntax is:

```python
list_name[index_of_nested_list].method()
```

{{% notice blue Example "rocket" %}}
Examine how including bracket notation affects how the ``reverse`` method
changes each list.

```python {linenos=table}
list_a = [ ['a', 'b', 'c'], ['A', 'b', 'c'], ['A', 'B', 'C'] ]
list_b = [ ['a', 'b', 'c'], ['A', 'b', 'c'], ['A', 'B', 'C'] ]

list_a.reverse()     # Change the order of the 3 nested lists, but NOT their elements.
list_b[2].reverse()  # Change the order of the list at index 2.

print(list_a, '\n', list_b)
```

**Console Output**

```console
[ ['A', 'B', 'C'], ['A', 'b', 'c'], ['a', 'b', 'c'] ] 
[ ['a', 'b', 'c'], ['A', 'b', 'c'], ['C', 'B', 'A'] ]
```
{{% /notice %}}


## Beyond Two Dimensional lists

There is no limit to how many layers we can have inside our lists. However, it
is rare to use more than two dimensions.

## Check Your Understanding

Use the following list to answer the questions:

```python {linenos=table}
data = [
    ["science", "computer", "art"],
    ["Jones", "Diaz", "Rhodes"]
]
```

{{% notice green Question "rocket" %}}
Which of the following will access the name `"Jones"`?

1. `data[0][0]`
1. `data[0][1]`
1. `data[1][0]`
1. `data[1][1]`

<!-- Solution: 3 -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
How would you add `"dance"` to the first nested list?

1. `data.append('dance')`
1. `data[0].append('dance')`
1. `data[1].append('dance')`

<!-- Solution: 2 -->
{{% /notice %}}