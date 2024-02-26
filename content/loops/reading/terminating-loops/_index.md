+++
title = "Ending Loops with a Break"
weight = 8
originalAuthorGitHub = "gildedgardenia"
+++

Python, like most programming languages, provides a way to stop a loop before it
would normally finish. The `break` keyword immediately stops the execution of
the loop. Program flow then continues with the next line of code below the loop.

{{% notice blue Example %}}

```python {linenos=table}
for iteration in range(42):
   print('This is iteration number:', iteration+1)

   if iteration > 4:
      break

print("The loop is done!")
```

**Console Output**

```console
This is iteration number: 1
This is iteration number: 2
This is iteration number: 3
This is iteration number: 4
This is iteration number: 5
This is iteration number: 6
The loop is done!
```
   
1. Line 2 repeats 6 times with values of `iteration` from 0 to 5.
1. The sixth time through the loop, `iteration` is 5 and the condition in
   line 4 (`iteration > 4`) evaluates to `True` for the first time.
1. As a result, the program flow reaches the `break` statement. The loop
   immediately stops, even though `range(42)` would normally keep the loop
   going.
1. Control moves to the first line of code after the loop.

{{% /notice %}}

Why would we need to use `break`? After all, we tell Python how many times
the loop should repeat in the `for` statement.

In some cases, you may want to provide a *second* ending condition. For
example, let's say you need to search through 100,000 items, and you find the
one you want after 5 iterations. In this case, there is no need to wait for the
loop to finish on its own. Adding a `break` statement will speed up your
program, especially if you need to use that large range multiple times.

The `break` statement can also be used within a `while` loop. 

{{% notice blue Note %}}

There is another command that interrupts a single iteration of a loop but
does not end the loop completely. This is the `continue` statement.

However, `continue` is rarely used, and we will not discuss it in detail
here. If you are curious, you can find more information at
[Tutorials Point](https://www.tutorialspoint.com/python/python_loop_control.htm).

{{% /notice %}}