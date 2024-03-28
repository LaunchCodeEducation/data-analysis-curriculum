+++
title = "Aggregation Functions"
date = 2024-03-26T11:48:30-05:00
draft = false
weight = 3
+++

SQL Part 2 - Aggregation Functions and Miscellany
=================================================

Use the examples and links in the following tables to get familiar with the various SQL functions.

`Aggregation Functions <https://docs.microsoft.com/en-us/sql/t-sql/functions/aggregate-functions-transact-sql?view=sql-server-ver15>`__
---------------------------------------------------------------------------------------------------------------------------------------

| The following examples are using the BooksDB.  

.. list-table::
   :align: left
   :header-rows: 1
   :widths: 15 30 35 20
   
   * - **Function**
     - **Definition**
     - **Syntax**
     - **Value Returned**
   * - `SUM <https://docs.microsoft.com/en-us/sql/t-sql/functions/sum-transact-sql?view=sql-server-ver15>`__.
     - Returns sum of all values or DISTINCT values.
     - ``SELECT SUM(ratings_2) FROM BooksDB.dbo.books;``
     - 31108850
   * - `MAX <https://docs.microsoft.com/en-us/sql/t-sql/functions/max-transact-sql?view=sql-server-ver15>`__.
     - Returns the highest value.
     - ``SELECT MAX(ratings_2) FROM BooksDB.dbo.books;``
     - 436802
   * - `MIN <https://docs.microsoft.com/en-us/sql/t-sql/functions/min-transact-sql?view=sql-server-ver15>`__.
     - Returns the lowest value.
     - ``SELECT MIN(ratings_2) FROM BooksDB.dbo.books;``
     - 30


``NULL`` Functions 
------------------

``IS NULL``
^^^^^^^^^^^

.. list-table::
   :align: left
   :header-rows: 1
   :widths: 15 30 35 20

   * - **Function**
     - **Definition**
     - **Syntax**
     - **Value Returned**
   * - `IS NULL <https://docs.microsoft.com/en-us/sql/t-sql/queries/is-null-transact-sql?view=sql-server-ver15>`__.
     - Determines whether value is null, often used as a condition with ``WHERE``.
     - See examples below.
     - 


**Example 1**

.. sourcecode:: SQL
   :linenos:

    SELECT  TOP 5 title, isbn, original_publication_year
    FROM BooksDB.dbo.books
    WHERE isbn IS NULL AND original_publication_year IS NULL;

**Value Returned**
(3 rows affected)

.. list-table::
   :align: left
   :widths: 5 40 15 40

   * -    
     - *title*
     - *isbn*
     - *original_publication_year*
   * - 1
     - BookRags Summary:  A Storm of Swords
     - *NULL*
     - *NULL*
   * - 2
     - A Shade of Blood (A Shade of Vampire, #2)
     - *NULL*
     - *NULL*
   * - 3
     - زغازيغ 
     - *NULL*
     - *NULL*

.. admonition:: Note

  In example 1, we asked for the ``TOP`` 5 rows, but only 3 qualified and were returned.

| **Example 2**

.. sourcecode:: SQL
   :linenos:
   
    SELECT title, original_title
    FROM BooksDB.dbo.books
    WHERE authors LIKE 'Sophocles%' AND original_title IS NULL;

| **Value Returned**

.. list-table::
   :align: left
   :widths: 5 65 30

   * -    
     - *title*
     - *original_title*
   * - 1
     - The Oedipus Cycle: Oedipus Rex/Oedipus at Colonus/Antigone (The Theban Plays, #1-3)NULL
     - *NULL*


``IS NOT NULL``
^^^^^^^^^^^^^^^

.. list-table::
   :align: left
   :widths: 15 30 35 20
   
   * - **Function**
     - **Definition**
     - **Syntax**
     - 
   * - `IS NOT NULL <https://docs.microsoft.com/en-us/sql/t-sql/queries/is-null-transact-sql?view=sql-server-ver15>`__.
     - Determines whether value is not null, often used as a condition with ``WHERE``.
     - See examples below.
     -  

| **Example 1**

.. sourcecode:: SQL
   :linenos:

    SELECT  TOP 5 title, isbn, original_publication_year
    FROM BooksDB.dbo.books
    WHERE isbn IS NOT NULL AND original_publication_year IS NOT NULL;

| **Value Returned**

| (5 rows affected)

.. list-table::
   :align: left
   :widths: 5 55 20 20

   * -    
     - *title*
     - *isbn*
     - *original_publication_year*
   * - 1
     - The Hunger Games (The Hunger Games, #1)
     - 439023483
     - 2008
   * - 2
     - Harry Potter and the Sorcerer's Stone (Harry Potter, #1)
     - 439554934
     - 1997
   * - 3
     - Twilight (Twilight, #1)
     - 316015849
     - 2005
   * - 4
     - To Kill a Mockingbird
     - 61120081
     - 1960
   * - 5
     - The Great Gatsby
     - 743273567
     - 1925

| **Example 2**

.. sourcecode:: SQL
   :linenos:
   
    SELECT title, original_title
    FROM BooksDB.dbo.books
    WHERE authors LIKE 'Sophocles%' AND original_title IS NOT NULL;

| **Value Returned**

.. list-table::
   :align: left
   :widths: 5 50 45

   * -    
     - *title*
     - *original_title*
   * - 1
     - Oedipus Rex  (The Theban Plays, #1)
     - Οἰδίπους Τύραννος
   * - 2
     - Antigone (The Theban Plays, #3)
     - Ἀντιγόνη


``ISNULL`` 
^^^^^^^^^^

.. list-table::
   :align: left
   :widths: 15 30 35 20
   
   * - **Function**
     - **Definition**
     - **Syntax**
     - 
   * - `ISNULL <https://docs.microsoft.com/en-us/sql/t-sql/functions/isnull-transact-sql?view=sql-server-ver15>`__.
     - Replaces a specific null value.
     - See example below.
     - 

.. admonition:: Note

   Note the use of an alias in the example below.
   
.. sourcecode:: SQL
   :linenos:

    SELECT original_title, ISNULL(original_title, title) AS UpdatedOriginalTitle
    FROM BooksDB.dbo.books
    WHERE authors LIKE 'Sophocles%';

| **Value Returned**

.. list-table::
   :align: left
   :widths: 5 30 65

   * -    
     - *original_title*
     - *UpdatedOriginalTitle*
   * - 1
     - Οἰδίπους Τύραννος
     - Οἰδίπους Τύραννος
   * - 2
     - Ἀντιγόνη
     - Ἀντιγόνη
   * - 3
     - NULL
     - The Oedipus Cycle: Oedipus Rex/Oedipus at Colonus/Antigone (The Theban Plays, #1-3)



``COALESCE``
^^^^^^^^^^^^

.. list-table::
   :align: left
   :widths: 15 30 35 20

   * - **Function**
     - **Definition**
     - **Syntax**
     - 
   * - `COALESCE <https://docs.microsoft.com/en-us/sql/t-sql/language-elements/coalesce-transact-sql?view=sql-server-ver15>`__.
     - Returns the first value that is not null. Can also be used to test multiple expressions unlike ``ISNULL``. Can be used to address null values when paired with string concatenation.
     - See examples below.
     - 

| **Example 1: Demonstrates returning the first non-null value.**

.. sourcecode:: SQL
   :linenos:
   
    SELECT COALESCE(NULL, 'cat', 'bird');
    SELECT COALESCE('cat', NULL, 'bird');

| **Value Returned**

.. list-table:: 
   :align: left
   
   * - *cat*
   * - *cat*

| **Example 2: Demonstrates using paring ``COALESCE`` with concatenation.**

.. sourcecode:: SQL
   :linenos:

    SELECT COALESCE(original_title, title) + ' by ' + authors AS 'Reading List'
    FROM BooksDB.dbo.books
    WHERE authors LIKE 'Sophocles%';

| **Value Returned**

.. list-table::
   :align: left
   :widths: 5 95

   * -    
     - *Reading List*
   * - 1
     - Οἰδίπους Τύραννος by Sophocles, J.E. Thomas
   * - 2
     - Ἀντιγόνη by Sophocles, J.E. Thomas
   * - 3
     - The Oedipus Cycle: Oedipus Rex/Oedipus at Colonus/Antigone (The Theban Plays, #1–3) by Sophocles, Dudley Fitts, Elena Bono, Robert Fitzgerald



Check Your Understanding
^^^^^^^^^^^^^^^^^^^^^^^^

.. admonition:: Question

   Francis has a database that contains information about car rentals.  She wants to create a query that would return the oldest car the company owns.  Which aggregation method would be a good fit for this query?

   a. ``AVG``
   b. ``MIN``
   c. ``COUNT``
   d. ``MAX``

.. admonition:: Question

   Francis wants to find the car with the highest mileage.  Which aggregation method would be a good option for this query?

   a. ``MAX``
   b. ``AVG``
   c. ``COUNT``
   d. ``MIN``

.. admonition:: Question

   Francis wants to create a column that contains a complete address for each car rental office in her database.  She has a column for street address, suite number, city, state, and zip code.  After some quick EDA, she has discovered that every rental office has a street address, city, state, and zip code.  She also discovered that only about 20% have suite numbers while the remaining 80% are null.  What function would let her still join these elements into addresses without worrying about the null elements affecting the final output?  

   a. ``COALESCE``
   b. ``IS NOT NULL``
   c. ``ISNULL``
   d. ``IS NULL``