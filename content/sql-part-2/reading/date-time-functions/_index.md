+++
title = "Date and Time Functions"
date = 2024-03-26T11:48:30-05:00
draft = false
weight = 2
+++

## [Date and Time Data Types and Functions](https://docs.microsoft.com/en-us/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql?view=sql-server-ver15)

| **Function** | **Definition** | **Syntax** | **Value Returned** |
|--------------|-----------------|------------|---------------------|
| [GETDATE](https://docs.microsoft.com/en-us/sql/t-sql/functions/getdate-transact-sql?view=sql-server-ver15) | Returns a timestamp that includes the date and time of the server. | `SELECT GETDATE()` | 2022-01-04 22:12:25.567 |
| [SYSDATETIME](https://docs.microsoft.com/en-us/sql/t-sql/functions/sysdatetime-transact-sql?view=sql-server-ver15) | Returns a timestamp that includes the date and time of the server. `SYSDATETIME` is more precise with the seconds than `GETTIME`. | `SELECT SYSDATETIME()` | 2022-01-04 22:12:25.5675908 |
| [DATEADD](https://docs.microsoft.com/en-us/sql/t-sql/functions/dateadd-transact-sql?view=sql-server-ver15) | Adds a time period to a date. In this example, we are increasing the month value from `02` (February) to `03` (March). | `SELECT DATEADD(month, 1, '20220224');` | 2022-03-24 00:00:00.000 |
| [DATEDIFF](https://docs.microsoft.com/en-us/sql/t-sql/functions/datediff-transact-sql?view=sql-server-ver15) | Calculates and returns the difference of a date part between an end date and a start date. | `SELECT DATEDIFF(day, '2022-11-13', '2022-12-12');` | 29 |
| DATEDIFF | Can also be used to compare months. | `SELECT DATEDIFF(month, '2022-11-13', '2022-12-12');` | 1 |
| DATEDIFF | Can also compare years. | `SELECT DATEDIFF(year, '1984-11-13', '2022-12-12');` | 38 |
| [DATENAME](https://docs.microsoft.com/en-us/sql/t-sql/functions/datename-transact-sql?view=sql-server-ver15) | Returns a string representing the desired date part. This example selects the day. | `SELECT DATENAME(day, '2022-07-25');` | 25 |
| DATENAME | month | `SELECT DATENAME(month, '2022-07-25');` | July |
| DATENAME | year | `SELECT DATENAME(year, '2022-07-25');` | 2022 |
| [DATEPART](https://docs.microsoft.com/en-us/sql/t-sql/functions/datepart-transact-sql?view=sql-server-ver15) | Returns an integer representing the desired date part. This example selects the day. | `SELECT DATEPART(day, '2022-08-21');` | 21 |
| DATEPART | month | `SELECT DATEPART(month, '2022-08-21');` | 08 |
| DATEPART | year | `SELECT DATEPART(year, '2022-08-21');` | 2022 |
| [DAY](https://learn.microsoft.com/en-us/sql/t-sql/functions/day-transact-sql?view=sql-server-ver16) | Select the day | `SELECT DAY('2022-08-21');` | 21 |
| [MONTH](https://learn.microsoft.com/en-us/sql/t-sql/functions/month-transact-sql?view=sql-server-ver16) | Select the month | `SELECT MONTH('2022-08-21');` | 8 |
| [YEAR](https://learn.microsoft.com/en-us/sql/t-sql/functions/year-transact-sql?view=sql-server-ver16) | Select the year | `SELECT YEAR('2022-08-21');` | 2022 |
| [CONVERT](https://docs.microsoft.com/en-us/sql/t-sql/functions/cast-and-convert-transact-sql?view=sql-server-ver15#j-using-convert-with-datetime-data-in-different-formats) | Paired with `GETDATE` to [convert other data types into dates and times](https://learn.microsoft.com/en-us/sql/t-sql/data-types/date-transact-sql?view=sql-server-ver15#converting-date-to-other-date-and-time-types) based on the desired format. | `SELECT CONVERT(varchar, GETDATE());` | Jan  5 2022  7:25PM |
| CONVERT | These examples convert the server date into various formats. The first example is the default format, the second example is format number 7. | `SELECT CONVERT(varchar, GETDATE(), 7);` | Jan 05, 22 |
| [FORMAT](https://docs.microsoft.com/en-us/sql/t-sql/functions/format-transact-sql?view=sql-server-ver15) | Used to set the format or reformat dates. This example is using the following date information: `Jan  5, 2022  7:38PM`. The first example the server date is formatted date, month, year. The time is not requested, so it is not returned. | `SELECT FORMAT(GETDATE(), 'dd/MM/yyyy');` | 05/01/2022 |
| FORMAT | The second example requests only the time in hours and minutes. Note that `MM` is used for months and `mm` is used for minutes. | `SELECT FORMAT(GETDATE(), 'hh:mm');` | 07:38 |

## Check Your Understanding

{{% notice green Question "rocket" %}}
Willow has a column in her table containing dates the library branches opened.  She wants to compare them to today’s date. Which function would allow her to do that?

1. `DATEADD`
1. `MONTH`
1. `CONVERT`
1. `DATEDIFF`
{{% /notice %}}

{{% notice green Question "rocket" %}}
Willow has a table that contains dates library books are checked out.  She uses the following function in her query: `WHERE DATEPART(MONTH, BorrowDate) = 05`.  What will this return?

1. Rows of data where books were borrowed in the month of May 
1. Rows of data where books were borrowed on the 5th day of the month. 
1. Rows of data where books were borrowed in 2005. 
1. Rows of data where the same library user borrowed exactly 5 books. 
{{% /notice %}}

{{% notice green Question "rocket" %}}
Willow wants to have all the dates in her database in the same format of `month-day-year`.  She used the following syntax: `FORMAT(ModifiedDate, 'mm/dd/yyyy')` and received an error message.  Why?
{{% /notice %}}