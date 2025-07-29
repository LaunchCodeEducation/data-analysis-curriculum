+++
title = "Dictionary Basics"
date = 2024-02-20T09:31:05-06:00
draft = false
weight = 1
+++

We learned that both lists and strings are examples of *ordered collections*.
They are built from smaller, individual pieces of data, each of which has its
own index value.

A third type of Python collection is called a **dictionary**.

**Dictionary facts:**

1. Dictionaries are *unordered* collections. They do NOT use index values (0, 1, 2, ...) to organize the data from left to right.
1. Dictionaries are *mutable*. We can add, remove, or modify the data in the collection.
1. Dictionaries store data using sets of **key/value pairs**. Think of a *key* just like a label or a variable name. It *points to* a specific piece of data, called the *value*.
1. Dictionaries store as many key/value pairs as needed, and each value needs a key. Without a key, the value cannot be accessed or modified.
1. The values in a dictionary may be of any data type, including lists and other dictionaries.
1. The keys should be an `int` or `str` data type. In most cases, using strings is the better choice. We will see why soon.

![Each key points to a value inside a dictionary.](pictures/dictionary.png?classes=border)

## Why Use Keys?

Imagine we have a list of phone numbers, and we want to access the one for
"Mom". Nothing in the list lets us know which element is the one we want.
`phone_numbers[0]` gives us the first entry in the list, but it does not tell
us who the number belongs to.

If we remember that Mom's phone number is at index `5`, then
`phone_numbers[5]` will work. However, lists are *mutable*. After a few
updates, her number might not be at position `5` anymore.

It would be nice if we could access a phone number by the *name of who it
belongs to* instead of by index. Maybe something like `phone_numbers['Mom']`
instead of `phone_numbers[5]`. That is why we would use a dictionary for our address book!

*Lists* order data from left to right, which is great. However, the index
values 0, 1, 2... do NOT tell us what the data actually represents. Index `0`
might refer to a string, number, list, etc. We cannot know until we access that
element.

*Dictionaries* organize data by linking concrete values to individual keys. The
order of the key/value pairs in the collection is not important, since we just
need to know the label for the value we want.

{{% notice blue Example "rocket" %}}
Compare the following data structures:

```python {linenos=table}
# A Python list:
phone_numbers = ['555-5555', '555-5556', '123-456-7890']

# A Python dictionary:
phone_book = {
   'Mom' : '555-5555',
   'Work' : '555-5556',
   'Home' : '123-456-7890'
}
```
{{% /notice %}}

By attaching a label to each value in `phone_book`, we make retrieving Mom's
number much easier. Keys give each data value a name.

Let's take a closer look at how to define a Python dictionary.

## Create a New Dictionary

To define a new dictionary, we need three things: a variable, a set of keys,
and their corresponding values. There are several ways to create a new
dictionary, but the simplest is to wrap the key/value pairs in curly braces
`{}`, with each pair separated from the others by commas.

{{% notice blue Example "rocket" %}}
```python
student = {'name' : 'Maria', 'id_number' : 1234, 'scores' : [90, 95, 88]}
```
{{% /notice %}}

**Note the following**:

1. The new dictionary is assigned to the variable ``student``.
1. Inside the curly braces, colons separate the key/value pairs, with the keys on the left and the values on the right.
   - `key : value`

1. In this example, all of the key names are strings---`'name', 'id_number', 'scores'`. The values linked to these keys include a string, an integer, and a list.
1. To help make our code more readable, we can place each key/value pair on its own line.

   ```python {}
   student = {
      'name' : 'Maria',
      'id_number' : 1234,
      'scores' : [90, 95, 88]
   }
   ```

   {{% notice orange Warning "rocket" %}}
   When putting the key/value pairs on separate lines, pay attention to spaces
   and tabs! Incorrect indentation can result in a bug.
   {{% /notice %}}

1. We can also define an empty dictionary using just a pair of braces.

   ```python
   empty_dictionary = {}
   ```

## Accessing Values

With lists and strings, we access elements or characters by using bracket
notation and placing an index value inside the `[]`.

```python
my_list[0]     # Access the first element in my_list.
my_string[3]   # Access the character at index 3 in my_string.
```

To access a specific entry in a dictionary, we still use bracket notation.
However, instead of placing an index inside the brackets, we use a key name
instead.

```python
student['name']     # Access the value linked to the key 'name'.
```

## Key Data Types

We can use either an integer or a string for a key name. However, since we want
the key to describe the data linked to it, the best choice is usually a string.

What if we used integers for the `phone_book` example?

```python {linenos=table}
phone_book = {
   0 : '555-5555',
   1 : '555-5556',
   2 : '123-456-7890'
}
```

This looks a lot like the index values of a list. If we use integers, the keys
do not tell us which number belongs to a specific person or place. Just like
variable names, we want the key names to be as descriptive as possible, and
strings do this best.

{{% notice blue Note "rocket" %}}
Technically, we can use an `int, str, float`, or `bool` data type for a
key name. Strings are still the best choice in most cases, however.

`bool` or `float` for a key?  Don't.  Just... don't.
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
A dictionary is an unordered collection of key/value pairs.

1. True
1. False
<!-- Solution: True -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
In a dictionary, two *keys* may have the same name.

1. True
1. False
<!-- Solution: False -->
{{% /notice %}}