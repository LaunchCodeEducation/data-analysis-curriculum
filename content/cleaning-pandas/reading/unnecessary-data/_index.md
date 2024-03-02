+++
title = "Handling Unnecessary Data"
draft = false
weight = 4
+++

Unnecessary data is data that is not vital to your analysis. 

```console
   Seller_Id  Seller                Owner_Name     Sales     Total_Rating     Current_Items
0  8967       Orchid Jewels         Orchid Smith   17,896    4.5              22
1  908764     Ducky Ducks           Nala Blake     5,478     3.8              10
2  7463529    Candy Yarns           Candy Elsbeth  89,974    4.8              18
3  161729     Parks Pins            Jade Slate     6,897     4.9              87
4  4217       Sierra's Stationary   Sierra Tomlin  112,988   4.3              347     
5  21378      Star Stitchery        Sara George    53,483    4.2              52 
```

The `Seller_Id` column is a unique identifier given to each seller by Etsy's system and now we have the `Owner_Name` as well. While we want to understand these sellers' sales number, we don't really need their name. 

```python
etsy_sellers.drop(columns=['Owner_Name'])
```

`drop()` defaults to dropping rows so if we want to drop a column we have to pass the column name to `columns`.