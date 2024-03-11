+++
title = "Studio: Strings and Lists"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 3
+++

Strings are **ordered collections** of *characters*, which are strings of
length 1. The characters in a string can be accessed using
**bracket notation**.

Lists are ordered collections of items, which can be strings, numbers,
other lists, etc. The items/elements/entries stored in an list can be
accessed using bracket notation.

Strings are **immutable**, whereas lists can be changed.

Strings and lists have **properties** and **methods** that allow us to easily
perform some useful actions.

{{% notice blue Note "rocket" %}}
The following studio starter code for each part can be found in your `data-analysis-projects/collections/studio` directory.
{{% /notice %}}

## Part 1: String Modification

Use string methods to convert a word into pseudo-pig latin.

1. Remove the first three characters from a string and add them to the end. Ex: `'LaunchCode'` becomes `'nchCodeLau'`. Use a template literal to print the original and modified string in a descriptive phrase.
1. Modify your code to accept user input. Query the user to enter the number of letters that will be relocated.
1. Add validation to your code to deal with user inputs that are longer than the word. In such cases, default to moving 3 characters. Also, the template literal should note the error.

## Part 2: List and String Conversion

The `split` and `join` methods convert back and forth between strings
and lists. Use **delimiters** as reference points to split a string into an
list, then modify the list and convert it back to a printable string.

1. For a given string, use the `in` method to check to see if the
words are separated by commas (`,`), semicolons (`;`) or just spaces.
1. If the string uses commas to separate the words, `split` it into an list,
reverse the entries, and then `join` the list into a new comma separated
string. For example, `"up,to,code,fun"` becomes `"fun,code,to,up"`.
1. If the string uses semicolons to separate the words, `split` it into an
list, alphabetize the entries, and then `join` the list into a new
hyphen separated string. For example, `"up;to;code;fun"` becomes
`"code-fun-to-up"`.
1. If the string uses spaces to separate the words, `split` it into an list,
reverse alphabetize the entries, and then `join` the list into a new
space separated string. For example, `"to code up fun"` becomes
`"up to fun code"`.
1. *Consider*: What if the string uses 'comma spaces' (, ) to separate the
list? Modify your code to produce the same result as part "b", making sure
that the extra spaces are NOT part of the final string.

## Part 3: Optional Fun With Multi-dimensional Lists 

Lists can store other lists!

1. The cargo hold in our shuttle contains several smaller storage spaces. Use `split` to convert the following strings into four cabinet lists. Alphabetize the contents of each cabinet.

    - `"water bottles, meal packs, snacks, chocolate"`
    - `"space suits, jet packs, tool belts, thermal detonators"`
    - `"parrots, cats, moose, alien eggs"`
    - `"blankets, pillows, eyepatches, alarm clocks"`

1. Initialize a `cargoHold` list and add the cabinet lists to it. Print
   `cargoHold` to verify its structure.
1. Query the user to select a cabinet (0-3) in the `cargoHold`.
1. Use bracket notation and a template literal to display the contents of the selected cabinet. If the user entered an invalid number, print an error message instead.

{{% notice green Bonus "rocket" %}}
Modify the code to query the user for BOTH a cabinet in `cargoHold` AND a particular item. Use the`includes` method to check if the cabinet contains the selected item, then print ``"Cabinet ____ DOES/DOES NOT contain ____."``
{{% /notice %}}

## Submitting Your Work

Copy the link to your personal `data-analysis-projects/collections/studio` github repository, and paste them into the submission box in Canvas for **Studio: Strings and Lists** and click *Submit*.