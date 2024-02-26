+++
title = "More on Range"
weight = 3
originalAuthorGitHub = "gildedgardenia"
+++

In one example from the last section, we used `range` to make the loop run
four times:

```python {linenos=table}
for num in range(4):
   print(num)
   print("Hello" * num)
```

For each iteration, the variable `num` took on a new value (0, 1, 2, or 3).

What if we wanted the loop to use the sequence 1, 2, 3, 4 instead?

## Set Start and Stop Values

Whenever we use `range(value)` in a `for` statement, Python always begins
counting with 0. To start counting at a different number, we need to include
that value inside the `()` in addition to a stop value.

Instead of `range(value)`, a more detailed version of the keyword is
`range(start_value, stop_value)`. The starting value is included in the
counting for the loop, but the stop value is not.

```python {linenos=table}
for num in range (start_value, stop_value):
   # do something...
```

If we replaced line 1 in the code above with `for num in range(1, 5)`, then
the loop variable `num` would take values of 1, 2, 3, and 4.

Now, what if we want to count DOWN from one value to another or change the 
loop variable by more than a single unit each iteration?

## Set a Step Value

Suppose we want our loop variable to only be a set of even numbers (e.g. 0, 2,
4, 6...). We want to begin counting at 0 and then increase the loop variable
by 2 units instead of 1.

To make this happen, we need to add one more value inside `range`. This is
called the **step value**.

```python {linenos=table}
for num in range(start_value, stop_value, step_value):
   # do something ...
```

{{% notice blue Example %}}

To count from 0 to 20 by 2's, use:

```python 
for num in range(0, 21, 2)
```

To count up by 5's, use:

```python
for num in range(0, 21, 5)
```

We can even count DOWN from a higher number to a lower one. The step value
just needs to be negative:

```python
for num in range(50, 39, -1)   # Counts from 50 down to 40
```

{{% /notice %}}

{{% notice blue Note %}}

For `range()`, the start and step values are OPTIONAL.

{{% /notice %}}

## Check Your Understanding

{{% notice green Question %}}

In the command `range(3, 10, 2)`, the second argument (`10`) specifies that `range` should:

1. generate a set of values that stops at 9 (including 9).
1. generate a set of values that starts at 10 (including 10).
1. generate a set of values starting at 3 that stops at 10 (including 10).
1. generate a set of values using every 10th number between 3 and 10.

{{% /notice %}}
   
<!-- Answer = 1 -->

{{% notice green Question %}}

What command correctly generates the values `2, 5, 8` in that order?

1. `range(2, 5, 8)`
1. `range(2, 8, 3)`
1. `range(2, 10, 3)`
1. `range(8, 1, -3)`

{{% /notice %}}

<!-- Answer = 3 -->

{{% notice green Question %}}

What happens if you give range only one argument, like `range(14)`?

1. It will generate a set of values starting at 1 and ending with the number in the ().
1. It will generate a set of values starting at 1 up to but NOT including the number in the ().
1. It will generate a set of values starting at 0 and ending with the number in the ().
1. It will generate a set of values starting at 0 up to but NOT including the number in the ().

{{% /notice %}}

<!-- Answer = 4 -->