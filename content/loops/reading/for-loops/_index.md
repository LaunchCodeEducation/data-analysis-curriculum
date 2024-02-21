+++
title = "For Loops"
weight = 2
originalAuthorGitHub = "gildedgardenia"
+++

The `for` loop is the first Python tool for iteration that we will explore. 
A **for loop** is typically used for **definite iteration**. 
Definite iteration is the process of repeating a specific task with a specific data set. 
When a `for` loop begins it can usually be determined exactly how many times it will execute: 
once for each item in the data set.

## For Loop Syntax

We have already seen the basic syntax of a `for` loop.

```python {linenos=table}
for num in range(51):
   print(num)

print("Not in the loop!")
```

This program prints the integers 0 through 50, one number per line. 
In the language of definite iteration, we say that the loop has a data set of 0-50, 
and its action is to print a value to the console.

Let's break down this syntax piece by piece, so we can begin to understand how `for` 
loops are structured.

1. In line 1, `num` is called the **loop variable**. Each time the loop
   executes, `num` gets assigned a new value based on the number in the `range`. 
   In this example, `num` will be assigned a value 51 times, starting with 0 and ending at 50.
   More on that later.
1. Line 2 begins the loop body. The loop body is ALWAYS indented. 
   The indentation determines exactly what statements are “in the loop”. 
   In this example, we are printing each value of `num` as we loop through the set range.
1. The *first* unindented line after the `for` statement marks the end of the
   loop body.  In this example, line 4 is not part of the loop.
1. The loop body can contain any number of statements.
1. The number of times the loop body runs depends on the value in `range()`.

### Line By Line

Let's modify the code just a little to follow the operation of a `for` loop.

{{% notice blue Example %}}

```python {linenos=table}
for num in range(4):
   print(num)
   print("Hello" * num)

print("Done!")
```

**Console Output**

```console
0

1
Hello
2
HelloHello
3
HelloHelloHello
Done!
```

{{% /notice %}}

1. The first time Python executes the `for` statement in line 1, `num` is
   assigned a value of `0`.
1. Next, Python checks if the value of `num` is less than the value inside
   `range`. Since `num < 4` evaluates to `True`, the loop body executes.
1. Line 2 prints the current value of `num`.
1. Line 3 prints the string `Hello` zero times.
1. Python reaches the end of the loop body (the indented lines). At this point,
   it increases the value of `num` by 1 and then MOVES BACK TO THE `for`
   STATEMENT (line 1).
1. The new value of `num` (`1`) gets compared to the `range` value.
   Since `num < 4` still returns `True`, the loop body executes again.
1. Lines 2 and 3 run with the new value of `num`, so we see `1` and
   `Hello` printed to the console.
1. Python again reaches the end of the loop body, increases the value of
   `num` and moves back up to the `for` statement.
1. This process continues until the value of `num` reaches the end of the
   specified `range`. Once the comparison `num < 4` returns `False`, the
   loop ends. Since Python adds 1 after each iteration, this occurs when
   `num` is 4 (so `4 < 4` is `False`). At that point, the loop body will
   have run exactly 4 times, with `num` taking the values 0, 1, 2, and 3.
1. Once the loop finishes, Python proceeds to line 5 and prints `Done!` one
   time.

We can use a diagram to show the *flow of execution* of this `for` loop:

![Diagram showing the flow of a program with a for loop](./pictures/for-loop-diagram.png)

Notice that even though line 1 uses `range(4)`, the value `4` is NOT
included in the output. Why?

### Begin Counting at 0

Iterating a certain number of times is a very common thing to do, and Python
gives us the built-in `range` keyword to provide a set of values for the loop
variable to use.

The sequence provided by `range` always starts with `0`. If you ask for
`range(4)`, then you will get 4 values starting with 0. In other words, 0, 1,
2, and finally 3. Notice that 4 is not included since we started with 0.
Likewise, `range(10)` provides 10 values, 0 through 9. Starting a count at 0
instead of at 1 is called **zero-based indexing** and is very common in
computer programming.

## Check Your Understanding

{{% notice green Question %}}

How does Python know what lines are contained in the loop body?

1. The lines are indented by the same amount from the `for` statement.
1. There is always exactly one line in the loop body.
1. The loop body ends with an empty line.
1. The loop body ends at the next `for` statement.

{{% /notice %}}

<!-- Answer = 1 -->

{{% notice green Question %}}

How many lines does the following code print?

```python {linenos=table}
for number in range(10):
   print("I have", 12 - number, "cookies. I'm going to eat one!")
```

1. 1
1. 9
1. 10
1. 12

{{% /notice %}}

<!-- Answer = 3 -->

{{% notice green Question %}}

For the code above, what is the value of `number` the *third* time Python
executes the loop?

1. 1
1. 2
1. 3
1. 4

{{% /notice %}}

<!-- Answer = 2 -->

{{% notice green Question %}}

For the same code, what is the LAST line printed by the program?

1. `I have 2 cookies. I'm going to eat one!`
1. `I have 3 cookies. I'm going to eat one!`
1. `I have 10 cookies. I'm going to eat one!`
1. `I have 12 cookies. I'm going to eat one!`

{{% /notice %}}
   
<!-- Answer = 2 -->