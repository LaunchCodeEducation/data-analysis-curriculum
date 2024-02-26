+++
title = "Type Conversion"
date = 2024-02-08T11:11:06-06:00
draft = false
weight = 2
+++

Sometimes it is necessary to convert values from one type to another.
A common example is when a program receives input from a user or a file.
In this situation, numeric data may be passed to the program as strings.

**Type conversion** is the process of converting a variable of one type to another type. In Python, we can do this using either **implicit type conversion** or **explicit type conversion**.

Implicit type conversion is when Python converts a variable to a different type without any extra effort from us as programmers.
For example, if you add a variable of type `int` and a variable of type `float` together, the resulting sum is a float.
With implicit type conversion, Python will always convert to a larger data type so no data is lost. 

{{% notice blue Note "rocket" %}}
If you try to add an integer and a string together, you may notice that Python cannot convert the result to a data type. 
While implicity type conversion is a handy trick, it doesn't work in every scenario!
{{% /notice %}}

Explicit type conversion uses functions such as `int()`, `str()`, and `float()` to convert variables of one type to another.

The `int()` function can take a string and turn it into an integer. Let us see this in action:

{{% notice blue Example "rocket" %}}
```python
print(int("2345"))
print(type(int("2345")))
print(int(17))
```

**Console Output**

```console
2345
int
17
```
{{% /notice %}}

What happens if we attempt to convert a string to an integer, and the string doesn't directly represent an integer?

{{% notice blue Example "rocket" %}}
```python
print(int("23bottles"))
```

**Console Output**

```console
ValueError: invalid literal for int() with base 10: '23bottles'
```
{{% /notice %}}

This example shows that a string has to be a syntactically legal number for conversion to go as expected.
Examples of such strings are `"34"` or `"-2.5"`.
If the value cannot be cleanly converted to a number then `ValueError` will be returned, which means that the value of our string is not compatible as a number

The type conversion function `str()` turns its argument into a string.
Remember that when we print a string, the quotes may be removed.
However, if we print the type, we can see that it is definitely `'string'`.

{{% notice blue Example "rocket" %}}
```python
print(str(17))
print(str(123.45))
print(type(str(123.45)))
```

**Console Output**

```console
17
123.45
string
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Which of the following strings result in `ValueError` when passed to `int()`? (Feel free to try running each of the conversions.)

1. `'3'`
1. `'three'`
1. `'3 3'`
1. `'33'`
{{% /notice %}}