+++
pre = "<b>4. </b>"
title = "Tuples"
date = 2024-02-20T09:31:05-06:00
draft = false
weight = 4
+++

Lists and dictionaries are just two of the four built-in collections in Python. The other two are tuples and sets.

## Tuples

Tuples are ordered collections similar to lists, except tuples are *immutable*. However, we can do many of the same things with tuples as we do with lists.
We can save snippets of a tuple in a different tuple, we can iterate over tuples, and access individual elements with their index.
So then, why use a tuple over a list?
Here are a few of the reasons why a programmer might opt for tuples over lists:

1. A tuple and a list of the same size do NOT take up the same amount of space in the computer's memory. Tuples take up less space! While this isn't always a concern in small personal applications, it can be a concern in larger enterprise applications.
1. Tuples take less time! If we want to iterate over a tuple of the same size as a list, it will take the computer less time to go over the tuple. This is another thing where if you are working with a small tuple than you probably won't notice the difference, but if the elements number in the tens of thousands, then you may want to use a tuple to save the computer time.
1. If you have a data set that you want to protect from accidental changes, then using a tuple for storage is a great way to protect it!

While tuples can serve many of the same functions as lists, the syntax is different.
If you want to assign a new tuple, you use parantheses as opposed to brackets.

```python
my_tuple = (1, 2, 3, 4, 5)
```

Let's walk through how to work with tuples. If you have a tuple with students' names, you may want to loop through the list to print out the class roster and then add a student who joins mid-year.

```python {linenos=table}
my_class = ("Sandra", "Deidre", "Mary")

for student in my_class:
    print(student)

my_class = my_class + ("Denise",)

for student in my_class:
    print(student)
```

Because tuples are immutable, to add an element to `my_class`, we have to save the result as a new tuple.
You may also note that when adding an element to a tuple, we had to use a second tuple even if it was only one element.
Tuples with one element must include the comma. If you remove the comma, `("Denise")`, that is not a tuple.

You can also easily convert between lists and tuples using type conversion:

```python {linenos=table}
my_tuple = (1, 2, 3, 4, 5)

my_list = list(my_tuple)

my_new_tuple = tuple(my_list)
```

## Sets

The final collection in Python is a set. Sets are unordered and unindexed. While we will not cover them in this class, you should know that they may come into play later in your data analysis career.
Sets cannot store duplicate values and are highly efficient when it comes to mathematical operations. This makes them great for large amounts of data!

## Check Your Understanding

{{% notice green Question "rocket" %}}
Which of the following is NOT a collection in Python?

1. list
1. dictionary
1. thesaurus
1. set
1. tuple
<!-- Solution: 3 -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
True or false: tuples are immutable.

<!-- Solution: True -->
{{% /notice %}}