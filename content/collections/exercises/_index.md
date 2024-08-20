+++
title = "Exercises: Collections"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

{{% notice blue Note "rocket" %}}
The exercises for this chapter can be found in the `data-analysis-projects/collections/exercises` directory.
{{% /notice %}}


## Part 1: Strings

### Bracket Notation Basics

The following exercises can be found in the `data-analysis-projects/collections/exercises/strings.py` file.

Use bracket notation to:

1. Print a slice of the first 12 characters from `"Strings_are_sequences_of_characters."`
2. Print a slice of the last 12 characters from the same string. You should NOT have to count the index values yourself!
3. Print a slice of the middle 12 characters from the same string.

   {{% expand "Check Your Solution" %}}
   ```python
   # 1
   print(text[:12])
   
   # 2
   print(text[-12:])
   
   # 3
   print(text[12:24])
   ```
   {{% /expand %}}

### Looping Through a String

Use index values to loop *backwards* through a string:

1. First, print one letter per line.
2. Next, instead of one letter per line, use the accumulator pattern to build up and print the reversed string. For example, if given the string `'good'`, your program prints `doog`.
3. Finally, use concatenation to print the combination of the original and reversed string. For example, given the string `'tomato'`, your program prints `tomatootamot`. (If you want to be fancy, include the `|` character to make the output look almost like a mirrored image: `tomato | otamot`). 

   {{% expand "Check Your Solution" %}}
   ```python
   # 1
   max_index = len(word)-1
   for index in range(max_index, -1, -1):
      print(word[index])
   
   # 2
   new_word = ""
   for index in range(max_index, -1, -1):
      new_word += word[index]
   
   print(new_word)
   ```
   {{% /expand %}}

## Part 2: Lists

The following exercises can be found in the `data-analysis-projects/collections/exercises/lists.py` file.

1. Create a list called `adding_practice` with a single entry: `273.15`. Use the `append` method to add the following elements to the list one at a time.
    - 42
    - "hello"

    Print the list after each step to confirm the changes.

   {{% expand "Check Your Solution" %}}
   ```python
   adding_practice.append(42)
   adding_practice.append("hello")
   ```
   {{% /expand %}}

1. Use `concatenation` to add these three items to the list all at once: `[False, -4.6, '87']`.

   {{% expand "Check Your Solution" %}}
   ```python
   adding_practice += [False, -4.6, '87']
   ```
   {{% /expand %}}

1. `append`, `insert`, `pop`, and `remove` are used to add or remove elements from a list. *Bracket notation* can be used to modify any element within a list. Starting with the `cargo_hold` list,

   ```console
   ['oxygen tanks', 'space suits', 'parrot', 'instruction manual', 'meal packs', 'slinky', 'security blanket']
   ```

    write statements to do the following:

    1. Use bracket notation to replace `'slinky'` in the list with `'space tether'`. Print the list to confirm the change.
    1. Remove the last item from the list with `pop`. Print the element removed and the updated list.
    1. Remove the first item from the list with `pop`. Print the element removed and the updated list.
    1. `append` and `insert` require arguments inside the `()`. Add the items `1138` and `'20 meters'` to the the list---the number at the start and the string at the end. Print the updated list to confirm the changes.
    1. `remove` the parrot from the cargo hold, then print the updated list.
    1. Use `format()` to print the final contents of the list and its length. `"The list ___ contains ___ items."`
   
   {{% expand "Check Your Solution" %}}
   ```python {linenos=table}
   # 1

   cargo_hold[5] = 'space tether'
   
   # 4

   cargo_hold.append('20 meters')

   cargo_hold.insert(0, 1138)
   
   # 6

   output = "The list {0} contains {1} items."

   print(output.format(cargo_hold, len(cargo_hold)))
   ```
   {{% /expand %}}

## Part 3: Search a Dictionary

The exercises for this portion can be found in the `data-analysis-projects/collections/exercises/search-a-dictionary.py` file.

The `flavors` dictionary contains entries that pair different ice cream flavors with their cost per scoop. Your job is to do the following:

1. Set a variable called choice to the flavor you want to search for.

   {{% expand "Check Your Solution" %}}
   ```python
   choice = 'vanilla'
   ```
   {{% /expand %}}

1. Use an if statement to check if choice is in the flavors
dictionary.

   {{% expand "Check Your Solution" %}}
   ```python
   if choice in flavors:
   ```
   {{% /expand %}}
   
1. If it is, set another variable called cost to the value
associated with choice.

   {{% expand "Check Your Solution" %}}
   ```python
   cost = flavors[choice]
   ```
   {{% /expand %}}

1. If it isn’t, set cost to 0.

   {{% expand "Check Your Solution" %}}
   ```python
   else:
      cost = 0
   ```
   {{% /expand %}}

1. Print the cost.

   {{% expand "Check Your Solution" %}}
   ```python
   print('The cost of', choice, 'is', cost)
   ```
   {{% /expand %}}


### Search a Dictionary Part 2

1. Initialize two variables: highest_cost to 0 and fanciest to an
empty string.

   {{% expand "Check Your Solution" %}}
   ```python
   highest_cost = 0

   fanciest = ''
   ```
   {{% /expand %}}

1. Loop through the flavors dictionary using a for loop.

   {{% expand "Check Your Solution" %}}
   ```python
   for flavor in flavors:
   ```
   {{% /expand %}}

1. For each flavor, check if its price is higher than highest_cost.

   {{% expand "Check Your Solution" %}}
   ```python
   if flavors[flavor] > highest_cost:
   ```
   {{% /expand %}}

1. If it is, update fanciest to this flavor and highest_cost to its
price.

   {{% expand "Check Your Solution" %}}
   ```python
   fanciest = flavor

   highest_cost = flavors[flavor]
   ```
   {{% /expand %}}

1. After the loop, print the most expensive flavor.

   {{% expand "Check Your Solution" %}}
   ```python
   print('The fanciest flavor is', fanciest, 'and it costs', highest_cost)
   ```
   {{% /expand %}}

## Submitting Your Work

When finished copy the URL to your GitHub repository for the exercises and paste it into the submission box in Canvas for **Exercises: Collections** and click *Submit*.