+++
title = "Infinite Loops"
weight = 7
originalAuthorGitHub = "gildedgardenia"
+++

Here's the code for a simple `while` loop:

```python {linenos=table}
num = 0

while num < 21:
   print(num)
   num -= 1  
```

What do you think will happen if we run this code?

This is an example of an **infinite loop**, which is a set of code that repeats
forever. 

By using the operator, `-=`, the value of the variable decreases every iteration. The expression `num < 21` will always
return `True`, so the `while` loop will NEVER stop.

## Coding Infinity

Simple mistakes in the code create infinite loops, and everyone
accidentally creates one from time to time.

{{% notice green Tip %}}

When this happens to you, holding down `control-c` will usually force your
program to stop.

{{% /notice %}}

Infinite loops are usually created from small typos or missing statements.
These mistakes set up a situation where the ending condition cannot be reached.

{{% notice blue Example %}}

Here's another infinite while loop. The program is supposed to print a
decreasing total until that total reaches 0.

```python {linenos=table}
start_value = 26
total = start_value

while start_value > 0:
   total -= 5
   print(total)
```

In this case, the update statement is correct (line 5), but the error occurs
in line 4. Instead of using `total` in the boolean expression, we used
`start_value`, which never gets updated in the loop.

{{% /notice %}}

## Check Your Understanding

{{% notice green Question %}}

The following code contains an infinite loop. Which is the BEST explanation for why the loop does not end?

```python {linenos=table}
num = 10
answer = 1

while num > 0:
   answer = answer + num
   num += 1

print(answer)
```

1. `num` starts at 10 and increases by 1 each time through the loop, so it will always be positive.
1. `answer` starts at 1 and increases by `num` each time, so it will always be positive.
1. You cannot compare `num` to 0 in a `while` loop. You must compare it to another variable.

{{% /notice %}}

<!-- Answer = 1 -->