+++
title = "A Good Function-Writing Process"
draft = false
weight = 6
+++

Functions are the most powerful Python tool that we have seen so far. They
have more parts to their syntax than either conditionals or loops, and they can
be used in more complex ways.

To avoid frustration and bugs, it's important to write functions in a very
structured way. *Have a plan* before you start coding any function! This is
essential now and once you start writing more complex code.

In this section, we outline what we think is the best approach. To show a
concrete example, we will consider a fictional function that makes a sandwich.

## Step 1: Design Your Function

Before typing anything, have a clear idea of what you want your function to do.
Once you identify that, ask yourself the following questions:

1. What is a good, descriptive name for my function?
1. What data (*parameters*) does my function need to do its job?
1. What data types do we expect the parameters to be?
1. What are good names for the parameters?
1. Should my function return a value? (*Hint*: The answer is almost always
   "YES".)
1. What will be the data type of the return value?

For our sandwich function, the answers might look like this:

* Function name: `make_sandwich`
* Parameters: bread, filling, condiments
* Parameter names and types: `bread_type` (string), `filling_type` (string), `condiment` (string)
* Return Value: The finished sandwich
* Return Type: An object of type `sandwich`
    
Python does not actually have a `sandwich` data type, but we want our
function to be as flexible as possible. For now, recognize that returning a
simple string to describe the sandwich will not be useful.

## Step 2: Create the Basic Structure

Now it is time to start coding. Using the decisions you just made, write the
minimal syntax needed to create and call the function.

Here's an outline for our sandwich function:

```python {linenos=table}
  def make_sandwich(bread_type, filling_type, condiment):

    # TODO: make a sandwich with the given ingredients

    return # TODO: Send back a sandwich object
  
  make_sandwich('this', 'is', 'practice')
```

Doing this step before writing the body makes sure we aren't
leaving off the `:` or forgetting to define a parameter.

Even though the function does not do anything yet, it will still work. Running
the program at this point will NOT generate any error messages unless we have a
syntax error (like forgetting the `:`) or the wrong number of parameters.

## Step 3: Write the Body

With the basic structure in place, start writing the function body. Be sure to
switch between finishing small parts of the function and running your code.
*Do not wait until you have written the entire function body before testing
it!*

We can't stress this enough. Going long stretches of time without running
your program is a good way to end up frustrated!

This applies *especially* to writing functions. Every good programmer works
this way: 

1. Write a few lines of code,
1. Run it,
1. Debug any errors,
1. Repeat.

Following these steps won't prevent you from making mistakes, but it will
reduce the number of bugs you create. This helps you create solid, working code
more quickly.