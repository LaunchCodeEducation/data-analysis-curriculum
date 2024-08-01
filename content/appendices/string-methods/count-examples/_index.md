+++
chapter = false
title = "Count Examples"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 1
+++

## `count` Examples

The general syntax for this method is:

```python
string_name.count(search_string)
```

This method returns the number of times `search_string` occurs in
`string_name`.

{{% notice blue Example "rocket" %}}
```python
print('bananas'.count('a'))
print('bananas'.count('B'))
print('bananas'.count('nana'))
```

**Console Output**

```console
3
0
1
```
{{% /notice %}}



Note that `count()` searches for the EXACT string placed in the `()`. Even
though `bananas` contains the letter `'b'`, since the case does NOT match
in line 2, the expression returns `0`.

##Search Part of a String

The `count()` method can also take a starting and ending index value:

```python
string_name.count(search_string, start, end)
```

Written this way, the method searches `string_name` from the `start` index
up to but NOT including the `end` index.

{{% notice blue Example "rocket" %}}
```python
produce = 'Bananas and rutabagas!'
# Note that the first three 'a' characters are at index values 1, 3, and 5.
   
print(produce.count('a'))
print(produce.count('a', 1, 5))
print(produce.count('a', 1, 6))
```

**Console Output**

```console
7
2
3
```
{{% /notice %}}