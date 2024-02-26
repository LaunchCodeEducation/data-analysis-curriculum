+++
title = "Decision Making"
draft = false
weight = 1
+++

One of the key features of any programming language is the ability to decide
whether to run a segment of code. This means you can execute a set of
statements *only if* a given condition is met.

{{% notice blue Example %}}

Consider an application that reminds you when you have an overdue book. The
app sends you a message *only if* the due date has passed and you have not
returned the book.

{{% /notice %}}

The *condition* in the example above depends on the status of the book. If the
condition is true (the book is overdue), a message gets sent. If the condition
is false, then the app does not pester you.

In general, we set up decision making in Python by using the following
structure:

```python {linenos=table}
if condition_is_true:
   # Run this code
else:
   # Run this other code
```

We will dive into the details soon, but first we need to understand how Python
determines if a condition is true or false.