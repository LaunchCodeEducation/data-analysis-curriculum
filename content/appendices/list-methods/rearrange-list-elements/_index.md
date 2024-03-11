+++
chapter = false
title = "Rearranging List Elements"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 6
+++

Python provides two list methods to rearrange the order of the elements. Both
methods *mutate* (change) the original list.

## `reverse` Example

The general syntax for this method is:

```python
list_name.reverse()
```

`reverse` flips the order of the elements in a list. No arguments go inside
the `()`.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
words = ['At', 'banana', 'orange', 'apple', 'zoo']

words.reverse()
print(words)
```

**Output**

```console
['zoo', 'apple', 'orange', 'banana', 'At']
```
{{% /notice %}}

## `sort` Examples

The general syntax for this method is:

```python
list_name.sort()
```

`sort` arranges the elements of a list into increasing order (smallest to
largest). However, all elements inside the list MUST be of the same data type.
Numbers sort with other numbers, strings with other strings, booleans with
other booleans, etc.

{{% notice blue Example "rocket" %}}
Numerical sorting:

```python {linenos=table}
numbers = [2, 8, 10, 400, 30, 45.5]
mixed_types = [20, 8, 'm', 'a']

numbers.sort()
print(numbers)

mixed_types.sort()
```

**Console Output**

```console
[2, 8, 10, 30, 45.5, 400]
Line 11:
    mixed_types.sort()
TypeError: '<' not supported between instances of 'str' and 'int'
```
{{% /notice %}}

For strings, `sort` arranges the elements in alphabetical order.

{{% notice blue Example "rocket" %}}
When sorting strings, case matters!

```python {linenos=table}
letters = ['f', 'c', 'B', 'X', 'a']
letters_and_numbers = ['5', '3', 'm', '8', 'T']

letters.sort()
letters_and_numbers.sort()
print(letters)
print(letters_and_numbers)
```

**Console Output**

```console
[ 'B', 'X', 'a', 'c', 'f' ]
['3', '5', '8', 'T', 'm']
```
        
From the alphabet song, we know that `'a'` comes before `'B'` (and
certainly before `'X'`), but Python treats capital and lowercase letters
differently. Capital letters get sorted before lowercase.

Note that *numerical strings* come before all letters.
{{% /notice %}}

## Sorting Numerical Strings

Let's take a look at sorting a list of strings when each element is a string
of digits.

{{% notice blue Example "rocket" %}}
```python {linenos=table}
number_strings = ['2', '8', '10', '400', '30']

number_strings.sort()
print(number_strings)
```

**Console Output**

```console
[ 10, 2, 30, 400, 8 ]
```

Wait... what? How is 8 larger than 400?

Note that even though we use digits, each element is still a *string*.
Just like `'apple'` comes before `'pear'` because `'a'` comes
before `'p'`, the string `'400'` begins with a `'4'`, which comes
before any string starting with an `'8'`. Looking only at the first
digit in each string, we see the expected progression (1, 2, 3, 4, 8).
{{% /notice %}}

### Sort in Descending Order

To sort a list from the largest to smallest value, the general syntax is:

```python
list_name.sort(reverse = True)
```

{{% notice blue Example "rocket" %}}
Sort in descending order:

```python {linenos=table}
numbers = [2, 8, 10, 400, 30, 45.5]
letters = ['f', 'c', 'B', 'X', 'a']

numbers.sort(reverse = True)
letters.sort(reverse = True)
print(numbers)
print(letters)
```

**Console Output**

```console
[400, 45.5, 30, 10, 8, 2]
['f', 'c', 'a', 'X', 'B']
```
{{% /notice %}}