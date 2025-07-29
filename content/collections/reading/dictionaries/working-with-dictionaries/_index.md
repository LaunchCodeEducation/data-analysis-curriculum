+++
title = "Working with Dictionaries"
date = 2024-02-20T09:31:05-06:00
draft = false
weight = 2
+++

Dictionaries are *mutable*, so we can change the value assigned to a key, add
new key/value pairs, or remove key/value pairs.

Since dictionaries are *unordered*, we have no options for sorting or
rearranging the key/value pairs within the collections.

## Change One Value

To update a single value in a dictionary, use the syntax:

```python
dictionary_name[key] = new_value
```

`dictionary_name[key]` identifies the value in the collection that we want to
change. The `=` operator assigns `new_value` to that key.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
phone_book = {
   'Mom' : '555-5555',
   'Work' : '555-5556',
   'Home' : '123-456-7890'
}
print(phone_book)

phone_book['Work'] = '314-555-5556'  # Link the key 'Work' to the value '314-555-5556'.
print(phone_book)
```

**Console Output**

```console
{'Mom' : '555-5555', 'Work' : '555-5556', 'Home' : '123-456-7890'}
{'Mom' : '555-5555', 'Work' : '314-555-5556', 'Home' : '123-456-7890'}
```
{{% /notice %}}

{{% notice blue Note "rocket" %}}
We cannot use this method to change the names of the keys.
{{% /notice %}}

## Add a New Key/Value Pair

After defining a dictionary, we can add new new key/value pairs at any time by
using bracket syntax:

```python
dictionary_name['new_key'] = new_value
```

{{% notice blue Example "rocket" %}}
```python {linenos=table}
phone_book = {
   'Mom' : '555-5555',
   'Work' : '555-5556',
   'Home' : '123-456-7890'
}
print(phone_book)

phone_book['BFF'] = '555-5557'
print(phone_book)
```

**Console Output**

```console
{'Mom' : '555-5555', 'Work' : '555-5556', 'Home' : '123-456-7890'}
{'Mom' : '555-5555', 'Work' : '555-5556', 'Home' : '123-456-7890', 'BFF' : '555-5557'}
```
{{% /notice %}}

## Remove a Key/Value Pair

To remove a key/value pair from a dictionary, use the `del` keyword. The
general syntax is:

```python
del dictionary_name[key]
```

{{% notice blue Example "rocket" %}}
```python {linenos=table}
phone_book = {
   'Mom' : '555-5555',
   'Work' : '555-5556',
   'Home' : '123-456-7890',
   'BFF' : '555-5557'
}
print(phone_book)

del phone_book['Home']
print(phone_book)
```

**Console Output**

```console
{'Mom' : '555-5555', 'Work' : '555-5556', 'Home' : '123-456-7890', 'BFF' : '555-5557'}
{'Mom' : '555-5555', 'Work' : '555-5556', 'BFF' : '555-5557'}
```
{{% /notice %}}

{{% notice blue Note "rocket" %}}
Once we define a key, it remains in the dictionary unless we use `del` to
remove it.

For example, if we wanted to rename the key `'Mom'` to `'Mother'`, we
would have to delete the old key first, then add a new key/value pair.

```python
del phone_book['Mom']
phone_book['Mother'] = '555-5555'
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Given the following dictionary:

```python
pet_population = {'cats' : 10, 'dogs' : 5, 'elephants' : 25}
```

What value does `len(pet_population)` return?

1. 3
1. 6
1. 40
<!-- Solution: 1 -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
Using the same `pet_population` dictionary, what would the following
statement do?

```python
pet_population['birds'] = 5
```

1. Throw an error message because `pet_population` does not contain a `'birds'` key.
1. Add the `'birds' : 5` key/value pair to the dictionary.
1. Add five `'birds'` keys to the dictionary.
1. Replace the `'dogs'` key with `'birds'`.
<!-- Solution: 2 -->
{{% /notice %}}