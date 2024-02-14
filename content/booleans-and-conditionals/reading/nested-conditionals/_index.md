+++
title = "Nested Conditionals"
draft = false
weight = 8
+++

By using an `if/else` statement, we produce two branches for our code to
follow. We can add more branches to our program flow by combining conditionals.

Let's see how this works by solving the following problem:

{{% notice blue Example %}}

Write a program that:

1. Prompts the user to enter a whole number.
1. If the number is odd, print nothing.
1. If the number is even, print "EVEN!" If the number is also positive,
   print "POSITIVE".

{{% /notice %}}

Our first attempt at a solution might look like this:

```python {linenos=table}
entry = int(input('Enter a whole number: '))

if entry%2 == 0:
   print("EVEN!")

if entry > 0:
   print("POSITIVE")
```

**Console Output**

```console
Enter a whole number: 7

POSITIVE
```

When we enter `7` in the prompt, we want the program to print nothing. However,
we see the output `POSITIVE`. The code doesn't work as we want. Why not?

Written this way, the two conditionals are separate from each other. The result
from one has no influence on the other. Checking `entry` as even or odd works
fine on its own. However, the second check gets carried out whether or not
`entry%2 == 0` is `True` or `False`. Remember, the `if` condition
does not apply after the first unindented line. 

We want to check if `entry` is positive only if the number is even. To do
this, we need to put the second conditional inside the first. This code
structure is called a **nested conditional**. The result of the first
conditional determines whether or not to consider the second.

Notice that when we put one conditional inside another, the body of the nested
conditional is indented by two levels rather than one. In Python, the indentation 
of an `if` statement determines if it is nested. For an `if`
statement to run inside another, it must be indented more than the outer conditional. 

## Nesting Also Works With `else`

In the examples above, we left out the `else` clauses from the conditionals. Here is how we could add the `else` clauses back in.

```python {linenos=table}
word = input('Please enter a word that is longer than 4 characters: ')

if len(word) == 4:
   print("We need you to think of a word that is longer than 4 characters.")
else:
   if len(word) < 4:
      print("You can think of a longer word than that!")
   else:
      print("Excellent word!")
```

{{% notice green Tip %}}

In Python, the amount of indentation tells us exactly which `else` clause belongs to which `if` statement.

{{% /notice %}}

## Check Your Understanding

{{% notice green Question %}}

What is printed when the following code runs?

```python {linenos=table}
num = 7

if num % 2 == 0:
   if num % 2 == 1:
      print("odd")
```

1. The code won't run due to invalid syntax.
1. odd
1. even
1. The code runs but doesn't print anything.

{{% /notice %}}

<!-- 4 -->

{{% notice green Question %}}

What is printed when the following code runs?

```python {linenos=table}
answer_1 = 'yes'
answer_2 = 'no'


if answer_1 == 'yes':
   if answer_2 == 'yes':
      print("Both of you agree!")
   else:
      print("You two need to work this out.")
else:
   if answer_2 == 'yes':
      print("Stop arguing and work it out.")
   else:
      print("Clean your bathroom anyway!")
```

1. Both of you agree!
1. You two need to work this out.
1. Stop arguing and work it out.
1. Clean your bathroom anyway!

{{% /notice %}}

<!-- 2 -->