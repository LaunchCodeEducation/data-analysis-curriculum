+++
pre = "<b>5. </b>"
title = "Searching Dictionaries"
date = 2024-02-20T09:31:05-06:00
draft = false
weight = 5
+++

With both lists and strings, we used the `in` and `not in` operators to
search for specific values. These expressions returned either `True` or
`False` depending on if the value was found in the collection.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
greeting = 'Hello, World!'
fruits = ['apple', 'banana', 'pear', 'kiwi', 'orange']
numbers = [28, 32, 7, 29, 33, 0]

print('or' in greeting)  # Search for the substring 'or' in the larger string.
print('nana' in fruits)  # Search for the value 'nana' in the list of strings.

print('!' not in greeting) # Check if '!' is NOT in 'Hello, World!'.
print(42 not in numbers)   # Check if 42 is NOT in the numbers list.
```

**Console Output**

```console
True
False
False
True
```
{{% /notice %}}

Since the elements in a dictionary come as pairs, we search for an item in
*either* the set of keys *or* the set of values.

We practiced with the `keys()` and `values()` methods in the previous two
sections, and we can use them in a similar way to search a dictionary.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
ticket_holders = {
    'Bob' : 100,
    'Jessi' : 103,
    'Maria' : 101,
    'Devon' : 102
}

print(101 in ticket_holders.keys())
print(101 in ticket_holders.values())

print('Jessi' in ticket_holders.keys())
print('Jessi' in ticket_holders.values())
```

**Console Output**

```console
False
True
True
False
```

1. In line 8, `101 in ticket_holders.keys()` returns `False`. Even though `101` is in the dictionary, it is a *value*, and in this case we are searching through the *keys*.
1. In line 9, `101 in ticket_holders.values()` returns `True`.
1. In lines 11 and 12, we search for the string `'Jessi'` first in the keys and then in the values.
{{% /notice %}}

## Default Search Method

If we do not add the `keys()` or `values()` method after the dictionary
name, Python searches the *keys* by default.

This means that

```python
search_value in dictionary_name.keys()
```

returns the same result as

```python
search_value in dictionary_name
```