+++
chapter = false
title = "find and index examples"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 2
+++

## ``find`` and ``index`` Examples

The general syntax for these methods is:

```python
string_name.find(a_string)
string_name.index(a_string)
```

`a_string` is called a **substring**, which means that it will match a
smaller part of `string_name`.

Given the value `a_string`, both `find()` and `index()` return the
integer index for the *first* occurrence of `a_string` in `string_name`.

The difference between the two methods appears when `a_string` is NOT found
in `string_name`.

1. `find()` returns a value of `-1`.
1. `index()` throws and error, and the program stops running.

{{% notice blue Examples "rocket" %}}
```python
text = "Rainbow Unicorns"
pets = "dogs and dogs and dogs!"

print(text.find('i'))
print(pets.index('dog'))

print(text.find('Q'))
print(pets.index('cats'))
```

**Console Output**

```console
2
0
-1
ValueError, line 8: substring not found
```
{{% /notice %}}
   
{{% notice blue Example "rocket" %}}
An email address must contain an `@` symbol. Checking for this symbol is a
part of email verification in most programs.

```python
user_input = "fake.email@launchcode.org"
at_index = user_input.find("@")

if at_index > -1:
   print("Email contains @")
else:
   print("Invalid email")
```

**Console Output**

```console
Email contains @   
```
{{% /notice %}}