+++
title = "String Functions"
date = 2024-03-26T11:48:30-05:00
draft = false
weight = 1
+++

Similar to pandas, SQL comes with many built-in functions to read, write, update, and in general manipulate data in any way you see fit. The examples below utilize the `SELECT` statement to work with strings so that we can first practice using these functions by only reading the data. A major benefit of this is it allows you to gain a visual of what would happen should you decide to manipulate the same data.

## String Functions

Below you will find some of the more common SQL string functions used and those that we will focus on in this class. You can find a more exhaustive list of string functions here: [SQL String Functions](https://learn.microsoft.com/en-us/sql/t-sql/functions/string-functions-transact-sql?view=sql-server-ver15).

### RTRIM

`RTRIM` removes whitespaces from the right of the last character.

{{% notice blue Example "rocket" %}}
```SQL
SELECT RTRIM('Too many trailing spaces.     ');
```

**Value Returned**

```console
Too many extra spaces.
```
{{% /notice %}}

### LTRIM

`LTRIM` removes whitespaces from the left of the first character.

{{% notice blue Example "rocket" %}}
```SQL
SELECT LTRIM('         Leading spaces');
```

**Value Returned**

```console
Leading spaces
```
{{% /notice %}}

### LEFT

`LEFT` returns the length of characters starting at the provided character index and moving left.

{{% notice blue Example "rocket" %}}
```SQL
SELECT LEFT('hello there!', 7);
```

**Value Returned**

```console
hello t
```
{{% /notice %}}

### RIGHT

`RIGHT` returns the length of characters starting at the provided character index and moving right.

{{% notice blue Example "rocket" %}}
```SQL
SELECT RIGHT('hello there!', 3);
```

**Value Returned**

```console
re!
```
{{% /notice %}}

### LEN

`LEN` returns the length of a string based on characters, not including trailing spaces.

{{% notice blue Example "rocket" %}}
```SQL
SELECT LEN('hello there!'');
```

**Value Returned**

```console
12
```
{{% /notice %}}

### DATALENGTH

`DATALENGTH` returns the length of a string based on bytes, not including trailing spaces.

{{% notice blue Example "rocket" %}}
```SQL
SELECT DATALENGTH('hello there!'');
```

**Value Returned**

```console
12
```
{{% /notice %}}

### CHARINDEX

`CHARINDEX` can use to find a specific character within a string and returns it's index location.

{{% notice blue Example "rocket" %}}
```SQL
SELECT CHARINDEX('log', 'catalogue');
```

**Value Returned**

```console
5
```
{{% /notice %}}

### SUBSTRING

`SUBSTRING` returns part of a string. The first number is the starting index location and the second number is the ending index location.

{{% notice blue Example "rocket" %}}
```SQL
SELECT SUBSTRING('Strings are fun!', 4, 9);
```

**Value Returned**

```console
ings are
```
{{% /notice %}}

### REVERSE

`REVERSE` returns the provided string backwards.

{{% notice blue Example "rocket" %}}
```SQL
SELECT REVERSE('Data Analysis');
```

**Values Returned**

```console
sisylanA ataD
```
{{% /notice %}}

### UPPER

`UPPER` returns a string in all upper case letters.

{{% notice blue Example "rocket" %}}
```SQL
SELECT UPPER('taco');
```

**Value Returned**

```console
TACO
```
{{% /notice %}}

### LOWER

`LOWER` returns a string in all lower case letters.

{{% notice blue Example "rocket" %}}
```SQL
SELECT LOWER('tACO');
```

**Value Returned**

```console
taco
```
{{% /notice %}}

### REPLACE

`REPLACE` replaces part of a string using the provided patterns.

{{% notice blue Example "rocket" %}}
```SQL
SELECT REPLACE('Beach Streat', 'ea', 'ee');
```

**Value Returned**

```console
Beech Street
```
{{% /notice %}}

### CONCAT

`CONCAT` is commonly used to combines strings together and work with `null` values.

{{% notice blue Examples "rocket" %}}
```SQL
SELECT CONCAT('Alyce','Cat', 'Frey');
```

```SQL
SELECT CONCAT('Alyce', NULL, 'Frey');
```

**Values Returned**

```SQL
-- Example 1 output:
AlyceCatFrey

-- Null example output:
AlyceFrey
```
{{% /notice %}}

### CONCAT_WS

`CONCAT_WS` allows you to combine strings together with a specified separator value. The separator can be anything you want.

{{% notice blue Examples "rocket" %}}
```SQL
SELECT CONCAT_WS(' =::= ',  'Alyce', 'Frey');
```

Works with `NULL` values similar to `CONCAT`.

```SQL
SELECT CONCAT_WS('  -  ',  'Alyce', NULL, 'Frey');
```

**Values Returned**

```SQL
-- Example 1 output:
Alyce=::=Frey
-- Null example output:
Alyce - Frey
```
{{% /notice %}}

### STUFF

`STUFF` inserts a string into another string. The first number indicates where to insert the new characters.

{{% notice blue Examples "rocket" %}}
```SQL
SELECT STUFF('Pumpkin Pie', 3, 0, 'Add Chars');
```

The second number indicates how many original characters will be deleted upon insertion.

```SQL
SELECT STUFF('Pumpkin Pie', 3, 5, 'Delete Chars');
```

**Values Returned**

```SQL
-- Example 1 Output:
PuAdd Charsmpkin Pie
-- Example 2 Output:
PuDelete Chars Pie
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Alyce is working with a dataset that contains information about local businesses.  They  want to create a query that returns titles of local businesses that contain "&".  Which string function should they use?

1. `LEN`
1. `STUFF`
1. `CHARINDEX`
1. `RTRIM`
{{% /notice %}}

{{% notice green Question "rocket" %}}
Alyce wants to create consistency in the formatting of the state abbreviations of the local business addresses contained in their dataset.  What string function could help with this?

1. `REVERSE`
1. `UPPER`
1. `CONCAT`
1. `LEFT`
{{% /notice %}}

{{% notice green Question "rocket" %}}
Alyce's dataset breaks down the addresses of local businesses into the following columns: `"Street"`, `"City"`, `"State"`, and ``"Zipcode"``.  They would like to create a column that has all items joined to return a complete address in a single column.   Which function would best help with this?

1. `CONCAT` or `CONCAT_WS` or `STUFF`
1. `LOWER`
1. `REPLACE`
1. `LEFT`
{{% /notice %}}

{{% notice green Question "rocket" %}}
Alyce is working with a column of phone numbers.  They only need the 7 digit number, not the area code.  However, some of the numbers include the area code, some include the country code and area code, and some only include the seven-digit phone number.  Which function could help them select the 7 digits that she needs?

1. `CONCAT_WS`
1. `CHARINDEX`
1. `RIGHT`
1. `RTRIM`
{{% /notice %}}