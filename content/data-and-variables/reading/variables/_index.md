+++
title = "Variables"
date = 2024-02-08T11:11:06-06:00
draft = false
weight = 3
+++

One of the most powerful features of a programming language is the ability to manipulate variables.
A **variable** is a name that refers to a value.
Recall that a value is a single, specific piece of data, such as a specific number or string.
Variables allow us to store values for later use.

A useful visual analogy for how a variable works is that of a label that *points to* a piece of data. 

![A label, programmingLanguages, pointing to string value "JavaScript"](pictures/variable.png?classes=border)

In this figure, the name `programmingLanguage` points to the string value `"JavaScript"`. 
This is more than an analogy, since it also is representative of how a variable and its value are stored in a computer's memory.

With this analogy in mind, let's look at how we can formally create variables in Python.

## Assigning Values

**Assignment statements** create new variables and also give them values to
refer to. The syntax for an assignment statement is:

```python
variable_name = value
```

The assignment statement links a name, on the left hand side of the `=`, with
the value on the right hand side. The *value* refers to any type of data.

{{% notice blue Example "rocket" %}}
```python
message = "Python ROCKS!"
num = 17
pi = 3.14159
```
{{% /notice %}}

This example makes three assignments. The first assigns the string value
`"Python ROCKS!"` to a new variable named `message`. The second gives the
integer `17` to `num`, and the third assigns the float `3.14159` to a
variable called `pi`.

{{% notice orange Warning "rocket" %}}
The `=` sign does NOT work both ways. `17 = num` causes an error. The
variable name MUST be on the left, and the value MUST be on the right.
{{% /notice %}}

One common mistake is to confuse the assignment operator `=` with the idea of
equality (things being the same). *Equality* compares two values, like `5`
vs. `4` or `'dog'` vs. `'dog'`. *Assignment* gives a value to a variable.

We will explore *equality* later and see that it uses the `==` operator
instead of `=`.

## Evaluating Variables

Once we create a variable and assign it a value, we can use the variable name to refer to that value.

{{% notice blue Example "rocket" %}}
These two examples give the exact same output.

```python
print("Hello, World!")
```

```python
message = "Hello, World!"
print(message)
```
{{% /notice %}}

In the second example just above, the variable name `message` points to the 
value `"Hello, World"`. `print(message)` means the same thing as `print("Hello, World!")`, so we
say that `message` **evaluates to** `"Hello, World!"`

{{% notice blue Example "rocket" %}}
```python {linenos=table}
message = "Python ROCKS!"
num = 17
pi = 3.14159

print(message)
print(num)
print(pi)
```

**Console Output**

```console
Python ROCKS!
17
3.14159
```
{{% /notice %}}

In each case, the printed result is the value of the variable. 

Like values, variables also have types. We determine the type of a variable the same way we determine the type of a value, using `type()`.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
message = "What's up, Doc?"
n = 17
pi = 3.14159

print(type(message))
print(type(n))
print(type(pi))
```

**Console Output**

```console
<class 'str'>
<class 'int'>
<class 'float'>
```
{{% /notice %}}

The type of a variable is the type of the data it currently refers to.

## Reassigning Variables

We use variables in a program to store values, like the current score at
a football game. Just like a score, variables can change over time.

To see this, read and then run the following program. Notice how we change the
value of `day` three times. We even give it a value of a different data type.

```python {linenos=table}
day = "Thursday"
print(day)

day = "Friday"
print(day)

day = 21
print(day)
```

A great deal of programming involves asking the computer to remember things.
For example, we might want to keep track of the number of missed calls on our
phones. Each time we miss another call, we can update a variable to reflect the
new total.

## Check Your Understanding

{{% notice green Question "rocket" %}}
What is printed when the following code executes?

```python {linenos=table}
day = "Thursday"
day = 32.5
day = 19
print(day)
```

1. Nothing is printed. A runtime error occurs.
1. `Thursday`
1. `32.5`
1. `19`
{{% /notice %}}

{{% notice green Question "rocket" %}}
How can you determine the type of a variable?

1. Print out the value and determine the data type based on the value printed.
1. Use `type()`.
1. Use it in a known equation and print the result.
1. Look at the declaration of the variable. 
{{% /notice %}}