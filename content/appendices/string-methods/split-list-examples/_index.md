+++
chapter = false
title = "split Examples"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 5
+++

.. _string-split-examples:

.. index::
   single: string; split

``split`` Examples
==================

The general syntax for this method is:

.. sourcecode:: python

   string_name.split('delimiter')

.. index:: ! delimiter

``split`` divides a string into smaller pieces, which are stored in a collection
called a *list*. The **delimiter** is a string, and it determines how
``string_name`` gets broken apart.

Including a value for ``delimiter`` is optional. By default, Python splits a
string at each space.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      vocab = "conditional;loop;string;int;bool;float"
      word = "Bananas"
      phrase = "Bookkeeper of balloons."

      print(phrase.split())      # Split the string at each space (default).

      print(vocab.split(';'))    # Split the string at each ';' character.

      print(word.split('nana'))  # Split the string at each 'nana' substring.

   **Console Output**

   ::

      ['Bookkeeper', 'of', 'balloons.']
      ['conditional', 'loop', 'string', 'int', 'bool', 'float']
      ['Ba', 's']

Notice that in each case, the ``delimiter`` string is NOT included in the
resulting list.

.. index::
   single: string; list

.. _list-function:

``list`` Function
-----------------

Sometimes we might want to split a string into a list of individual characters.
To make this happen, we need to use the ``list()`` function instead of the
``split`` method.

The general syntax is:

.. sourcecode:: python

   list(string_name)

.. admonition:: Note

   Did you spot the difference in syntax? *Methods* are called using dot
   notation (``string_name.method_name()``), while ``list`` is called by
   placing ``string_name`` inside the ``()``.

   ``list`` is a *function* and NOT a string method. This means we can call
   ``list`` on objects besides strings. Methods like ``split`` can only be
   called on a specific data type: strings.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      word = "Bananas"
      phrase = "Bookkeeper of balloons."

      print(list(word))      # Split the string into individual characters.

      print(list(phrase))

   **Console Output**

   ::

      ['B', 'a', 'n', 'a', 'n', 'a', 's']
      ['B', 'o', 'o', 'k', 'k', 'e', 'e', 'p', 'e', 'r', ' ', 'o', 'f', ' ', 'b', 'a', 'l', 'l', 'o', 'o', 'n', 's', '.']

Note that the resulting lists show all of the characters from the strings,
including spaces.
