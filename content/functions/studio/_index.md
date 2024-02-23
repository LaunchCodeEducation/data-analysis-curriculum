+++
title = "Studio: Functions"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 3
+++

The `reverse` list method flips the order of the elements within an list.
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

## Reverse Characters

1. In order to create this function, let's review some string methods and 
   list methods we learned about earlier. 
   Using these built-in methods, we can create a function that will not
   only reverse the order of elements, but the characters contained within each element.

   a. Define the function as `reverse_characters`. Give it one parameter, which will
      be the string to reverse.
   b. Within your function, use the `list` function to split the 
      string into a list of individual characters.
   c. `reverse` your new list.
   d. Use `join` to create the reversed string and *return* that string from the
      function.
   e. Create a variable of type string to test your new function.  (See suggestions below)
   f. Use `print(reverse_characters(my_variable_name))` to call the function and verify
      that it correctly reverses the characters in the string.
   g. *Optional*: Use method chaining to reduce the lines of code within the
      function.

{{% notice green Tip %}}

Use these sample strings for testing:

a. `'apple'`
b. `'LC101'`
c. `'Capitalized Letters'`
d. `'I love the smell of code in the morning.'`

{{% /notice %}}

## Reverse Digits

2. The `reverse_characters` function works great on strings, but what if the
   argument passed to the function is a number type? Using
   `print(reverse_characters(1234))` results in an error, since
   `split` only works on strings. When passed a number, we want the
   function to return a number with all the digits reversed (e.g. 1234 converts
   to 4321 and NOT the string `"4321"`).

   a. Add an `if` statement to `reverse_characters` to check the `type` the
      parameter.
   b. If `type` is `str`, return the reversed string as before.
   c. If `type` is `int` or  `float`, convert the parameter to a string, reverse the
      characters, then convert it back into a number.
   d. Return the reversed number.
   e. Be sure to print the result returned by the function to verify that your code
      works for *both strings and numbers*. Do this before moving on to the
      next exercise.

{{% notice green Tip %}}

Use these samples for testing:

a. `1234`
b. `'LC101'`
c. `8675309`
d. `'radar'`

{{% /notice %}}

## Complete Reversal

3. Now we are ready to finish our complete reversal process. Create a new
   function with one parameter, which is the list we want to change. The
   function should:

   a. Define and initialize an empty list.
   b. Loop through the old list.
   c. For each element in the old list, call `reverse_characters` to flip the
      characters or digits.
   d. Add the reversed string (or number) to the list defined in part 'a'.
   e. Return the final, reversed list.
   f. *Be sure to print the results from each test case in order to verify your
      code*.

{{% notice green Tip %}}

Use this sample data for testing.

| Input | Output |
|-------|--------|
| `['apple', 'potato', 'Capitalized Words']` | `['sdroW dezilatipaC', 'otatop', 'elppa']` |
| `[123, 8897, 42, 1138, 8675309]` | `[9035768, 8311, 24, 7988, 321]` |
| `['hello', 'world', 123, 'orange']` | `['egnaro', 321, 'dlrow', 'olleh']` |

{{% /notice %}}

## Bonus Missions

4. Define a function with one parameter, which will be a string. The function
   must do the following:

   a. Have a clear, descriptive name like `fun_phrase`.
   b. Retrieve only the last character from strings with lengths of 3 or less.
   c. Retrieve only the first 3 characters from strings with lengths larger
      than 3.
   d. Use a template literal to return the phrase `We put the '___' in '___'.`
      Fill the first blank with the modified string, and fill the second blank
      with the original string.
   e. `Build your function at repl.it <https://replit.com/@launchcode/FunctionsStudio-Bonus01>`__.

#. Now test your function:

   f. Outside of the function, define the variable `str` and initialize it
      with a string (e.g. `'Functions rock!'`).
   g. Call your function and print the returned phrase.

#. The area of a rectangle is equal to its *length x width*.

   a. Define a function with the required parameters to calculate the area of a
      rectangle.
   b. The function should *return* the area, NOT print it.
   c. Call your area function by passing in two arguments - the length and
      width.
   d. If only one argument is passed to the function, then the shape is a
      square. Modify your code to deal with this case.
   e. Use a template literal to print, "The area is ____ cm^2."
   f. `Code the area function at repl.it <https://replit.com/@launchcode/FunctionsStudio-Bonus02>`__.

{{% notice green Tip %}}

Use these test cases.

a. length = 2, width = 4 (area = 8)
b. length = 14, width = 7 (area = 98)
c. length = 20 (area = 400)

{{% /notice %}}

## Submitting Your Work

You should have **1** repl when finished with the studio. Copy the URL to your repl and paste it into the submission box in Canvas for **Studio: Functions** and click *Submit*.

If you did the bonus missions, submit them through Canvas as well.
