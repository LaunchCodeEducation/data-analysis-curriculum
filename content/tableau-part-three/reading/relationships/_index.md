+++
title = "Relationships"
date = 2024-05-28T13:45:19-05:00
draft = false
weight = 3
+++

Tableau allows you to create **relationships** between data sources. The relationship itself is based on a column(s) that the two tables you are trying to relate have in common. A relationship must have at least one matching pair of fields in order to be created, meaning they must be of the same data type.

One of the great things about relationships with Tableau is that you do not need to specify the join type for the relationship, Tableau takes care of that query behind the scenes for you.

## Creating a Relationship

In order to create a new relationship you can simply existing data sources onto the canvas and select the appropriate columns to relate.

{{% notice blue Example "rocket" %}}
In the example below, we initially connected to the `cleaning-data-practice` data source which serves as the **root table** for building the relationship. After creating an additional connection to the `transaction-data` data source, dragging it only the canvas alongside `cleaning-data-practice` created a relationship between the two.

![Create a new relationship by dragging an additional table onto the canvas](pictures/create-relationship.png?classes=border)
{{% /notice %}}

{{% notice blue Example "rocket" %}}
Initially, we received an error message notifying us that matching fields need to be selected in order to create the relationship

![Relationship displays as invalid because the fields do not match](pictures/invalid-relationship.png?classes=border)
{{% /notice %}}


{{% notice blue Example "rocket" %}}
Selecting the `transaction_total` from each table cleared the error message allowing us to establish the relationship using the matching fields of data.

![Update the relationship so that the transaction total column is selected from each table](pictures/valid-relationship.png?classes=border)
{{% /notice %}}

{{% notice blue Example "rocket" %}}
As mentioned above, you can add as many fields as you would like to the relationship as long as you have fields that allow for it.

![Adding a secondary matching field to the relationship between the cleaning-data-practice and transaction-data tables](pictures/add-more-fields.png?classes=border)
{{% /notice %}}

Once the relationship is established, fields from both tables will be available when creating a new worksheet. Tableau will automatically use the relationship to combine and display the data correctly.