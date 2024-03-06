+++
title = "Handling Unnecessary Data"
draft = false
weight = 4
+++

Unnecessary data is data that is not vital to your analysis. For example, if you are doing an analysis on tax data, information like a taxpayer's name or street address might not be necessary for your analysis. The taxpayer's name may be helpful in distinguishing one taxpayer from the other, but do you need to distinguish the taxpayer data on an individual basis? The answer is likely not. This means we have some unnecessary data in the dataset that we need to clean.

{{% notice blue Note %}}

You may also clean unnecessary data for cybersecurity reasons. Taxpayers' personal identifying information  or PII is not something that you want to keep in your dataset in case your company gets hacked.

{{% /notice %}}

We have made some updates to `etsy_sellers` so that we can see how to use pandas to remove unnecessary data.

```console
   Seller_Id  Seller                Owner_Name     Sales     Total_Rating     Current_Items
0  8967       Orchid Jewels         Orchid Smith   17,896    4.5              22
1  908764     Ducky Ducks           Nala Blake     5,478     3.8              10
2  7463529    Candy Yarns           Candy Elsbeth  89,974    4.8              18
3  161729     Parks Pins            Jade Slate     6,897     4.9              87
4  4217       Sierra's Stationary   Sierra Tomlin  112,988   4.3              347     
5  21378      Star Stitchery        Sara George    53,483    4.2              52 
```

The `Seller_Id` column is a unique identifier given to each seller by Etsy's system and now we have the `Owner_Name` as well. The seller's id can be used to tie this info back to a specific shop so with that there, we should be asking ourselves if we need the shop name and the owner name. While we want to understand these sellers' sales number, we don't really need the owner name. 

```python
etsy_sellers.drop(columns=['Owner_Name'])
```

`drop()` defaults to dropping rows so if we want to drop a column we have to pass the column name to `columns`. Alternatively, we can use the axis parameter to drop this column:

```python
etsy_sellers.drop(['Owner_Name'], axis=1)
```

With both of these code samples, we need to specify the column name that we want to drop, but some people might prefer one method over the other. Keep an eye out for both ways of dropping a column when reviewing others' code!

If our analysis only focuses on sellers that do not have any items in the fiber arts space, then we might also want to remove Candy Yarns and Star Stitchery. 

```python
etsy_sellers.drop([2,5])
```

Since we know the indices of Candy Yarns and Star Stitchery, we can drop by index with the above syntax. 

## Check Your Understanding

{{% notice green Question %}}

If you are performing an analysis on inflation and grocery prices, do you need the zip code of a grocery store?

{{% /notice %}}