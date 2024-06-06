SEMI ADDITIVE measures

Additive measure uses sum() for the dimension in question

Case example: balances in Accounting when c/f to next month

dimensions:
	x - customers
	y - months


balance c/f per month = correct
balance c/f per customer = wrong => why => balance is reported on last date basis not cumulative

Therefore, we need semi-additive measure that uses sum() over month dim only, and "another" aggregation over another dim (case example customer should not be using sum() as that would lead to additive measure)

See this for example <img src=https://cdn.sqlbi.com/wp-content/uploads/Semi-additive-measures-in-DAX-01.png>

First solution:

LastBalance LD :=
CALCULATE (
    SUM ( Balances[Balance] ),
    LASTDATE ( 'Date'[Date] )
) 
//The filter context changed to LastDate()
//lastDate() works on date table but last date of the year and quarter is has no data!

Problem: no result in totals of quarter and year level


LastBalance MD :=
VAR LastBalanceDate = MAX ( Balances[Date] )
RETURN
    CALCULATE (
        SUM ( Balances[Balance] ),
        'Date'[Date] = LastBalanceDate
    )
//

technique debugging: replace with actual date to pintpoint missing data

when there is no filter context e.g. as in total, the last date is date of all the customers i.e. 18Nov where two of the customers having missing data.