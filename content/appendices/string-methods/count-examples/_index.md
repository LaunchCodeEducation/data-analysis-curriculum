+++
chapter = false
title = "Count Examples"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 1
+++

.. _string-count-examples:

.. index::
   single: string; count

``count`` Examples
==================

The general syntax for this method is:

.. sourcecode:: python

   string_name.count(search_string)

This method returns the number of times ``search_string`` occurs in
``string_name``.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:
         
      print('bananas'.count('a'))
      print('bananas'.count('B'))
      print('bananas'.count('nana'))

   **Console Output**

   ::

      3
      0
      1

Note that ``count()`` searches for the EXACT string placed in the ``()``. Even
though ``bananas`` contains the letter ``'b'``, since the case does NOT match
in line 2, the expression returns ``0``.

Search Part of a String
-----------------------

The ``count()`` method can also take a starting and ending index value:

.. sourcecode:: python

   string_name.count(search_string, start, end)

Written this way, the method searches ``string_name`` from the ``start`` index
up to but NOT including the ``end`` index.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      produce = 'Bananas and rutabagas!'
      # Note that the first three 'a' characters are at index values 1, 3, and 5.
         
      print(produce.count('a'))
      print(produce.count('a', 1, 5))
      print(produce.count('a', 1, 6))

   **Console Output**

   ::

      7
      2
      3
