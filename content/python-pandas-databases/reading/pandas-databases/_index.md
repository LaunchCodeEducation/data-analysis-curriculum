+++
title = "Pandas with Databases"
date = 2024-04-17T10:00:24-05:00
draft = false
weight = 2
+++

In the previous lesson we talked about ease of use when manipulating data stored within a database. Pandas makes working with data much easier than executing numerous queries within the database itself.

<!-- TODO: Reassess this note -->
{{% notice blue Note "rocket" %}}
Just because pandas makes working with data easier for the user than working within the database does not make it the right tool for every job. 

Some developers may prefer to work with a different tool and that is okay!
{{% /notice %}}

This lesson will also utilize SQLite3 as the database used to access and manipulate data. Since we have already covered how to manipulate data with pandas in previous lessons we will instead focus on reading data, and repopulating the database with an updated dataframe.