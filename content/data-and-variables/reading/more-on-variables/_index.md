+++
title = "More on Variables"
date = 2024-02-08T11:11:06-06:00
draft = false
weight = 4
+++

The previous section covered creating, evaluating, and reassigning variables.
This section will cover some additional, more nuanced topics related to
variables.

## Naming Variables

### Valid Variable Names

As you may have discovered already, not just any sequence of characters is a
valid variable name. For example, if we try to declare a variable with a name
containing a space, Python complains.

{{% notice blue Example "rocket" %}}
```python
application name = "Planning App"
```

**Console Output**

```console
SyntaxError: Invalid syntax
```
{{% /notice %}}

Python provides a broad set of rules for naming variables, but there is no
reason to go beyond a few easy-to-remember guidelines:

1. Use only the characters 0-9, a-z, A-Z, and underscore. In other words, do not use special characters or whitespace (space, tab, and so on).
1. Do not start a variable name with a number.
1. Do not use **keywords**, which are words reserved by Python for use by the language itself. We'll discuss these in detail in a moment.

Following these guidelines will prevent you from creating illegal variable
names. While this is important, we should also strive to create good variable
names.

### Good Variable Names

Writing good code is about more than writing code that simply works and
accomplishes the task at-hand. It is also about writing code that can be read,
updated, and maintained as easily as possible. How to write code that achieves
these goals is a theme we will return to again and again.

One of the primary ways that code can be written poorly is by using bad
variable names. For example, consider the following program. While we haven't
introduced each of the components used here, you should be able to come to a
general understanding of the new components.

```python
x = 5
Y = 3.14
z = Y * x ** 2
print(z)
```

Understanding what this program is trying to do is not obvious, to say the
least. The main problem is that the variable names `x`, `Y`, and `z` are
not descriptive. They don't tell us anything about what they represent, or how
they will be used.

> Variable names should be descriptive, providing context about the data they contain and how they will be used.

Let's look at an improved version of this program.

```python
radius_of_circle = 5
PI = 3.14
area_of_circle = PI * radius_of_circle ** 2
print(area_of_circle)
```

With improved variable names, it now becomes clear that the program is calculating the area of a circle of radius 5.

{{% notice green Tip "rocket" %}}
When considering program readability, think about whether or not your code will make sense to another programmer. It is not enough for code to be readable by only the programmer that originally wrote it.
{{% /notice %}}

## Creating Constants

One of the key features of variables that we have discussed so far is their
ability to change value. We can create a variable with one value, and then
reassign it to another value.  

A possible problem with this approach is that an unwitting programmer might change the
value of that same variable later in the program, causing unexpected outcomes.

An easy way to avoid this is by creating **constant** variables.
Constant variables are initialized once and not able to be changed later throughout the program.
No matter how hard you may try.

We will explore constant variables later in this course.  
For now, we suggest being aware of your variable names so you don't accidentally reassign them.


## Keywords

Our last note on naming variables has to do with a collection of words that are reserved for use by the Python language itself. Such words are called **keywords**, or **reserved words**.
Any word that is formally part of the Python language syntax is a keyword.

{{% notice orange Warning "rocket" %}}
While `print()` may seem like a keyword, it is actually slightly different.
It is actually a built-in name that is available by default in Python environments.
Here is an [article](http://python-history.blogspot.com/2013/11/story-of-none-true-false.html) by the Python language designer about the difference between built-in names and keywords if you are interested in learning more.
{{% /notice %}}
   
Attempting to use a keyword for anything other than it's intended use will result in an error.

{{% notice green Tip "rocket" %}}
Most code editors will highlight keywords in a different color than variables or other parts of your code. This serves as a visual cue that a given word is a keyword, and can help prevent mistakes.
{{% /notice %}}
   
We will not provide the full list of keywords at this time, but rather point them out as we learn about each of them. If you are curious, the [full list is available at W3Schools](https://www.w3schools.com/python/python_ref_keywords.asp).
