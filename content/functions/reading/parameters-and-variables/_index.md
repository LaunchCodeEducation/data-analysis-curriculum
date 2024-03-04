+++
title = "Parameters and Variables"
draft = false
weight = 7
+++

Earlier, we said that a parameter "behaves like a variable within the
function." While this is true, the relationship between variables and
parameters is a bit more complicated.

## Function Scope

The **scope** of a variable refers to where that variable is useable within a
program. Scope consists of all locations in a program where a variable can be
used or modified.

A variable is not always usable throughout an entire program. Where it can be used depends on where it
is defined. Parameters and variables defined inside a function are only visible within that function.

## Variable Shadowing

What about variables defined OUTSIDE of a function?

This situation is more complicated. A variable defined outside a
function *may* be visible within the function, but using it or trying to
change its value creates problems.    

{{% notice green Tip %}}

Do NOT define variables inside a function that use the same names found
outside of the function.

{{% /notice %}}

{{% notice blue Example %}}

What if we did something like this:

```python {linenos=table}
def remove_hyphens(phone_number):
   without_hyphens = phone_number.replace('-', '')
   return without_hyphens

phone_number = "614-555-5555"
no_hyph_number = remove_hyphens('56-78')
```

We don't recommend doing this! Are you having trouble interpreting this code?
When the function runs, does `phone_number` on line 2 have the value `"614-555-5555"` or
`'56-78'`? Feel free to run this code in a code editor above to find out.

{{% /notice %}}

An interesting thing happens when a function parameter has the same name as a
variable defined outside of that function.

While the variable `phone_number` declared on line 5 is visible inside
`remove_hyphens`, it is *hidden* by the function parameter with the same
name. When `remove_hyphens('56-78')` is called, and
`phone_number.replace('-', '')` runs, `phone_number` has the value
`'56-78'`, which is the argument passed into the function.

This situation is called **shadowing**. We can imagine that a function
parameter *casts a shadow* over a variable of the same name and hides it from
view.

{{% notice orange Warning %}}

There is NO good reason to allow variable shadowing in your programs! 

*Avoid giving variables and function parameters the same name.*

{{% /notice %}}

## Check Your Understanding

{{% notice green Question %}}

What does the following code output?

```python {linenos=table}
def is_even(num): 
   return num % 2 == 0

num = 42
print(is_even(43))
```

1. `True`
1. `False`

{{% /notice %}}

<!-- Answer = b -->

