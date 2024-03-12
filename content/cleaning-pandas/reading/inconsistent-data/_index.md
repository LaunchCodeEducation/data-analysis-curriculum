+++
title = "Handling Inconsistent Data"
draft = false
weight = 5
+++

Our final type of dirty data we want to clean is inconsistent data. Inconsistent data is data that is not properly formatted for the analysis. This could be data that is strings but should be numbers (`'0'` instead of `0` or `'one hundred'` instead of `100`). Let's study `etsy_sellers` for the final time to see how we can detect and handle inconsistent data. 

```console
   Seller_Id  Seller               Sales     Total_Rating     Current_Items  Star_Seller
0  8967       Orchid Jewels        17,896    4.5              22             0 
1  908764     Ducky Ducks          5,478     3.8              10             True 
2  7463529    Candy Yarns          89,974    4.8              18             True 
3  161729     Parks Pins           6,897     4.9              87             True
4  4217       Sierra's Stationary  112,988   4.3              347            0
5  21378      Star Stitchery       53,483    4.2              52             0
```

Star sellers meet Etsy's highest standard of customer service so it makes sense that we would have a column in our dataset to designate whether or not someone is a star seller. If we take a look at the new `Star_Seller` column, we can see that all the star sellers are labeled with `'True'` and those who aren't star sellers have `'0'`. Now we need to resolve this inconsistency in order for us to do an effective analysis with the `Star_Seller` column. We can either convert everything to booleans or to numbers.

## The Numbers Era of Star Sellers

We are going to start by converting everything to numbers. Once everything in the column is converted to numbers, it will be easier for us to convert the column to booleans. The sellers that are not star sellers are designated with a `'0'` so converting that string to a number is going to be a little more straightforward than converting the string `'True'` to `1`.

1. First, let's focus in on turning `'True'` to `'1'`.

   ```python
   etsy_sellers = etsy_sellers.loc[etsy_sellers['Star_Seller'] == 'True'] = '1'
   ```

   This code will replace all the values in the `Star_Seller` column with `'1'` only if that value is currently equal to `'True'`.

1. We can now convert the whole `Star_Seller` column to integers.

   ```python
   etsy_sellers.Star_Seller = etsy_sellers.Star_Seller.astype('int64')
   ```

   `astype()` allows us to convert a dataframe or column of a dataframe to a specific type, in this case, `int64`.

After all of this, our dataframe will look a lot more like this:

```console
   Seller_Id  Seller               Sales     Total_Rating     Current_Items  Star_Seller
0  8967       Orchid Jewels        17,896    4.5              22             0 
1  908764     Ducky Ducks          5,478     3.8              10             1 
2  7463529    Candy Yarns          89,974    4.8              18             1 
3  161729     Parks Pins           6,897     4.9              87             1
4  4217       Sierra's Stationary  112,988   4.3              347            0
5  21378      Star Stitchery       53,483    4.2              52             0
```

## The Booleans Era of Star Sellers

With the whole `Star_Seller` column converted to integers, we just have to do one more step to convert the whole column to booleans.

```python
etsy_sellers.Star_Seller = etsy_sellers.Star_Seller.astype('bool')
```

With this step, `etsy_sellers` is going to become:

```console
   Seller_Id  Seller               Sales     Total_Rating     Current_Items  Star_Seller
0  8967       Orchid Jewels        17,896    4.5              22             False
1  908764     Ducky Ducks          5,478     3.8              10             True 
2  7463529    Candy Yarns          89,974    4.8              18             True 
3  161729     Parks Pins           6,897     4.9              87             True
4  4217       Sierra's Stationary  112,988   4.3              347            False
5  21378      Star Stitchery       53,483    4.2              52             False
```

Whether you convert the column to booleans or stay with integers depends entirely on what you need from your analysis and what you find easier to work with later on. This is the case with a lot of cleaning data. The approach you take to cleaning data is heavily dependent on you and what you are hoping to achieve with your analysis. The key for now is to practice and not be afraid to try something new.