+++
title = "Comments"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 3
+++

As programs get bigger and more complicated, they get more difficult to read.
Good programmers try to make their code understandable to others, but it is
still tricky to look at a large program and figure out what it is doing and
why.

Best practice encourages us to add notes to our programs, which clearly
explain what the program is doing. These notes are called *comments*.

A **comment** is text within a program intended only for a human reader---it is
completely ignored by the compiler or interpreter. In Python, the `#`
token starts a comment, and the rest of the line gets ignored. For comments
that stretch over multiple lines, each line must begin with a `#`.

{{% notice blue Example "rocket" %}}
```python
# This Example shows off comments!

# print("This does not print.")

print("Hello, World!") # Comments do not have to start at the beginning of a line.

# Here is how
# to have
# multi-line
# comments.

print("Comments make your code more readable by others.")
```
{{% /notice %}}

## Experiment with Comments

{{% notice blue Note "rocket" %}}
In order to launch Visual Studio Code from the command line as referenced in the section below you will need to install the `code` command in your PATH. The following articles will help you navigate this process:

Launching Visual Studio Code from your terminal with the command `code .` will open Visual Studio Code with all files and directories at your current(relative) location.

You may also find the following [Tips and Tricks section](https://code.visualstudio.com/docs/getstarted/tips-and-tricks) useful.
{{% /notice %}}

1. On your own computer, in `data-analysis-projects`, locate the `how-to-write-code` folder. Within that folder, you will find an example called `Comments.py`. You should use the terminal to do so. Here are the steps:
    1. To navigate inside the `how-to-write-code` folder, use the command `cd data-analysis-projects/how-to-write-code`.
    1. Open up the required example in Visual Studio Code by running the command, `code Comments.py`.

2. You are ready to add and remove comments! Here is what the starter code looks like:

    ```python
    # This demo shows off comments!

    # print("This does not print.");

    print("Hello, World!"); # Comments do not have to start at the beginning of a line.

    # Here is how
    # to have
    # multi-line
    # comments.

    print("Comments make your code more readable by others.");
    ```

3. Try removing or un-commenting some code first. Then try adding both a single-line and multi-line comment.

{{% notice blue Note "rocket" %}}
When the above program is run, it still prints the phrase `Hello, World!`, but none of the comments appear. Blank lines left in the code are also ignored by the compiler. Comments and blank lines make your programs much easier for humans to understand. Use them frequently!
{{% /notice %}}