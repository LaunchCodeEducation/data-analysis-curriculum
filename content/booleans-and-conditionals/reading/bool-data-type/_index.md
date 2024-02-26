+++
title = "Data Type for True and False"
draft = false
weight = 2
+++

In order for us to build code that can make decisions, we need to understand
how programming languages represent true and false.

{{% notice blue Example %}}

If we run the following code, we would see in the following output.

```python {linenos=table}
print('dog' == 'cat')
print(3 < 4)
print(3 > 10)
print('dog' != 'cat')
```

**Console Output**

```console
False
True
False
True
```

{{% /notice %}}

In the code above, we make four comparisons and then print the results to the
console. Python evaluates each comparison as being either `True` or
`False`.

1. In line 1, the **equality operator**, `==`, compares the strings `'dog'`
   and `'cat'`. Since these are not the same, the comparison returns the
   value `False`.
1. In line 2, the operator `<` compares the values of 3 and 4. Since 3 is
   indeed less than 4, comparison returns the result `True`.
1. The comparison in line 3 returns `False`, since 3 is not larger than 10.
1. In line 4, the `!=` operator stands for "not equal", so
   `'dog' != 'cat'` returns `True`, while something like `3 != 3` would
   return `False`.

## Identify `True` and `False`

Recall that the `type()` function tells us the data type of what's inside
the `()`.

```python {linenos=table}
print(3 < 4)
print(type(3 < 4))

print('dog' == 'cat')
print(type('dog' == 'cat'))
```

**Console Output**

```console
True
<class 'bool'>
False
<class 'bool'>
```

In the previous chapter, we learned about three data types---`int`,
`float`, and `string`. The first two deal with numbers, while `string`
deals with collections of characters.

We can now add the data type `bool`, which stands for
**boolean value**, to our list.

## Boolean Values

There are only two boolean values---`True` and `False`.

{{% notice blue Note %}}

Capitalization matters! Since Python is case-sensitive, `true` and
`false` are NOT valid boolean values.

{{% /notice %}}


The values `True` and `False` are NOT strings. We can see this by printing
another set of `type()` results:

{{% notice blue Example %}}

   ```python {linenos=table}
   print(type(True))
   print(type("True"))
   print(True == "True")
   ```

   **Console Output**

   ```console
   <class 'bool'>
   <class 'str'>
   False
   ```

{{% /notice %}}

Putting quotes around boolean values (`"True"` and `"False"`) makes them
strings, just like `"1234"` is a string rather than an `int` data type.

Line 3 shows that even though they look similar, `True` and `"True"` are
not the same! `str` and `bool` are different data types.

## Data Type Review

1. The string (`str`) data type represents a collection of characters.
1. The integer (`int`) data type represents a whole number.
1. The float (`float`) data type represents a decimal value.
1. The boolean (`bool`) data type represents `True` or `False`.