+++
title = "Date and Time Functions"
date = 2024-03-26T11:48:30-05:00
draft = false
weight = 2
+++

SQL Part 2 - Date and Time Functions
====================================

`Date and Time Data Types and Functions <https://docs.microsoft.com/en-us/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql?view=sql-server-ver15>`__
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

.. list-table::
   :align: left
   :header-rows: 1
   :widths: 15 30 35 20
   
   * - **Function**
     - **Definition**
     - **Syntax**
     - **Value Returned**
   * - `GETDATE <https://docs.microsoft.com/en-us/sql/t-sql/functions/getdate-transact-sql?view=sql-server-ver15>`__.
     - Returns a timestamp that includes the date and time of the server. 
     - ``SELECT GETDATE()``
     - 2022-01-04 22:12:25.567
   * - `SYSDATETIME <https://docs.microsoft.com/en-us/sql/t-sql/functions/sysdatetime-transact-sql?view=sql-server-ver15>`__.
     - Returns a timestamp that includes the date and time of the server. ``SYSDATETIME`` is more precise with the seconds than ``GETTIME``.
     - ``SELECT SYSDATETIME()``
     - 2022-01-04 22:12:25.5675908
   * - `DATEADD <https://docs.microsoft.com/en-us/sql/t-sql/functions/dateadd-transact-sql?view=sql-server-ver15>`__.
     - Adds a time period to a date. In this example, we are increasing the month value from ``02`` (February) to ``03`` (March).
     - ``SELECT DATEADD(month, 1, '20220224');``
     - 2022-03-24 00:00:00.000
   * - `DATEDIFF <https://docs.microsoft.com/en-us/sql/t-sql/functions/datediff-transact-sql?view=sql-server-ver15>`__.
     - Calculates and returns the difference of a date part between an end date and a start date.
     - ``SELECT DATEDIFF(day, '2022-11-13', '2022-12-12');``
     - 29
   * - 
     - Can also be used to compare months.
     - ``SELECT DATEDIFF(month, '2022-11-13', '2022-12-12');``
     - 1
   * - 
     - Can also compare years.
     - ``SELECT DATEDIFF(year, '1984-11-13', '2022-12-12');``
     - 38
   * - `DATENAME <https://docs.microsoft.com/en-us/sql/t-sql/functions/datename-transact-sql?view=sql-server-ver15>`__.
     - Returns a string representing the desired date part.
     - ``SELECT DATENAME(day, '2022-07-25');``
     - 25
   * - 
     - 
     - ``SELECT DATENAME(month, '2022-07-25');``
     - July
   * -
     - 
     - ``SELECT DATENAME(year, '2022-07-25');``
     - 2022
   * - `DATEPART <https://docs.microsoft.com/en-us/sql/t-sql/functions/datepart-transact-sql?view=sql-server-ver15>`__.
     - Returns an integer representing the desired date part.
     - ``SELECT DATEPART(day, '2022-08-21');``
     - 21
   * -
     - 
     - ``SELECT DATEPART(month, '2022-08-21');``
     - 08
   * -
     -  
     - ``SELECT DATEPART(year, '2022-08-21');``
     - 2022
   * - `DAY, MONTH, YEAR <https://docs.microsoft.com/en-us/sql/t-sql/functions/month-transact-sql?view=sql-server-ver15>`__.
     - Each part of a date.
     - ``SELECT DAY('2022-08-21');``
     - 21
   * -
     - 
     - ``SELECT MONTH('2022-08-21');``
     - 8
   * -
     - 
     - ``SELECT YEAR('2022-08-21');``
     - 2022
   * - `CONVERT <https://docs.microsoft.com/en-us/sql/t-sql/functions/cast-and-convert-transact-sql?view=sql-server-ver15#j-using-convert-with-datetime-data-in-different-formats>`__.
     - Paired with ``GETDATE`` to `convert other data types into dates and times <https://learn.microsoft.com/en-us/sql/t-sql/data-types/date-transact-sql?view=sql-server-ver15#converting-date-to-other-date-and-time-types>`__ based on the desired format.
     - ``SELECT CONVERT(varchar, GETDATE());``
     - Jan  5 2022  7:25PM
   * - 
     - These examples convert the server date into various formats. The first example is the default format, the second example is format number 7. 
     - ``SELECT CONVERT(varchar, GETDATE(), 7);``
     - Jan 05, 22
   * - `FORMAT <https://docs.microsoft.com/en-us/sql/t-sql/functions/format-transact-sql?view=sql-server-ver15>`__.
     - Used to set the format or reformat dates. This example is using the following date information: ``Jan  5, 2022  7:38PM``. The first example the server date is formatted date, month, year. The time is not requested, so it is not returned.
     - ``SELECT FORMAT(GETDATE(), 'dd/MM/yyyy');``
     - 05/01/2022
   * - 
     - The second example requests only the time in hours and minutes. Note that ``MM`` is used for months and ``mm`` is used for minutes.
     - ``SELECT FORMAT(GETDATE(), 'hh:mm');``
     - 07:38

Check Your Understanding
^^^^^^^^^^^^^^^^^^^^^^^^

.. admonition:: Question

   Willow has a column in her table containing dates the library branches opened.  She wants to compare them to today’s date. Which function would allow her to do that?

   a. ``DATEADD``
   b. ``MONTH``
   c. ``CONVERT``
   d. ``DATEDIFF``
   
.. admonition:: Question

   Willow has a table that contains dates library books are checked out.  She uses the following function in her query: ``WHERE DATEPART(MONTH, BorrowDate) = 05``.  What will this return?

   a. Rows of data where books were borrowed in the month of May 
   b. Rows of data where books were borrowed on the 5th day of the month. 
   c. Rows of data where books were borrowed in 2005. 
   d. Rows of data where the same library user borrowed exactly 5 books. 

.. admonition:: Question

   Willow wants to have all the dates in her database in the same format of ``month-day-year``.  She used the following syntax: ``FORMAT(ModifiedDate, 'mm/dd/yyyy')`` and received an error message.  Why?