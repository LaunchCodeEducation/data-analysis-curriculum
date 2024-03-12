+++
pre = "<b>3. </b>"
title = "Iterating with Dictionaries"
date = 2024-02-20T09:31:05-06:00
draft = false
weight = 3
+++

Many times in this book, we looped through the characters in a string or the
elements in a list without using the index values.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
my_string = 'Rutabagas!'
numbers = [33, -25, 3.14, 86, 1168, 42, 6.022e23]

for character in my_string:
    print(character)

total = 0
for number in numbers:
    total += number*2
```
{{% /notice %}}

Each time the loop body repeats, the loop variable (`character` or
`number`) gets assigned the next value in the collection.

We can do something similar with dictionaries.

## Loop by Keys or Values

To loop through a dictionary, we need to specify whether to assign the loop
variable the keys or the values from the collection. To do this, we use the
`keys()` or `values()` method in the `for` statement:

```python {linenos=table}
for key in dictionary_name.keys():
    # Loop body...

for value in dictionary_name.values():
    # Loop body...
```

In the first `for` loop, each time the code repeats, the loop variable
`key` gets assigned one of the key names from the dictionary. In the second
loop, the variable `value` gets assigned a new value each iteration.

{{% notice blue Note "rocket" %}}
We do not have to use the name `key` or `value` for the loop variable,
but doing so helps keep our code clear.
{{% /notice %}}

### Loop by Key/Value Pairs

The `items()` method returns each key/value pair as a unit, and it allows us
to assign BOTH the key and value from the dictionary to separate variables. The
general syntax for this is:

```python
for (key, value) in dictionary_name.items():
```

In the `for` statement, we define a pair of variables `(key, value)` to
hold a key name and its linked value from the dictionary. Each iteration, these
two variables represent a new key/value pair from the collection.

{{% notice blue Example "rocket" %}}
Compare the following two loops, which do exactly the same thing:

```python {linenos=table}
comics = {
    'Gary Larson' : 'The Far Side',
    'Terri Libenson' : 'Pajama Diaries',
    'Hilary B. Price' : 'Rhymes with Orange',
    'Jim Toomey' : "Sherman's Lagoon"
}

# Iterate by keys, and print out the dictionary key/value pairs:
for key in comics.keys():
    print(key, comics[key])

# Iterate by key/value pairs:
for (key, value) in comics.items():
    print(key, value)
```

By defining a pair of variables, we can access the values from the
dictionary without needing to use bracket notation. On line 14, the variable
`value` replaces `comics[key]` in our code.
{{% /notice %}}

## Sorting by Keys

Dictionaries are *unordered* collections, so they do NOT include any type of
sorting method. However, sometimes we might want to access or display the
key/value pairs in a particular order---like alphabetically by key name.

If we want to sort a dictionary, the short answer is...we can't. However, we
can use a work-around.

By adding copies of the key names to a separate list, we can sort the list to
get the order we want. Then we use the key names *from the sorted list* to
access the values in the dictionary.

## Check Your Understanding

{{% notice green Question "rocket" %}}
Given the code:

```python {linenos=table}
comics = {
    'Georgia Dunn' : 'Breaking Cat News',
    'Jan Eliot' : 'Stone Soup',
    'Wiley Miller' : 'Non Sequitur',         
    'Bill Watterson' : 'Calvin and Hobbs'
}

for key in comics.keys():
    print(key, comics[key])
```

What is the value of `comics[key]` the *third* time through the loop?

1. `'Wiley Miller'`
1. `'Bill Watterson'`
1. `'Non Sequitur'`
1. `'Calvin and Hobbs'`
<!-- Solution: 3 -->
{{% /notice %}}