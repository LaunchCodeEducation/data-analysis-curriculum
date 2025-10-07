+++
title = "Setting Up Visual Studio Code for SQL"
date = 2024-02-12T13:42:28-06:00
draft = false
weight = 6
hidden = false
+++

Visual Studio Code with SQL extensions provides a powerful environment for working with Microsoft SQL Server databases. This setup allows us to connect to SQL Server instances, write queries, and work with SQL Server directly in VS Code.

## Installing the SQL Server Extension

1. First, ensure you have [Visual Studio Code installed]({{% relref "../install-visual-studio/" %}}).

2. Open Visual Studio Code and go to the Extensions view by clicking the Extensions icon in the Activity Bar or pressing `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (Mac).

3. Search for "SQL Server (mssql)" and install the official Microsoft extension.

## Connecting to SQL Server

1. In order to connect to the server using the following instructions, you need to be in an open SQL file. 
   - Create a new file by going to File -> New File and entering a name for the file. It can be named anything, as long as it ends in the ".sql" file extension. (e.g., "new-file.sql").

2. With this new file open, open the Command Palette (`Ctrl+Shift+P` or `Cmd+Shift+P`) and type "MS SQL: Connect", then select "+ Create a Connection Profile"

3. You'll be prompted to create a connection profile:
   - **Profile Name:**: Give this profile a helpful name so you can remember what you're connecting to
   - **Connection Group**: Leave set to "<Default>"
   - **Server name**: Enter the SQL Server instance details provided in Canvas under "Lesson: SQL Part 1"
   - **Trust Server Certificate**: Check this box
   - **Authentication Type**: Choose "SQL Login" 
   - **User name**: Enter your provided SQL Server username
   - **Password**: Enter your provided SQL Server password
   - **Save Password**: Check this box, so you don't have to provide your password every time you activate this connection
   - **Database name**: Leave blank to use the default database for the SQL Server instance.

4. Once the connection profile is created, you can feel free to delete the file you created in step one. 

{{% notice blue Note %}}

The login information for the SQL Server you'll connect to should be provided by your program manager. Save this connection profile so you won't need to re-enter these details each time.

{{% /notice %}}
