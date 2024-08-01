+++
chapter = false
title = "replace Examples"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 4
+++

.. _string-replace-examples:

.. index::
   single: string; replace

``replace`` Examples
====================

The general syntax for this method is:

.. sourcecode:: python

   string_name.replace(a_string, replacement)

This method returns a copy of ``string_name`` with every occurrence of
``a_string`` replaced by the ``replacement`` string. If ``a_string`` is NOT
found in ``string_name``, then the original string gets returned.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      pets = 'Dogs and dogs and dogs!'
         
      print('Replace the spaces'.replace(' ', '-'))
      print(pets.replace('dog', 'cat'))
      print(pets.replace('zebra', 'anaconda'))

   **Console Output**

   ::

      Replace-the-spaces
      Dogs and cats and cats!
      Dogs and dogs and dogs!

.. admonition:: Note

   The ``replace`` method is case-sensitive. This is why ``Dog`` did not
   change to ``cat`` when line 4 printed to the console.

Replace Less Than All
---------------------

By default, the method replaces ALL occurrences of ``a_string`` with the
``replacement`` string. By adding a third parameter, we can tell Python how
many replacements to make. The syntax is:

.. sourcecode:: python

   string_name.replace(a_string, replacement, num_to_replace) 

``num_to_replace`` must be an integer.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      produce = 'Bananas and rutabagas'
         
      print(produce.replace('a', 'u'))       # Replaces all 'a' characters with 'u'.
      print(produce.replace('a', 'u', 2))    # Replaces the first 2 'a' characters with 'u'.

   **Console Output**

   ::

      Bununus und rutubugus
      Bununas and rutabagas
