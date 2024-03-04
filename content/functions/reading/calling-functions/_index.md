+++
title = "Calling Functions"
draft = false
weight = 2
+++

**Calling a function** is the act of running that function and giving it the
information it needs to do its job.

## Making a Function Run

The general syntax for calling a function is:

```python
function_name(input values)
```

You have already become familiar with several Python functions:

1. `print()`
1. `len()`
1. Type conversion functions like `int()`, `str()`, and `list()`
1. String and list methods, such as `find()` or `reverse()`.

Every function works in the same way. By typing the function's name, followed by
parentheses, we *call* the function. This results in an action being carried
out.

Sometimes, we include values inside the parentheses. When we do this, the
function carries out its action with that data.

{{% notice blue Example %}}

The *action* of the `print` function displays information to the console,
while the `int` function returns the integer value from the given input.

```python {linenos=table}
print("Hello, World!")
num = int("23")
print(num)
```

**Console Output**

```console
Hello, World!
23
```

{{% /notice %}}

As programmers, we do not need to know *how* Python prints to the console or
converts a string to an integer. Instead, we just need to be able to ask Python
to do those jobs for us with the data we supply.

{{% notice blue Note %}}

**Arguments** refer to the data values we send to a function. Some functions
do not require arguments inside the parentheses, `()`.

{{% /notice %}}

If a function requires more than one argument, we separate them with commas:

```python
function_name(argument_1, argument_2, ...)
```