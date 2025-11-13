+++
title = "Studio: Functions"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 3
+++

The `reverse` list method flips the order of the elements within a list.
However, `reverse` does not affect the digits or characters *within* those
elements.

{{% notice blue Example %}}

```python {linenos=table}
fun_list = ['hello', 'world', 123, 'orange']

fun_list.reverse()
print(fun_list)
```

**Console Output**

```console
['orange', 123, 'world', 'hello']
```

{{% /notice %}}

What if we wanted the reversed list to be
`['egnaro', 321, 'dlrow', 'olleh']`?

Let's have some fun by creating a process that reverses BOTH the order of the
entries in an list AND the order of characters within the individual elements.

Remember that a function should perform only one task. To follow this best
practice, we will solve the list reversal by defining two functions - one that
reverses the characters in a string (or the digits in a number) and one that
flips the order of entries in the list.

To get started on the studio, open up `data-analysis-projects/functions/studio/functions-studio.py`.

## Reverse Characters

1. In order to create this function, let's review some string methods and 
   list methods we learned about earlier. 
   Using these built-in methods, we can create a function that will not
   only reverse the order of elements, but the characters contained within each element.

   1. Define the function as `reverse_characters`. Give it one parameter, which will
      be the string to reverse.
   1. Within your function, use the `list` function to split the 
      string into a list of individual characters.
   1. `reverse` your new list.
   1. Use `join` to create the reversed string and *return* that string from the
      function.
   1. Create a variable of type string to test your new function.  (See suggestions below)
   1. Use `print(reverse_characters(my_variable_name))` to call the function and verify
      that it correctly reverses the characters in the string.
   1. *Optional*: Use method chaining to reduce the lines of code within the
      function.

{{% notice green Tip %}}

Use these sample strings for testing:

1. `'apple'`
1. `'LC101'`
1. `'Capitalized Letters'`
1. `'I love the smell of code in the morning.'`

{{% /notice %}}

## Reverse Digits

2. The `reverse_characters` function works great on strings, but what if the
   argument passed to the function is a number type? Using
   `print(reverse_characters(1234))` results in an error, since
   `split` only works on strings. When passed a number, we want the
   function to return a number with all the digits reversed (e.g. 1234 converts
   to 4321 and NOT the string `"4321"`).

   1. Add an `if` statement to `reverse_characters` to check the `type` the
      parameter.
   1. If `type` is `str`, return the reversed string as before.
   1. If `type` is `int` or  `float`, convert the parameter to a string, reverse the
      characters, then convert it back into a number.
   1. Return the reversed number.
   1. Be sure to print the result returned by the function to verify that your code
      works for *both strings and numbers*. Do this before moving on to the
      next exercise.

{{% notice green Tip %}}

Use these samples for testing:

1. `1234`
1. `'LC101'`
1. `8675309`
1. `'radar'`

{{% /notice %}}

## Complete Reversal

3. Now we are ready to finish our complete reversal process. Create a new
   function with one parameter, which is the list we want to change. The
   function should:

   1. Define and initialize an empty list.
   1. Loop through the old list.
   1. For each element in the old list, call `reverse_characters` to flip the
      characters or digits.
   1. Add the reversed string (or number) to the list defined in part 'a'.
   1. Return the final, reversed list.
   1. *Be sure to print the results from each test case in order to verify your
      code*.

{{% notice green Tip %}}

Use this sample data for testing.

| Input | Output |
|-------|--------|
| `['apple', 'potato', 'Capitalized Words']` | `['sdroW dezilatipaC', 'otatop', 'elppa']` |
| `[123, 8897, 42, 1138, 8675309]` | `[9035768, 8311, 24, 7988, 321]` |
| `['hello', 'world', 123, 'orange']` | `['egnaro', 321, 'dlrow', 'olleh']` |

{{% /notice %}}

## Submitting Your Work

Copy the URL to your GitHub repo and paste it in the submission box on the Canvas assignment page.
