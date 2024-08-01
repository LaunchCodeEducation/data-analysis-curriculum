+++
chapter = false
title = "lower and upper examples"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 3
+++

.. _string-lower-examples:

.. index::
   single: string; lower

``lower`` Examples
==================

The general syntax for this method is:

.. sourcecode:: python

   string_name.lower()

This method returns a copy of ``string_name`` with all uppercase letters
converted to lowercase. It leaves non-alphabetic characters alone.

``string_name`` can be a literal string, like ``'Hello'``, or it can be a
variable that points to a string value.

.. sourcecode:: python
   :linenos:

   print("LaunchCode".lower())

   word = "Some Title With Non-letters!"
   print(word.lower())

**Output**

::

   launchcode
   some title with non-letters!

.. _string-upper-examples:

.. index::
   single: string; upper

``upper`` Examples
==================

The general syntax for this method is:

.. sourcecode:: python

   string_name.upper()

This method returns a copy of ``string_name`` with all lowercase letters
converted to uppercase. It leaves non-alphabetic characters alone.

``string_name`` can be a literal string, like ``'Hello'``, or it can be a
variable that points to a string value.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      email = username@some_site.org

      print("LaunchCode".upper())
      print(email.upper())

   **Output**

   ::

      LAUNCHCODE
      USERNAME@SOME_SITE.ORG
