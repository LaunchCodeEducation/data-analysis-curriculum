+++
title = "Boolean Expressions"
draft = false
weight = 3
+++

A **boolean expression** makes a comparison and returns one of the boolean
values, either `True` or `False`.

To make a decision within our code, a boolean expression is used as the
**condition**. A condition is a comparison that can be called correct
(`True`) or incorrect (`False`).

## Testing for Equality

The equality operator, `==`, compares two values and returns `True` or
`False` depending on whether the values are identical.

{{% notice blue Example %}}

  ```python {linenos=table}
  num = 37
  other_num = 40

  print(5 == 5)
  print('abc' == 'def')
  print(num == other_num - 3)
  ```

   **Console Output**

  ```console
  True
  False
  True
  ```

{{% /notice %}}

In line 4, the two values are equal, so the expression evaluates to `True`.
In line 5, the string `'abc'` is not equal to `'def'`, so we get `False`.
Line 7 compares the result of `other_num - 3` with the value stored in
`num`.

{{% notice green Tip %}}

A common error is using a single equals sign (`=`) instead of a double
equals (`==`) when comparing two values. We call `=` an
assignment operator, but `==` is a comparison operator.

1. To set the value of a variable, use `=` (e.g. `name = 'Mae'`).
1. To compare values, use `==` (e.g. `name == other_name`).

{{% /notice %}}
   
An equality test is symmetric, meaning that we can switch the places of the
two values and get the same result.  If `num == 7` is `True`, then
`7 == num` is also `True`. However, an assignment statement is not
symmetric. `num = 7` works while `7 = num` does not.

## Other Comparisons

The `==` operator is one of seven common **comparison operators**.

{{% notice blue Note %}}

Remember: The values on either side of an operator are called **operands**.

{{% /notice %}}

| Operator | Description | Example Returning `True` | Example Returning `False` |
|----------|-------------|---------------------------|----------------------------|
| Equal (`==`) | Returns `True` if two compared operands are equal, and `False` otherwise. | `7 == 3 + 4` | `7 == 5` |
| Not equal (`!=`) | Returns `True` if two operands are NOT equal, and `False` otherwise. | `7 != 5` | `7 != 7` |
| Greater than (`>`) | Returns `True` if the left-hand operand is greater than the right-hand operand, and `False` otherwise. | `7 > 5` | `7 > 7` |
| Less than (`<`) | Returns `True` if the left-hand operand is less than the right-hand operand, and `False` otherwise. | `5 < 7` | `15 < 15`|
| Greater than or equal (`>=`) | Returns `True` if the left-hand operand is greater than or equal to the right-hand operand, and `False` otherwise. | `7 >= 5` | `5 >= 7` |
| Less than or equal (`<=`) | Returns `True` if the left-hand operand is less than or equal to the right-hand operand, and `False` otherwise. | `5 <= 7` | `7 <= 5` |
| `in` | Returns `True` if the left-hand operand is found inside the right-hand operand, and `False` otherwise. This operator does not work for the `int` or `float` data types. | `'a' in 'Happy'` | `'A' in 'apple'` (case matters) |

## Check Your Understanding

{{% notice green Question %}}

Which of the following are boolean expressions? Select ALL that apply.

1. `3 <= 4`
1. `3 + 4`
1. `"DogCat" == "dog" + "cat"`
1. `"False"`
1. `text = 'Rutabagas!'`

{{% /notice %}}
	
<!-- Answers = 1 and 3. -->