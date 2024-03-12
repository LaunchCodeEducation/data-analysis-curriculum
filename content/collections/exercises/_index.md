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
   Back to the exercises.
   ```
   {{% /expand %}}

## Part 3: Search a Dictionary

The exercises for this portion can be found in the `data-analysis-projects/collections/exercises/search-a-dictionary.py` file.

The `flavors` dictionary contains entries that pair different ice cream
flavors with their cost per scoop. Your job is to do the following:

1. Write a function called `return_cost` that takes a dictionary and flavor choice as parameters.
   
   - The function searches the dictionary for the flavor and returns its cost.
   - If the flavor is not in the dictionary, return a value of `0`.

   {{% expand "Check Your Solution" %}}
   ```python
   def return_cost(menu, item):
       if item in menu:
           return menu[item]
       return 0
   ```
   {{% /expand %}}

1. After coding the `return_cost` function, run the program and examine the output. Make sure your function behaves as expected before moving to the next step. Don't forget to assign different strings to the `choice` variable! 
   
1. Write a function called `fanciest_flavor` that takes a dictionary as a parameter. The function should return the key name for the most expensive choice in the dictionary.

   {{% expand "Check Your Solution" %}}
   ```python
   def fanciest_flavor(menu):
       highest_cost = 0
       fanciest = ''
       for (flavor, price) in menu.items():
           if price > highest_cost:
               fanciest = flavor
               highest_cost = price
       return fanciest
   ```
   {{% /expand %}}

1. Uncomment the 3 indicated lines in `main()`, then run the program several times and examine the output. Change the prices in `flavors` after each run to make sure your function correctly identifies the most expensive ice cream flavor.

## Submitting Your Work

When finished copy the URL to your GitHub repository for the exercises and paste it into the submission box in Canvas for **Exercises: Collections** and click *Submit*.