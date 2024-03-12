+++
chapter = false
title = "Dictionary Methods"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 1001
+++

As with strings and lists, Python provides us with some useful **methods** for
dictionaries. These methods will either *change* an existing dictionary,
*return* information about the dictionary, or *create and return* a new
dictionary.

## Common Dictionary Methods

Here is a sample of the most frequently used dictionary methods.

To see detailed examples for a particular method, click on its name.

| Method | Syntax | Description |
|---|---|---|
| `clear` | `dictionary_name.clear()` | Removes all key/value pairs from a dictionary. |
| `copy` | `dictionary_name.copy()` | Returns an independent copy of a dictionary. This is also called *cloning*. |
| `pop` | `dictionary_name.pop(key)` | Removes the selected key/value pair from the dictionary and returns the value. |
| `keys` | `dictionary_name.keys()` | Returns all of the key names in the dictionary, which can then be moved into a list. |
| `values` | `dictionary_name.values()` | Returns all of the values in the dictionary, which can then be moved into a list. |
| `items` | `dictionary_name.items()` | Returns all of the key/value pairs in the dictionary, which can then be moved into a list. | 

{{% notice blue Note "rocket" %}}
Since dictionaries are unordered, we have no need for methods that sort the
key/value pairs.
{{% /notice %}}

## `max`, `min`, and `len`

Just like with strings and lists, the `len()` function returns the number of
items in a dictionary. Note that each key/value pair gets counted as a single
item.

`max()` and `min()` provide similar results for dictionaries as they do for
strings and lists. By default, the functions return the largest or smallest KEY
in the dictionary, not value. As a best practice, we should specify if we are
looking for a largest/smallest key or value.

```python {linenos=table}
max(dictionary_name.keys())    # Returns the largest key from the dictionary.
min(dictionary_name.values())  # Returns the smallest value in the dictionary.

min(dictionary_name)           # Returns the smallest key from the dictionary.
```

{{% notice blue Note "rocket" %}}
Remember that for strings, `max()` and `min()` return values based on
their position in the alphabet, with capital letters coming before
lowercase.

Using this model, Python considers `"Zebra"` larger than `"Hippo"` but
smaller than `"apple"`.
{{% /notice %}}