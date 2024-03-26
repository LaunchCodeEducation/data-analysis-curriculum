+++
title = "String Functions"
date = 2024-03-26T11:48:30-05:00
draft = false
weight = 1
+++

## String Functions

You can find a more exhaustive list of string functions here: [SQL String Functions](https://learn.microsoft.com/en-us/sql/t-sql/functions/string-functions-transact-sql?view=sql-server-ver15)

### RTRIM

Removes whitespaces from right of last character.

Syntax:

```sql
SELECT RTRIM('Too many trailing spaces.     ');
```

### LTRIM

Removes whitespaces from left of first character.

Syntax:

```sql
SELECT LTRIM('         Leading spaces');
```

### LEFT

Returns length of characters starting at provided character index and moving left.

Syntax:

```sql
SELECT LEFT('hello there!', 7);
```

### RIGHT

Returns length of characters starting at provided character index and moving right.

Syntax:

```sql
SELECT RIGHT('hello there!', 3);
```

### LEN

Returns the length of a string based on characters, not including trailing spaces.

Syntax:

```sql
SELECT LEN('hello there!'');
```

### DATALENGTH

Returns the length of a string based on bytes, not including trailing spaces.

Syntax:

```sql
SELECT DATALENGTH('hello there!'');
```

### CHARINDEX

Can use to find specific character within a string. Returns the index location.

Syntax:

```sql
SELECT CHARINDEX('log', 'catalogue');
```

### SUBSTRING

Returns part of a string. First number is starting index location and second number is ending index location.

Syntax:

```sql
SELECT SUBSTRING('Strings are fun!', 4, 9);
```

### REVERSE

Returns the string backwards.

Syntax:

```sql
SELECT REVERSE('Data Analysis');
```

### UPPER

Returns a string in all upper case.

Syntax:

```sql
SELECT UPPER('taco');
```

### LOWER

Returns a string in all lower case.

Syntax:

```sql
SELECT LOWER('tACO');
```

### REPLACE

Replaces part of a string using provided patterns.

Syntax:

```sql
SELECT REPLACE('Beach Streat', 'ea', 'ee');
```

### CONCAT

Combines strings together.

Syntax:

```sql
SELECT CONCAT('Alyce','Cat', 'Frey');
```

Good for working with null values as seen in example 2.

```sql
SELECT CONCAT('Alyce', NULL, 'Frey');
```

### CONCAT_WS

Combines strings together with a specified separator value. The separator can be anything you want.

Syntax:

```sql
SELECT CONCAT_WS(' =::= ',  'Alyce', 'Frey');
```

Works with `NULL` values similar to `CONCAT`.

```sql
SELECT CONCAT_WS('  -  ',  'Alyce', NULL, 'Frey');
```

### STUFF

Inserts a string into another string. The first number indicates where to insert the new characters.

Syntax:

```sql
SELECT STUFF('Pumpkin Pie', 3, 0, 'Add Chars');
```

The second number indicates how many original characters will be deleted upon insertion.

```sql
SELECT STUFF('Pumpkin Pie', 3, 5, 'Delete Chars');
```

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