+++
title = "Handling Inconsistent Data"
draft = false
weight = 5
+++

Inconsistent data is data that is not properly formatted for the analysis. 

```console
   Seller_Id  Seller               Sales     Total_Rating     Current_Items  Star_Seller
0  8967       Orchid Jewels        17,896    4.5              22             0 
1  908764     Ducky Ducks          5,478     3.8              10             True 
2  7463529    Candy Yarns          89,974    4.8              18             True 
3  161729     Parks Pins           6,897     4.9              87             True
4  4217       Sierra's Stationary  112,988   4.3              347            0
5  21378      Star Stitchery       53,483    4.2              52             0
```

If we take a look at `Star_Seller`, we can see that all the star sellers are labeled with `True` and those who aren't star sellers have `0`. 

We can choose either to convert everything either to booleans or numbers.

Booleans

Change string 0 to False
Convert

Numbers

Change string True to 1
Convert