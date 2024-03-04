+++
title = "Conditionals"
draft = false
weight = 5
+++

At the beginning of this chapter, we presented an example of an app that tracks
overdue library books.

{{% notice blue Example %}}

Consider an application that reminds you when you have an overdue book. The
app sends you a message *only if* the due date has passed and you have not
returned the book.

{{% /notice %}}

The app sends a message to the user if the condition "the book is overdue" is
`True`.

In Python and other programming languages, **conditional statements** are used
to either run or skip certain parts of the code. If a condition is `True`,
then the program runs a specific block of code. Otherwise, the program ignores
that code and performs a different action.

## `if` Statements

The most basic form of a conditional is an **if statement**. Here's how to
create one in Python:

```python {linenos=table}
if condition:
   # Code statement 1
   # Code statement 2
   # Code statement 3
   # etc.
```

**Syntax Notes:**

1. The `if` statement consists of a header line and a body. The header line
   begins with the keyword `if` followed by a condition and then a
   colon (`:`).
1. `condition` is a boolean expression, which returns either `True` or
   `False`. Examples include `name == 'Jack'` or `points > 10`.
1. The statements underneath the header make up a **code block** (lines
   2 - 5). Note that these statements MUST be indented, and the code block
   can be any size.
1. The indented code runs if the condition evaluates to `True`. If the
   condition is `False`, this code gets ignored.
1. *The first unindented line marks the end of the if statement*.

Here is an example that checks the length of a string:

```python {linenos=table}
text = "Don't Panic"

if len(text) >= 10:
   print(text, "has more than 10 characters.")
```

`len(text)` returns the number of characters in the string stored in
`text`. If the comparison is `True`, then line 4 prints the message to the
console. If the string is less than 10 characters long, then no message
appears.

{{% notice blue Note %}}

Should you indent with tabs or spaces? This question usually starts BIG
arguments within the programming world.

Many code editors automatically indent the lines within an `if` block, so most
of the time you won't need to worry about how far to move in the cursor.
However, here are the accepted guidelines for Python:

1. Use SPACES, not tabs
1. Four spaces are preferred
1. Indentation must be consistent within a code block.

{{% /notice %}}

## `else` Clause

The example above either prints a message or nothing at all, depending on the
value of `num`. What if we ALWAYS want to print something, but we want the
message to change based on the value of `num`?

Adding an **else clause** to an `if` statement allows us to include code that
runs when the condition is `False`.

This structure is known as an **if/else statement**, and it allows our program
to **branch**. The flow of the program takes one of two paths when it reaches a
conditional, depending on whether the condition is `True` or `False`.

## Check Your Understanding

Use the code below to answer the following questions:

```python {linenos=table}
name = input('Please enter a username: ')

if len(name) >= 8:
   print("Welcome, " + name + "!")
else:
   print("Invalid username.")
```

{{% notice green Question %}}

What message gets printed if the user enters `"Aaliyah"` as their username?

1. Invalid username.
1. Welcome, name!
1. Welcome, Aaliyah!
1. Nothing is printed.

{{% /notice %}}

<!-- 1 -->

{{% notice green Question %}}

Assume that you replace line 3 with `if len(name) < 5:`. When would `Invalid username` get printed?

1. For any name with 4 characters or less
1. For any name with 5 characters or less
1. For any name with 4 characters or more
1. For any name with 5 characters or more

{{% /notice %}}

<!-- 4 -->

{{% notice green Question %}}

If you want to print the welcome message for any username SHORTER than 20
characters, how should you change line 3?

1. `if len(name) > 20:`
1. `if len(name) >= 20:`
1. `if len(name) < 20:`
1. `if len(name) <= 20:`

{{% /notice %}}

<!-- 3 -->