+++
title = "Defining Our Own Functions"
draft = false
weight = 3
+++

Built-in functions in Python give us a lot of capabilities. We gain even more coding potential by 
writing our own functions.

We’ll start by looking at the general syntax.

## Function Syntax

To create a function, use the following syntax:

```python {linenos=table}
def function_name( parameters ):
   # Code statements...
```

`def` is a keyword that instructs Python to create a new function.

Following `def` is the **function name**, which is the label that Python
attaches to the code. When writing our own functions, the programmer chooses the function name. Like any 
other variable, a function name should describe the purpose of the function. The stronger we make the name,
the less confusion we add to our code. A list of good naming practices appears
in the next section.

Following the function name, we define **parameters** within the parentheses.
Parameters are variables that can only be used within the function itself. We
can define a function with one parameter, multiple parameters, or no parameters
at all.

The number and names of the parameters depends on what we want the function to
do. Parameters specify what information, if any, the function needs in order to
do its job.

The `def` statement ends with a colon.

### Naming Functions

Python function names should follow these rules:

1. Names CANNOT match any Python keyword like `print` or `for`.

   {{% notice green Tip %}}
   
   Most code editors use syntax highlighting to indicate keywords. Paying
   attention to the highlighting helps avoid this naming mistake.

   {{% /notice %}}

1. Names use only lowercase letters.
1. The name should describe exactly what the function does.

   {{% notice green Tip %}}
   
   You should prefer *long, descriptive names* over *short, abbreviated names*.
   If someone unfamiliar with your code can read the function name and tell
   you what it does, then you chose a good name.

   {{% /notice %}}

1. For names with multiple words, separate the words with underscores (e.g.
   `convert_score_to_percentage`).

{{% notice blue Example %}}

**Good**

1. `convert_feet_to_meters`
1. `is_valid_number_entry`
1. `draw_square`

**Not Good**

1. `convert`
1. `is_valid`
1. `draw`

{{% /notice %}}

## Function Code

After the `def` statement comes the **function body**. This is where we code
the action that the function carries out. The function body can contain any
amount of code (statements, loops, conditionals, etc.), but the lines must be
indented when compared to the `def` keyword. Python recognizes the end of the
function body once it finds the first *unindented* line after the `def`
keyword.

{{% notice blue Example %}}

```python {linenos=table}
def add_numbers_together(num):
   total = 0
   while num < 100:
      total += number
      number +=1
   
   return total

print("Hello, World!")
```

Line 1 defines the function name and parameter. Lines 2 - 6 are part of the
function body. Line 89 is even with the `def` keyword, so it is NOT part of
the `add_list_numbers` function.

{{% /notice %}}

## Defining vs. Calling

When we *define* a function, we make it available for later use. However, a
function does NOT run when it is defined. It must be *called* in order to
execute.

{{% notice orange Warning %}}

This is not only a common point of confusion for new programmers, but it can
also cause logic errors!

{{% /notice %}}

## Check Your Understanding

{{% notice green Question %}}

What are the *parameters* of the following function? Click *ALL* that apply.

```python {linenos=table}
def perimeter_of_square(side_length):
   return side_length * 4

print(perimeter_of_square(4))
```

1. `perimeter_of_square`
1. `side_length`
1. `print`

{{% /notice %}}

<!-- Answer = 2 -->

{{% notice green Question %}}

For the same code sample, what are the *arguments* sent by the function call?
Click *ALL* that apply.

1. `square`
1. `side_length`
1. `4`

{{% /notice %}}

<!-- Answers = 3 -->
