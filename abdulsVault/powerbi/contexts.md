no iterator - no row context

row context - table level (unaware of relationships by itself unless related() used)
filter context - model level

filter context is essentially a group by in sql using following measure for each cell in pivot table

SUMMARIZE (group_by, {",", <group_by>},<iterator>)
//note the filter context followed by an iterator i.e. the row context

SUMMARIZE deprecated by SUMMARIZECOLUMNS()


row context = current row (not the matrix in the viz!!!)

DAX operators on columns

MEASURES COMPUTED AT AGGREGATE LEVELS - row context limitation

WITHOUT ROW CONTEXT YOU CANNOT ACCESS ROW'S VALUE


Amount := SUM ( Sales[Quantity] ) * SUM ( Sales[Net Price] )
//multiplication of two aggregations!

iterator = goes row by row

Amount :=
--
--  Outside of SUMX, there is no row context
--
SUMX (
    Sales,                               -- Sales is evaluated in the outer context
    Sales[Quantity] * Sales[Net Price]   -- The multiplication is evaluated in the row context
)
--
--  Outside of SUMX, the row context is no longer there
If you need to access columns in another table linked through a relationship, then you can rely on the RELATED and RELATEDTABLE functions, which we cover in other articles