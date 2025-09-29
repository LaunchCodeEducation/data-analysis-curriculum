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

1. Open the Command Palette (`Ctrl+Shift+P` or `Cmd+Shift+P`) and type "MS SQL: Connect".

2. You'll be prompted to create a connection profile:
   - **Server name**: Enter the SQL Server instance details provided by your program manager
   - **Database name**: Leave blank to use the default database for the SQL Server instance. Or, you can enter the specific database name to always connect to that one from this connection.
   - **Authentication Type**: Choose "SQL Login" 
   - **User name**: Enter your provided SQL Server username
   - **Password**: Enter your provided SQL Server password
   - **Save Password**: Choose "Yes", so you don't have to provide your password every time you activate this connection

3. Give your connection profile a name for easy identification.

{{% notice blue Note %}}

The login information for the SQL Server you'll connect to should be provided by your program manager. Save this connection profile so you won't need to re-enter these details each time.

{{% /notice %}}
