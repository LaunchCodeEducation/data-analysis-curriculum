+++
title = "Calculations"
weight = 3
originalAuthorGitHub = "gildedgardenia"
+++


Right now, we have a lot of information stored in our spreadsheet, but we haven't fully unlocked all that we can do with spreadsheets. One feature that many data analysts make use of is formulas. Formulas in spreadsheets enable us to run a mathematical calculation using the value of a cell. We can sum multiple cells together or multiple a cell's value by 3. 

To write a formula, we can start by typing a `=` in the cell. This tells Google Sheets that we are going to write a formula. If we want to multiple the value of B4 by 3, then we type `=B4*3`. When you are done with your formula you can hit *Enter* to see the result. 

Let's explore some ways we can use formulas in Car Info.

## Setting Up a New Column Based on a Formula

Sometimes, we want to set up a whole column where each value is the result of a formula. In the case of cars, since we have to pay property taxes on our vehicle, we want to set up a column for the tax value of each car. 

1. Add a new header to column G called "Tax Value".
1. We checked the tax rate and on cars right now, it is 2%, so the taxes we owe would be 2% of the current value.
1. Starting with G2, write in that cell the formula for finding the tax value of the car. As you write the cell identifuer for the current value of row 2, Google Sheets will highlight the cell that you are referencing which can serve as a helpful visual reminder of what the formula is going to be using.
1. Now we want every row in column G to accurately reflect the tax value of the car. To copy the formula and not the value in G2, hover your mouse over the bottom right corner of G2 and you will see a plus sign appear. Click and drag down to G3. Release once both cells are highlighted and you should see 2% of E3 in G3. To confirm, click on the cell to see what the formula looks like.
1. If you want to add another row, you can click and drag down as you did above.

The benefit of setting up a formula like this is that we don't have to worry about a human miscalculating and even more importantly, these cars are going to depreciate in value so that "Current Value" column is going to look different over time. Instead of us have to updating both the current value and the tax value when the car depreciates, we can update the current value and the tax value will update to reflect the change.

## Setting up a constant

Just as the current value may change, so may the tax rate. However, we don't want to go through every cell and make sure the formula is updated. We also don't want to add a new column with the tax rate because that is going to involve some extra data entry. We want to make this as simple as possible!

1. Over in J6, let's add "Current Tax Rate" and in K6, we will add 0.02.
1. We want to reference K6 in our formula for the tax value, but we want it to be constant for each row. We can reference K6 with dollar signs to designate that the value is a constant in our formula, like so `$K$6`. Try updating your formula in G2 and seeing if you get the same number.
1. Once you are satisfied, click and drag down to G3 to update that formula. You won't see the number change, but you can click on the cell to see that the formula is updated and that both values are based on the current tax rate.

## Connecting to Another Sheet

Finally, in a formula, you may want to reference a cell in another spreadsheet. In the case of Car Info, we want to take the sum of all the maintenance tasks and place it in a column on our Overview spreadsheet.

{{% notice blue "Note" rocket %}}
   For now, we will be importing one cell at a time. We can reference a range of cells in a formula using `IMPORTRANGE`, which we will see later in this class.
{{% /notice %}}

1. Add another header to H for "Maintenance Budget Used"
1. To reference another spreadsheet in a formula, we first need to type the name of the spreadsheet, an exclamation point, and then the cell. If we have a spreadsheet named "Budget" and we want to reference A1 in that spreadsheet, then we would write `Budget!A1`. If there are spaces in our spreadsheet name, then it should be wrapped in single quotes like `'Budget 2024'!A1`.
1. We want to track how much of each car's maintenance budget has been spent. Since there is only one maintenance job for one car in another spreadsheet, we are going to set up a formula and NOT click and drag it to the second car. Use the above to reference the cost of the one maintenance task and divide it by a budget of 2000 to see how much we have used so far.

With formulas, the possibilities are endless! We can also make use of the *Quick Calculations* menu to easy set up sums and averages.