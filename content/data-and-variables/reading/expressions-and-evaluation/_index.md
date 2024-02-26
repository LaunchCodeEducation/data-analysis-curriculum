+++
title = "Expressions and Evaluation"
date = 2024-02-08T11:11:06-06:00
draft = false
weight = 5
+++

An **expression** is a combination of values, variables, operators, and calls to functions. An expression can be thought of as a formula that is made up of multiple pieces.

The *evaluation* of an expression produces a value, known as the **return value**. We say that an expression **returns** a value.

Expressions need to be evaluated when the code executes in order to determine the return value, or specific piece of data that should be used. Evaluation is the process of computing the return value.

If you ask Python to print an expression using `print()`, the interpreter **evaluates** the expression and displays the result.

{{% notice blue Example "rocket" %}}
```python
print(1 + 1)
```

**Console Output**

```console
2
```
{{% /notice %}}

This code prints not `1 + 1` but rather the *result* of calculating `1 + 1`. In other words, `print(1 + 1)` prints the value `2`. This is what we would expect.

Since evaluating an expression produces a value, expressions can appear on the right-hand side of assignment statements. 

{{% notice blue Example "rocket" %}}

```python
sum = 1 + 2
print(sum)
```

**Console Output**

```console
3
```
{{% /notice %}}

The value of the variable `sum` is the result of evaluating the expression `1 + 2`, so the value `3` is printed.

A value all by itself is a simple expression, and so is a variable. Evaluating a variable gives the value that the variable refers to. This means that line 2 of the example above also contains the simple expression `sum`.