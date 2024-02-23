+++
title = "Function Input"
draft = false
weight = 4
+++

Earlier in this chapter, we used the image of the function machine, noting that the machine takes
*input* and provides *output*. Let's take a closer look at what we send in to the function.

## Arguments and Parameters

Over the past few sections, we defined two terms that are very similar and
often confused: *arguments* and *parameters*. Both deal with the input we send
to a function. (Remember, input consists of the values that control how the
function does its job).

Seeing the difference between the two terms is tricky, and the easiest way to
clear up the issue is with an example.

{{% notice blue Example %}}

The function `say_hello` takes a single value, which we expect to be a
person's name, and prints a greeting. 

```python {linenos=table}
def say_hello(name):
   print("Hello, {0}!".format(name))

say_hello("Lamar")
say_hello('rutabaga')
```

**Console Output**

```console
Hello, Lamar!
Hello, rutabaga!
```

{{% /notice %}}

In this example, `name` is a **parameter**. It is part of the function
definition, and it behaves like a variable within the function. A parameter
*receives* an input value sent to the function.

The value `"Lamar"` used in the function call on line 4 is an **argument**.
It is a specific value sent by the function call. Similarly, the value
`'rutabaga'` in line 5 is a different argument sent to the `say_hello`
function.

When we call the `say_hello` function in line 4, Python sends the value
`"Lamar"` to the function. Before running the function body, however, Python
assigns that value to the parameter `name`. In the background, Python
completes the statement `name = "Lamar"`.

When we call the `say_hello` function in line 5, Python sends a new
argument to the function and assigns that value to `name` before
running the function code (`name = 'rutabaga'`).

The difference between a parameter and an argument is the same as that between
a variable and a value. A variable *refers to* a specific value, just like a
parameter *refers to* a specific argument when a function is called. Like a
value, an argument is a concrete piece of data.

{{% notice blue Note %}}

**Arguments:** Specific data values sent by the function call to a named
function.

**Parameters:** Variables defined in a function that *receive* data. Python
assigns data to these variables.

{{% /notice %}}

## Mismatched Arguments and Parameters

Let's say we define a function with a single parameter. When we call
that function, what happens if we provide two arguments? What if we call the function but give
no arguments?

In this example, we receive a `TypeError` message each time we call the
`say_hello` function with the wrong number of arguments. As defined in line
1, the function has one parameter, so it *expects* to receive one data value.
When we send the wrong number of arguments, the program crashes with a runtime error, since we did not tell the program how to
deal with missing or extra data.

Read the error messages again, and note that we are given information about why
the program crashed. How useful! The messages tell us how many missing or extra
arguments we used in the function call.

## Default Parameter Values

One way to deal with missing arguments is to provide a *default value* for a
parameter. Since each parameter is just a variable, we can tell Python to
assign it the default value IF its argument is missing from the function call.

The general syntax is:

```python
def function_name(parameter_name = default_value):
```

Applied to the `say_hello` function from the previous example, this looks
like:

{{% notice blue Example %}}

```python {linenos=table}
def say_hello(name = 'World'):
   print("Hello, {0}!".format(name))

say_hello("RBG")
say_hello()
```

**Console Output**

```console
Hello, RBG!
Hello, World!
```

{{% /notice %}}

Now, if we provide an argument in the function call (line 4), Python assigns
that value to `name`. If we do not provide an argument (line 5), Python
assigns the value `'World'` to `name`.

## Check Your Understanding

{{% notice green Question %}}

What does the following code output?

```python {linenos=table}
def string_repeater(a_string):
   repeated = a_string + a_string
   print(repeated)

string_repeater('Bob')
```

1. "BobBob"
1. Nothing (no output)
1. repeated
1. The value of a_string

{{% /notice %}}

<!-- Answer = 1 -->

