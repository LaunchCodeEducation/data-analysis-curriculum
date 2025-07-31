+++
title = "Setting Up Visual Studio Code for SQL"
date = 2024-02-12T13:42:28-06:00
draft = false
weight = 6
hidden = true
+++

Visual Studio Code with SQL extensions provides a powerful environment for working with Microsoft SQL Server databases. This setup allows us to connect to SQL Server instances, write queries, and work with SQL notebooks directly in VS Code.

## Installing the SQL Server Extension

1. First, ensure you have [Visual Studio Code installed]({{% relref "../install-visual-studio/" %}}).

2. Open Visual Studio Code and go to the Extensions view by clicking the Extensions icon in the Activity Bar or pressing `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (Mac).

3. Search for "SQL Server (mssql)" and install the official Microsoft extension.

4. Optionally, you may also want to install the "SQL Notebook" extension for enhanced notebook support.

## Connecting to SQL Server

1. Open the Command Palette (`Ctrl+Shift+P` or `Cmd+Shift+P`) and type "MS SQL: Connect".

2. You'll be prompted to create a connection profile:
   - **Server name**: Enter the SQL Server instance details provided by your program manager
   - **Database name**: Leave blank for default, or enter specific database name
   - **Authentication Type**: Choose "SQL Login" 
   - **User name**: Enter your SQL Server username
   - **Password**: Enter your SQL Server password
   - **Save Password**: Choose "Yes" for convenience

3. Give your connection profile a name for easy identification.

{{% notice blue Note %}}

The login information for the SQL Server you'll connect to should be provided by your program manager. Save this connection profile so you won't need to re-enter these details each time.

{{% /notice %}}

## Working with SQL Notebooks

VS Code supports SQL notebooks (.ipynb files) that allow you to combine SQL queries with markdown documentation:

1. Open your SQL notebook file in VS Code
2. Select your SQL Server connection when prompted
3. You can now run SQL code cells and view results directly in the notebook

The SQL Server extension provides IntelliSense, syntax highlighting, and query execution capabilities that make working with T-SQL efficient and user-friendly.
