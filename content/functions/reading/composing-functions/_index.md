+++
title = "Functions Calling Other Functions"
draft = false
weight = 8
+++

Once we define a function, we can call it on its own (line 5), as part of a conditional (line 7),
or from inside of a loop (line 10).

{{% notice blue Example %}}

```python {linenos=table}
def double_number(num):
   return num*2

integer = 8
result = double_number(integer)
print(result)

if integer > 5:
   result = double_number(integer)
   print(result)

for number in range(10):
   result = double_number(number)
   print(result)
```

{{% /notice %}}

Even better, we can call one function from INSIDE another function.

## Functions Should Do Exactly One Thing

When writing a function, we should pay attention to its size. Functions work best when they are
small and do only one thing.

Consider the `make_sandwich` function from an
earlier section. What if we wanted to expand our
program to not only make a sandwich, but also to pour a drink. It would be a
bad idea to write one function to do both (`make_sandwich_and_pour_drink`).
What if a customer wants only one thing---a sandwich or a drink?

A much better solution would look like this:

```python {linenos=table}
def make_sandwich( parameters ):
   # make the sandwich

def pour_drink( parameters ):
   # pour the drink

def make_lunch( parameters ):
   make_sandwich( sand_arguments )
   pour_drink( drink_arguments )
```

Why is this better? First, smaller functions are easier to debug. Also, by
assigning single jobs to separate functions, we make our code easier to read
and more reusable.

Looking at the `make_lunch` function, it is very clear what is going on.
It makes a sandwich first, and then it pours a drink.

If the `make_lunch` function held all of the code needed to do *both* tasks,
there would be no clear separation between one job and the other.
