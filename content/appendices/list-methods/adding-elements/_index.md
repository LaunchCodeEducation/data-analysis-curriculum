+++
chapter = false
title = "Adding Elements To a List"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 1
+++

The `append` and `insert` list methods *mutate* (change) the original list.

## `append` Examples

The general syntax for this method is:

```python
list_name.append(new_value)
```

`append` adds one new item to the END of a list. The new item may be of any
data type, including another list.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
letters = ['a', 'b', 'c']

letters.append('a')
print(letters)

letters.append(['l', 'm', 'n', 'o', 'p'])
print(letters)
```

**Console Output**

```console
['a', 'b', 'c', 'a']
['a', 'b', 'c', 'a', ['l', 'm', 'n', 'o', 'p']]
```
{{% /notice %}}

{{% notice blue Note "rocket" %}}
To add multiple, separate items to the end of a list:

1. Use multiple `append` statements (possibly in a loop), OR
1. Use concatenation to add two lists together.

```python {linenos=table}
letters = ['a', 'b', 'c']
digits = [0, 1, 2, 3]

for digit in digits:
letters.append(digit)   # Each iteration, add a digit to the end of the list.

print(letters)

letters = letters + ['l', 'm', 'n', 'o', 'p']
print(letters)
```

**Console Output**

```console
['a', 'b', 'c', 0, 1, 2, 3]
['a', 'b', 'c', 0, 1, 2, 3, 'l', 'm', 'n', 'o', 'p']
```
{{% /notice %}}



## `insert` Examples

The general syntax for this method is:

```python
list_name.insert(index, new_value)
```

`insert` adds `new_value` at the specified `index` in the list. The new
element may be of any data type, including another list.

Existing data values that come before `index` remain unchanged. Data values
at or after `index` all get shifted further down the list.

{{% notice blue Example "rocket" %}}
```python
languages = ['Python', 'JavaScript', 'Java', 'C#']

languages.insert(2, 'Swift')
print(languages)
```

**Output**

```console
['Python', 'JavaScript', 'Swift', 'Java', 'C#']
```
{{% /notice %}}