+++
chapter = false
title = "index Examples"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 4
+++

The general syntax for this methods is:

```python
list_name.index(value)
```

`index` returns the index of the FIRST occurrence of `value` in the list.
If the value is not in the list, Python throws an error.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
letters = ['o', 'y', 'j', 'j', 'g', 'f', 'h', 'y', 'j', 'x']

print(letters.index('j'))
print(letters.index('nope!'))
```

**Console Output**

```console
2
ValueError: 'nope!' is not in list
```
{{% /notice %}}

## Finding All Index Values

Often, we want to return all of the index values for a given search. One way to
accomplish this is by using a loop:

{{% notice blue Example "rocket" %}}
```python
letters = ['o', 'y', 'j', 'j', 'g', 'f', 'h', 'y', 'j', 'x']
index_values = []
search_value = 'j'

for index in range(len(letters)):
    if letters[index] == search_value:
    index_values.append(index)

print("{0} has indexes of {1} in the list.".format(search_value, index_values))
```

**Console Output**

```console
j has indexes of [2, 3, 8] in the list.
```
{{% /notice %}}

{{% notice blue Note "rocket" %}}
Returning all index values for a given search is such a common task that
Python coders have found a short, elegant way to do it:

```python
index_values = [index for index in range(len(list_name)) if list_name[index] == search_value]
```

This does the same thing as the `for` loop shown in the example above.
(Take a close look at the code to find the `for` and `if` statements).
{{% /notice %}}