+++
title = "Table Relationships"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 15
+++

Each table should deal with a very narrow set of data, and any specific piece of information should be stored in ONLY ONE PLACE. This
makes it much simpler to perform updates, since changes can be applied once
rather than over multiple tables.

For example, a school might keep track of their course offerings by creating a
`courses` table. This would include information such as an ID number, title,
duration, a short description, and number of credits. All of these items define
a course---Chemistry, for example.

Every course has an assigned teacher as well as a student roster, and these may
also seem like good things to add to the `courses` table. However, a list of
student names does NOT define "Chemistry". Since student placement in a
course is temporary, the roster data needs to be kept in a separate location.
Similarly, multiple teachers could run the same course. Since there could be
two Chemistry classes that take place during 1st period, the names of
specific instructors should be kept out of the `courses` table.

A separate `teachers` table would include information like ID, name, email,
and hire date---everything the school needs to define an instructor. Data such
as courses taught, planning period, or room number would NOT go into this
table, since these items can change every year and are not specific to one
person.

Similarly, a `students` table could contain ID, name, email, courses
completed, parent phone numbers, and grades---anything that defines a
particular child. Something like the name of their first period teacher would
be stored elsewhere.

So, `courses` only holds data that directly defines each class the school
offers. `teachers` only contains information that defines each instructor,
and `students` stores student data and nothing else. This sounds obvious, but
it is very easy to throw lots of data into a table and provide descriptive
column names. While this may seem like a good idea at the time, it leads to
repetition of data, and it makes maintaining that information more difficult.

Any time you add a new column to a table, ask yourself whether the data it
represents *defines* that table. If you answer *No*, then store the data in
a different place (e.g. `lunch_period` does not fit within `students`, so
it will have to go in a different table, such as `schedule`).

## Relating Data

Keeping data in separate, smaller chunks is more efficient than keeping a huge
amount of data in one place. However, this often means we need to access
information stored in different tables. To gather all the data we want, we will
have to combine parts of these tables to get the whole picture.

For our school example, knowing which students are enrolled in which classes is
useful. Similarly, we might want to display a list of students shared by a
group of teachers.

Relational databases allow us to link tables together. Even though teacher
names are not stored in `courses`, a connection can be made between that
table and `teachers`.

Inside `courses`, we can add an `instructor` column. However, this column
will NOT hold any names. Instead, it will store references that point to the
`teachers` table. These references identify the information in `teachers`
that is connected to a particular entry in `courses`.

## One-To-Many Relationships

A common structure for database tables is the **one-to-many relationship**.
In this form, each entry in one table relates to many rows in a different
table. For example, a single row in `courses` represents one class offered by
a school. That single course can be taught by multiple teachers, and lots of
different students will be enrolled in it. Thus, *one* entry in the `courses`
table relates *to many* entries in `teachers` and `students`.

## Table Keys

To connect the `courses` table to `teachers` in a one-to-many relationship,
the following conditions must be met:

1. Each table must include a **primary key** column. A primary key is a unique,
   numerical identifier given to an entry.
1. The `teachers` table must include a **foreign key** column. Foreign keys
   are integers that tie directly to the entries in a different table. In our
   school example, the foreign key for a row in `teachers` matches one
   primary key in `courses`.

Note that different teacher entries could have the same value for the foreign
key. This sets up the one-to-many link between a single row in `courses` and
multiple rows in `teachers`.

A primary key column is oftentimes called `id` whereas the foreign key column will oftentimes be called `tablename_id`. For example, the `teachers` table might have a column called `id` to refer to the primary key and a column called `course_id` to specify it is a foreign key pointing to the primary key of the `courses` table. We cover more on how to implement and create these columns in a later chapter. For now, keep an eye out for these columns in the databases you explore.

## Other Relationships

Besides the common one-to-many structure, there are two other ways to relate
tables to each other. Read the following articles (or do a quick Google search)
to explore these options:

1. [One-to-one](http://www.databaseprimer.com/pages/relationship_1to1/)
1. [Many-to-many](http://www.databaseprimer.com/pages/relationship_xtox/)

You will need this information to answer the last few concept check questions.

## Check Your Understanding

{{% notice green Question %}}

Which if the following is the BEST table to store the period and room number for an Algebra I course?

1. `teachers`
1. `students`
1. `courses`
1. `schedule`

{{% /notice %}}

<!-- d (schedule) -->

{{% notice green Question %}}

Which type of relationship would exist between the `teachers` and `students` tables?

1. One-to-one
1. One-to-many
1. Many-to-many

{{% /notice %}}

<!-- Answer = c (many-to-many) -->
