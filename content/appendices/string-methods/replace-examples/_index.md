+++
chapter = false
title = "replace Examples"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 4
+++

## `replace` Examples

The general syntax for this method is:

```python
string_name.replace(a_string, replacement)
```

This method returns a copy of `string_name` with every occurrence of
`a_string` replaced by the `replacement` string. If `a_string` is NOT
found in `string_name`, then the original string gets returned.

{{% notice blue Example "rocket" %}}
```python
pets = 'Dogs and dogs and dogs!'
   
print('Replace the spaces'.replace(' ', '-'))
print(pets.replace('dog', 'cat'))
print(pets.replace('zebra', 'anaconda'))

```

**Console Output**

```console
Replace-the-spaces
Dogs and cats and cats!
Dogs and dogs and dogs!
```
{{% /notice %}}

{{% notice blue Note "rocket" %}}
The `replace` method is case-sensitive. This is why `Dog` did not
change to `cat` when line 4 printed to the console.
{{% /notice %}}

## Replace Less Than All

By default, the method replaces ALL occurrences of `a_string` with the
`replacement` string. By adding a third parameter, we can tell Python how
many replacements to make. The syntax is:

```python
string_name.replace(a_string, replacement, num_to_replace)
```

`num_to_replace` must be an integer.

{{% notice blue Example "rocket" %}}
```python
produce = 'Bananas and rutabagas'
   
print(produce.replace('a', 'u'))       # Replaces all 'a' characters with 'u'.
print(produce.replace('a', 'u', 2))    # Replaces the first 2 'a' characters with 'u'.
```

**Console Output**

```console
Bununus und rutubugus
Bununas and rutabagas
```
{{% /notice %}}