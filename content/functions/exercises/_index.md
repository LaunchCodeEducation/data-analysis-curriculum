+++
title = "Exercises: Functions"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

To solve problems with code, you need to be able to break large
problems into small ones. Usually, these smaller problems will take the form of
functions that are used to solve the larger problem. Therefore, to solve problems with code, 
you need to be skilled at writing functions. And to master
functions, you need to write a *lot* of them.

These exercises ask you to write many relatively small functions, which
combine to form larger, more complicated ones.

At the end, you will be able to create strings of shapes, like this nifty
diamond:

```console
       #
      ###
     #####
    #######
   #########
   #########
    #######
     #####
      ###
       #
```

## Getting Started

You will find the starter code `here <https://replit.com/@launchcode/FunctionsExercises>`_.

## Part 1: Rectangles

1. Write a function `make_line(size)` that returns a line with exactly `size`
   hashes.

   ```python
   print(make_line(5))
   ```

   **Console Output**

   ```console
   #####
   ```

1. Write a function called `make_square(size)` that returns a `size` by
   `size` string of hashes. The function should NOT print each row of the
   square. Instead, it must return a single string that contains the entire
   shape.

   {{% notice green Tip %}}
   
   1. Call your `make_line` function to create each row of the square.
   1. The newline character, `\n`, will be helpful to you.
   1. Do NOT include a newline character at the end of your string.

   {{% /notice %}}

   ```python
   print(make_square(5))
   ```

   **Console Output**

   ```console
   #####
   #####
   #####
   #####
   #####
   ```

   {{% notice orange Warning %}}
   
   For each of the shape exercises, do not include a newline character at
   the very end of your string. While the final `\n` might not be
   noticeable for the simpler shapes, including it will make life harder for
   you toward the end of the exercises.

   {{% /notice %}}

   {{% expand "Check your solution" %}}
   
   {{% /expand %}}

1. Write a function `make_rectangle(width, height)` that returns a
   rectangle with the given width and height. Use your `make_line` function to
   do this.

   ```python
   print(make_rectangle(5, 3))
   ```

   **Console Output**

   ```console
   #####
   #####
   #####
   ```

1. Now, go back and rewrite `make_square` to use `make_rectangle`.

{{% expand "Check your solution" %}}

{{% /expand %}}

## Part 2:  Triangles

1. Write a function `make_downward_stairs(height)` that prints the staircase
   pattern shown below, with the given height. Use your `make_line` function
   to do this.

   ```python
   print(make_downward_stairs(5))
   ```

   **Console Output**

   ```console
   #
   ##
   ###
   ####
   #####
   ```

   {{% expand "Check your solution" %}}
   
   {{% /expand %}}

1. Write a function `make_space_line(numSpaces, numChars)` that returns a line
   with exactly the specified number of spaces, followed by the
   specified number of hashes, followed again by `num_spaces` more spaces.

   ```python
   print(make_space_line(3, 5));
   ```

   **Console Output**

   ```console
   ___#####___
   ```

   {{% notice blue Note %}}
   
   We have inserted underscores to represent spaces, so they are visible in the output. Don't do this in your code.

   {{% /notice %}}
   
   {{% expand "Check your solution" %}}
   
   {{% /expand %}}

1. Write a function `make_isosceles_triangle(height)` that returns a triangle
   of the given height.

   ```python
   print(make_isosceles_triangle(5))
   ```

   **Console Output**

   ```console
          #
         ###
        #####
       #######
      #########
   ```

   {{% notice green Tip %}}
   
   Consider the top line of the triangle to be level 0, the next to be line 1, and so on. Then line `i` is a space-line with `height - i - 1` spaces and `2 * i + 1` hashes.

   {{% /notice %}}

   {{% expand "Check your solution" %}}
   
   {{% /expand %}}

## Part 3: Diamonds

1. Write a function `make_diamond(height)` that returns a diamond where the
   triangle formed by the *top* portion has the given height.

   ```python
   print(make_diamond(5))
   ```

   **Console Output**

   ```console
          #
         ###
        #####
       #######
      #########
      #########
       #######
        #####
         ###
          #
   ```

   {{% expand "Check your solution" %}}
   
   {{% /expand %}}

## Submitting Your Work

When finished copy the URLs to your repls for the exercises, separating each URL with a semi-colon and paste them into the submission box in Canvas for **Exercises: Booleans, Conditionals, and Loops** and click *Submit*.

