+++
title = "Bracket Notation"
date = 2024-02-20T09:31:05-06:00
draft = false
weight = 2
+++

Strings are *ordered* collections of characters, and this gives us a nice
mental model for how they are put together. Each character has its own specific
location within a string. We call this location the **index**.

Consider the string `'Go Python!'`. The first character, `'G'`, has an index
value of 0, the first `'o'` has index 1, the space `' '` has index 2, and
so on. Index values are integers representing the position of a character
within a given string.

![The string "Go Python!" with index values labeled below each character](pictures/index-figure.png?classes=border)

{{% notice blue Note %}}
This is another example of *zero-based indexing*. The count begins with the value 0.
{{% /notice %}}

## Access One Character

**Bracket notation** is the special syntax that allows us to access the single
characters that make up a string. To access a character, we use the following syntax:

```python
some_string[index]
```

The expression `'school'[2]` selects the character at index `2` and creates
a new string containing just that one character.

With zero-based indexing, the letter at index 0 of `'school'` is `'s'`. So
at position [2] we have the letter `'h'`.

In step 2 above, `this_string[40]` causes an *index out of range* error.
This happens anytime we try to reference an index location that does not exist
in the string.

We will discuss what a negative index value returns in step 3 shortly.

### Expressions for index

If we want to access the *last* character in a string, we need to know its
index value. How can we find this number without having to count all of the
characters?

An index value must either be an integer---like 0, 1, 2, etc.---or an
expression that evaluates to an integer.

Recall that we can use the ``len()`` function to return the number of
characters in a string.

{{% notice blue Example "rocket" %}}
```python
this_string = 'Zero-based indexing!'

print(len(this_string))
```

**Console Output**

```console
20
```

``len(this_string)`` evaluates to 20, and that value gets printed to the
console.
{{% /notice %}}

{{% notice green Tip "rocket" %}}
We can access the last character of the string and avoid the out of range error
by using:

```python
print(this_string[len(this_string) - 1])
```

The expression `len(this_string) - 1` evaluates to `19`, and
`this_string[19]` is the last character (`'!'`).
{{% /notice %}}

## Negative Index Values

Consider the string `'Go Python!'` again. From left to right, the characters
take the index values 0 - 9.

Python also allows us to use index values that move from the end of the string
to the beginning (right to left). In this case, the index values are
*negative* integers.

![The string "Go Python!" with positive and negative index values shown.](pictures/full-string-index.png?classes=border)

Note that when we move from right to left, the index values start with `-1`.

## Slicing

In addition to accessing single characters in a string, we can also use bracket
notation to return multiple characters. This smaller set of characters is
called a **substring** of the original.

A substring is also called a **slice** of the original string. Selecting a
slice is similar to selecting a character, and the syntax is:

```python
some_string[start_index : end_index]
```

With this format, Python returns all of the characters from the `start_index` value up to but NOT including the `end_index`.

### Saving Substrings

When we use brackets to return part of a string, we actually *create a new string*. This new string is a piece of data, and we can perform operations on it like any other string. It can be advantageous to assign the newly created string to a variable whenever we use bracket notation so that the value is stored.

{{% notice blue Example "rocket" %}}
```python
some_string = "Hello Slice"
new_string = some_string[5:11]
print(new_string)
```

```console
Slice
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Which of the following returns `True` given `my_str = 'index'`?  Choose
ALL correct answers.

1. `my_str[2] == 'n'`
1. `my_str[4] == 'x'`
1. `my_str[6] == ' '`
1. `my_str[0] == 'i'`
<!-- Solution: 2 and 4 -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
What is printed by the following code?

```python
phrase = "Python rocks!"
print(phrase[len(phrase) - 9])
```

1. `'o'`
1. `'t'`
1. `'n'`
1. `'c'`
<!-- Solution: 'o'' -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
Given `language = 'Python'`, what does `language[1:5]` return?

1. `"Pyth"`
1. `"Pyt"`
1. `"yth"`
1. `"ytho"`
<!-- Solution: 4 -->
{{% /notice %}}