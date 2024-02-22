+++
pre = "<b>1. </b>"
title = "List Basics"
date = 2024-02-20T09:31:05-06:00
draft = false
weight = 1
+++

The Python **list** data type is another example of an *ordered collection*.
Lists store data values, which are called **elements**. Just like with strings, each
element has its own index value. However, strings are ordered collections of *characters* and the elements of lists can be of any data type.

![A label, languages, pointing to an array that contains "Python" at index 0, "C#" at index 1, "Java" at index 2, and "JavaScript" at index 3.](pictures/list-diagram.png?classes=border)

## Create a New List

There are several ways to create a new list. The simplest is to enclose the
elements in square brackets `[]`, with each element separated from the others
by commas.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
numbers = [5, 15, 15, 0, 25]
strings = ['banana', 'broccoli', 'kale', 'applesauce']
mixed_data = ["Hello", 42, True, 3.14, [-3, 48.5]]
empty_list = []
```

1. Line 1 assigns a list of five integers to the variable ``numbers``.
1. Line 2 assigns a list of four strings.
1. The elements of a list don’t have to be the same data type! The list in line 3 contains a string, an integer, a boolean, a float, and another list.
1. Line 4 assigns a special list that contains no elements, called the **empty list**.
{{% /notice %}}

{{% notice blue Note "rocket" %}}
A list within another list is said to be *nested*. We will explore this idea
later in the chapter.
{{% /notice %}}

## Accessing Elements

With strings, we accessed individual characters by using square brackets. With lists, we use square brackets to access list elements. The
integer or expression inside the brackets gives the *index* for the element we
want.

Any integer (or an expression that returns a whole number) can be used as the
index. Negative index values identify elements from right-to-left, beginning
at `-1` for the last element in the list.

Besides being ordered collections, Python lists share other similarities with strings.

## List Length

The `len()` function also returns the length of a list (the number of elements in the list).

{{% notice blue Example "rocket" %}}
```python {linenos=table}
letters = ['a', 'b', 'c', 'x', 'y', 'z']

print("The list {0} has {1} elements.".format(letters, len(letters)))
```

**Console Output**

```console
The list ['a', 'b', 'c', 'x', 'y', 'z'] has 6 elements.
```

In line 3, `len(letters)` returns the number of items stored in the
`letters` list.
{{% /notice %}}

Note that the statement `print(letters[len(letters)])` will throw an *index
out of range* error. Since index values start at 0, the last element in any
list will always have a value of `len(list_name) - 1`.

## Combining Lists

Just like strings, we can use the `+` and `*` operators for *concatenation*
and *repetition*. Concatenation combines different lists to create one new,
longer list. Repetition makes multiple copies of the same elements within a
single list.
{{% notice blue Example "rocket" %}}
```python {linenos=table}
first_list = [1, 2, 3]
second_list = [4, 5, 6]

print(first_list + second_list)
print(second_list + first_list)
print(first_list * 3)
```

**Console Output**

```console
[1, 2, 3, 4, 5, 6]
[4, 5, 6, 1, 2, 3]
[1, 2, 3, 1, 2, 3, 1, 2, 3]
```
{{% /notice %}}

## `in` and `not in`

Just like strings, we can use the `in` and `not in` operators to check if a
specific value is present in a list. The operators return `True` or `False`
depending on if the value matches an element.

{{% notice blue Example "rocket" %}}
```python
first_list = [1, 2, 3]

print(10 in first_list)
```

**Console Output**

```console
False
```
{{% /notice %}}

## List Slices

Just like strings, we can return a *slice* (several elements) from a list.
Taking a slice creates a new list, and the syntax should be familiar:

```python
list_name[start_index : end_index]
```

The new list contains the elements from `start_index` up to but NOT including
`end_index`. If we leave out `start_index`, the slice starts at the
beginning of the list. If we leave out `end_index`, the slice continues to
the end of the list.

The index values in the new list begin at 0.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
original_list = [2, 4, 6, 8, 10, 12, 14]

new_list = original_list[2:5]

print(new_list, 'vs.', original_list)
print(new_list[0])
print(original_list[:3])
print(original_list[3:])
```

**Console Output**

```console
[6, 8, 10] vs. [2, 4, 6, 8, 10, 12, 14]
6
[2, 4, 6]
[8, 10, 12, 14]
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}

Identify the length of these two lists. (The answers list `classes` first,
then `teachers`).

```python
classes = ["Chemistry, US History, Intro To Coding"]
teachers = ["Cortez", "Holmes", "Bracey"]
```

1. 1 and 3
1. 3 and 1
1. 3 and 3
1. 1 and 1

<!-- Solution: Answer: 1 -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
Identify the output from the following statements:

```python
a_list = ["Hello", 42, True, 3.14]
print(a_list[2])
```

1. `Hello`
1. `42`
1. `True`
1. `3.14`

<!-- Solution: 3 -->
{{% /notice %}}

<!-- Check Your Understanding
------------------------

.. admonition:: Question

   What is printed by the following code?

   .. sourcecode:: Python
      :linenos:

      a_list = [4, 2, 8, 6, 5, 4]
      print(a_list[3])

   a. 2
   b. 8
   c. 6
   d. 5

.. Answer = c

.. admonition:: Question

   Given ``num_list = [8, 6, 7, 5, 3, 0, 9]``, what does ``num_list[2:5]``
   return?

   a. [7, 5, 3]
   b. [7, 5, 3, 0]
   c. [6, 7, 5]
   d. [6, 7, 5, 3]

.. Answer = a

.. admonition:: Question

   What is printed by the following code?

   .. sourcecode:: Python
      :linenos:

      a_list = [4, 2, 8]
      print(a_list * 2)

   a. [4, 4, 2, 2, 8, 8]
   b. [4, 2, 8, 4, 2, 8]
   c. [8, 4, 16]
   d. The code throws an error.

.. Answer = b

.. admonition:: Question

   Given ``fruit = ["apple", "orange", "banana", "cherry", "tomato", "bell pepper"]``,
   which of the following statements return ``True``? Select ALL that apply.

   a. apples in fruit
   b. pepper in fruit
   c. banana in fruit[:3]
   d. tomato in fruit[1:4]
   e. broccoli not in fruit
   f. orange not in fruit[2:]

.. Answers = c, e, f -->