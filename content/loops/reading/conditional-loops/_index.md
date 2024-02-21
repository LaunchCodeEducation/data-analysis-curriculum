+++
title = "Loops with Conditions"
weight = 4
originalAuthorGitHub = "gildedgardenia"
+++

In the last chapter, we learned how to use conditionals
to decide which block of code to run. In this chapter, we use loops to repeat a
set of statements multiple times. Now you might wonder how you can combine loops and conditionals.

## Repeating a Check

Check out the following code samples to see how each one behaves.

{{% notice blue Example %}} 

```python {linenos=table}
num = 13

for number in range(num):
   if number%3 == 0:
      print(number, "is divisible by 3.")
   else:
      print(number, "is NOT divisible by 3.")
```

In this first loop, the text displayed in the console depends on whether the
condition `number%3 == 0` returns `True`. If `number` is evenly
divisible by 3, then line 5 runs. Otherwise, line 7 runs.

```python {linenos=table}
text = 'Coding ROCKS!'
num_vowels = 0

for char in text:
   if char in 'aeiou':
      num_vowels += 1

print(text, "contains", num_vowels, "lowercase vowels.")
```

In the second loop, the condition `char in 'aeiou'` returns `True` if
the value of `char` matches any part of the string. When this happens,
`num_vowels` gets increased by 1 (line 6). `Coding ROCKS!` contains 2
lowercase vowels, so line 6 only runs 2 times. For every other character in
the string, the line gets skipped.

{{% /notice %}}

## Looping with If

We can also place a loop inside any of the code blocks of an `if/elif/else`
statement.

{{% notice blue Example %}}

```python {linenos=table}
if condition:
   for var_name in range(value):
      # Loop body
elif other_condition:
   for char in string:
      # Loop body
else:
   for step in range(20):
      print("Python ROCKS!")
```

Set up this way, only one of the three loops will run:

1. IF `condition` is `True`, the `for` loop starting on line 2 runs.
1. IF `condition` is `False` and `other_condition` is `True`, then
   the loop starting on line 5 runs.
1. IF `condition` and `other_condition` both return `False`, then
   `Python ROCKS!` gets printed 20 times by the last loop.

{{% /notice %}}

Placing a loop inside a conditional allows us to choose when the loop body
should run.