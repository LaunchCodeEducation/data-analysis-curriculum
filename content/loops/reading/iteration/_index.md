+++
title = "Iteration"
weight = 1
originalAuthorGitHub = "gildedgardenia"
+++

When repeating the same action over and over again, any human will eventually
make a mistake. Computers, on the other hand, possess the incredible ability to
carry out repetitive tasks without making mistakes.

Suppose you want to print out the integers 0 through 50. With the Python you
currently know, your program would look like this:

```python {linenos=table}
print(0)
print(1)
print(2)
print(3)
print(4)
# and so on...
```

Typing out this code is repetitive, boring, and also error-prone. Even
using copy-paste, the large amount of code makes it likely that we will make a
simple mistake, such as skipping a number or misspelling `print`.

The code is also hard to modify. If we want to make a simple change---such as
printing all the way to 100, or only printing even numbers---then we are forced
to update a large number of lines.

Programming languages provide tools that allow us to repeat a sequence of
statements in a much simpler way.

Repeating the same set of statements again and again is called
**iteration**. This chapter explores two ways Python makes iteration simple and
flexible---the `for` and `while` loops.

To give you a taste of what's to come, here is how we could write the program
above using a `for` loop.

```python {linenos=table}
for num in range(51):
   print(num)
```

We will explore the details soon, but take a moment to marvel how simple this
program is compared to the one above!

## Don't Repeat Yourself

Learning about iteration and loops gives us the chance to introduce one of the
most popular phrases in programming: *Don't Repeat Yourself*, or **DRY**. A
common piece of advice from instructors and experienced programmers is that you
should "Keep your code DRY."

Anytime you find yourself typing the same set of statements over and over
again in a program, little alarm bells should start going off in your head.
Instead of all that typing, consider how you could structure the process so
you only need to write the statements *once*.