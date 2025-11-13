+++
title = "Function Output"
draft = false
weight = 5
+++

The final part of the function machine is the function providing output.
Let's take a look at function output in greater detail.

## Return Statements

Some functions return values that are useful. 
In particular, the type conversion functions convert input to the specified data type 
and return the result---calling `int("3")` returns the integer value `3`.

### Returning a Value

To return a value from functions that *we* create, we can use a **return statement**. A return statement has the form:

```python
return some_val
```

where `some_val` is any value.

{{% notice blue Example %}}

This function has a single parameter, `n`, which is expected to be a
positive integer. It returns the sum 1+2+...+n.

```python {linenos=table}
def sum_to_n(n):
   sum = 0
   for i in range(n+1):
      sum += i
   return sum

print(sum_to_n(3))
```

**Console Output**

```console
6
```

{{% /notice %}}

Notice that `sum_to_n` does not print anything; the output comes from the final
line of the program, which prints the value *returned by* the function call
`sum_to_n(3)`.

Now that we have return statements in our coding toolbox, we will very rarely
print anything *within* a function. If we want to see the value returned by a
function then we must print it *after* calling the function.

### Return Terminates Function Execution

When a return statement executes, the function terminates, regardless of whether or not there is any code following the return statement. This means that you must be careful to use `return` only when the work of the function has been completed.

{{% notice blue Example %}}

This `print()` statement in this function never executes, since the function returns before it is reached.

```python {linenos=table}
def past_the_point_of_return():
   return "I'm done!"
   print("This will not be printed")

print(past_the_point_of_return())
```

**Console Output**

```console
I'm done!
```

{{% /notice %}}

We can use the fact that `return` stops the execution of a function intentionally, to force a function to stop execution.

{{% notice blue Example %}}

This function prints out the integers 1...n using an infinite `while` loop, which nonetheless terminates when the `return` statement is executed.

```python {linenos=table}
def count_to_n(n):
   count = 1
   while True:
      if count > n:
         return
      print(count)
      count += 1
```

{{% /notice %}}

### Boolean Functions

A function that returns a boolean value is known as a **boolean function**. Perhaps the simplest such function is one that tests an integer to determine if it is even.

{{% notice blue Example %}}

```python {linenos=table}
def is_even(n):
   if n % 2 == 0:
      return True
   else:
      return False

print(is_even(4))
print(is_even(7))
```

**Console Output**

```console
True
False
```

{{% /notice %}}

It is conventional to name boolean functions by starting with either `is` or `has`, which creates a nice semantic effect when reading the code.
For example, reading `is_even(4)` communicates to the reader that the function should answer the question, "Is 4 even?" This is a convention so widely used by programmers that it extends to nearly every language. 

Let's return to the `is_even` function above, to see how we can use the power of return statements to make it even better.

Since `return` terminates the function, we can leave out the `else` clause and have the same effect. This is because if `n` is even, the return statement in the `if` block will execute and the function will end. If `n` is odd, the `if` block will be skipped and the second return statement will execute.

```python {linenos=table}
def is_even(n):
   if n % 2 == 0:
      return True
   return False
```

This updated version works exactly the same as our initial function. 

Additionally, notice that the function returns `True` when `n % 2 == 0` returns `True`, and it returns `False` when `n % 2 == 0` returns `False`.
In other words, the return value is *exactly the same* as the value of `n % 2 == 0`. This means that we can simplify the function even further by returning the value of this expression.

```python {linenos=table}
def is_even(n):
   return n % 2 == 0
```

This version of `is_even` is better than the first two, not because it is shorter (shorter isn't always better), but because it is simpler to read. We don't have to break down the conditional logic to see what is being returned.

Most boolean functions can be written so that they return the value of a boolean expression, rather than explicitly returning `True` or `False`. 

## Check Your Understanding

{{% notice green Question %}}

What does the following code output?

```python {linenos=table}
def plus_two(num):
   return num + 2

a = 2

for i in range(4):
   a = plus_two(a)

print(a)
```

1. 10
1. 12
1. 4
1. 16

{{% /notice %}}

<!-- ans = 10 -->

{{% notice green Question %}}

What does the following function *return*?

```python {linenos=table}
def repeater(str):
   repeated = str + str
   print(repeated)

repeater('Bob')
```

1. `"BobBob"`
1. Nothing (no return value)
1. `undefined`
1. The value of `Bob`

{{% /notice %}}

<!-- ans = Nothing -->