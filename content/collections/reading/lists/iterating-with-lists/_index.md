+++
title = "Iterating with Lists"
date = 2024-02-20T09:31:05-06:00
draft = false
weight = 3
+++

We can use a loop to iterate through the elements in a list in the same way we did with the characters in a string.

## Loop by Element

Since a list is simply a sequence of separate data values, Python gives us a
way to automatically iterate over those elements.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
shopping_list_items = ['apples', 'oranges', 'bananas', 'bread', 'toothpaste']

print('You need to buy:')
for item in shopping_list_items:     # Iterate by element
print('\t' + item)           # Print a tab followed by the string assigned to 'item'
```

**Console Output**

```console
You need to buy:
apples
oranges
bananas
bread
toothpaste
```
{{% /notice %}}

The syntax almost reads like natural language: *For each item in
shopping_list_items, print a tab character plus the item*.

Each time the loop repeats, Python assigns the next element in the list to the
variable `item`. The elements may be of any data type.

{{% notice green Tip "rocket" %}}
To keep the meaning of your code clear, use plural names for your
lists---like `fruits`, `cars`, `even_numbers`, etc.

When you iterate through a list, use the singular name for the loop
variable.

1. `for fruit in fruits:`
1. `for car in cars:`
1. `for even_number in even_numbers:`

This helps you explain what your code is doing. For example, in step 2, you
can think to yourself, *Each time the loop repeats, my code takes one
car element from the cars list*.
{{% /notice %}}

## Loop by Index

We can also use the `range` command to generate index values, and then use
bracket notation to access each element from the list:

{{% notice blue Example "rocket" %}}
```python {linenos=table}
shopping_list_items = ['apples', 'oranges', 'bananas', 'bread', 'toothpaste']

for index in range(len(shopping_list_items)):     # Iterate by index
    print("{0}) {1}".format(index+1, shopping_list_items[index]))
```

**Console Output**

```console
1) apples
2) oranges
3) bananas
4) bread
5) toothpaste
```
{{% /notice %}}

Note the following:

1. In this loop, `range(len(shopping_list_items))` generates a sequence of
integers up to but not including the length of the list. Since
`len(shopping_list_items)` returns the value `5`, this list of integers
will be `0, 1, 2, 3, 4`.
1. Each time the loop repeats, Python assigns the next integer in the sequence to the variable `index`.
1. In line 4, note how we use the `index` values to calculate the item numbers and access each element from the list.

1. The `{0}` placeholder gets filled with the value of `index` plus one. Since `index` takes the values 0 - 4, the output shows the line numbers 1 - 5.
1. The `{1}` placeholder gets filled with one element from the list. When `index` is `0`, `shopping_list_items[index]`` returns `'apples'``. The next time the loop repeats, `index` is `1`, and `shopping_list_items[index]` returns `'oranges'`.

## Which Syntax Should We Use?

Should we *loop by element* or *loop by index*? In many cases, the choice comes
down to personal preference. Sometimes, however, one option will be better than
the other.

{{% notice blue Example "rocket" %}}
Given `scores = [10, 25, 8, 33, 0]`, the code shows two ways to add up all
of the values from the list:

```python {linenos=table}
for score in scores:             # Option 1: Loop by element
    total_points += score

for index in range(len(scores)): # Option 2: Loop by index
    total_points += scores[index]
```
{{% /notice %}}

The end result is the same for both loops, `total_points` winds up with a
value of `76`. However, the syntax for looping by element (option 1) is
cleaner, since we do not have to worry about bracket notation.

This example shows doing something WITH the list elements. We access each one
in turn and add it to `total_points`. We do NOT change any of the elements
themselves. `print(scores)` returns `[10, 25, 8, 33, 0]` even after the
loop finishes.

The next example shows a case where we change the values of some list elements:

{{% notice blue Example "rocket" %}}
Given `scores = [10, 25, 8, 33, 0]`, the code below changes the points for
some of the values:

```python {linenos=table}
print(scores)

for index in range(len(scores)):    # Loop by index
    if index >= 2:                   # Check position in list
        scores[index] += 12           # If True, increase the value of the element

print(scores)
```

**Console Output**

```console
[10, 25, 8, 33, 0]
[10, 25, 20, 45, 12]
```
{{% /notice %}}

Take a moment to think about what happens inside this loop. We change the
value of an element based on its *position* in the list. 
   
1. Each time the loop runs, `index` gets assigned the next value in the
sequence `0, 1, 2, 3, 4`.
1. Line 4 checks if the element in the list is at index 2 or later. If
`True`, we add 12 points to the value.
1. We use the bracket notation in line 5 to change the value of the selected
element.

We can also change list elements based on their values instead of their
locations:

{{% notice blue Example "rocket" %}}
```python
print(scores)

for index in range(len(scores)):    # Loop by index
    if scores[index]%2 == 0:         # Check if the current score is even
        scores[index] *= 2            # If True, double the score

print(scores)
```

**Console Output**

```console
[10, 25, 8, 33, 0]
[20, 25, 16, 33, 0]
```

1. Line 4 checks if the value for the current list element is even.
1. If `True`, line 5 doubles the value and reassigns it to the same
index location in the list.
{{% /notice %}}

Since lists are mutable, we can use a loop to change some or all of the
elements. To do this, we must know the *position* of the element in the list,
and this requires an index value.