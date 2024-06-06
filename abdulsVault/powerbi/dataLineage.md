What? Data lineage is a tag

EVALUATE VALUES('Product'[Category])

{'category':['audio','tv and audio',...]}

Context transition iterating values filters the Sales Table with this measure

EVALUATE
ADDCOLUMNS (
    VALUES ( 'Product'[Category] ), //in product table
    "Amt", [Sales Amount] //in sales table
)
//filter propagation from product to sales table
//context transition iterating values, Product[Category]
//context transition occuring because of the measure from row context to filter context (query context in this case)

-- filter contexts applied to measures mostly

Data lineage is maintained as long as an expression is only made up of one column reference

For example, adding an empty string to Product[Category] in the previous expression does not change the column content, whereas it does break the data lineage

EVALUATE
ADDCOLUMNS (
    SELECTCOLUMNS (
        VALUES ( 'Product'[Category] ),
        "New name for Category", 'Product'[Category] & ""
    ),
    "Amt", [Sales Amount]
)

This will fail to apply filter context

EVALUATE
VAR Categories =
    DATATABLE (
        "Category", STRING,
        {
            { "Category" },
            { "Audio" },
            { "TV and Video" },
            { "Computers" },
            { "Cameras and camcorders" },
            { "Cell phones" },
            { "Music, Movies and Audio Books" },
            { "Games and Toys" },
            { "Home Appliances" }
        }
    )
RETURN
    ADDCOLUMNS ( Categories, "Amt", [Sales Amount] ) //we have lost data lineage of products[category]


Data lineage means capability of parent table is inherited e.g. product filtering sales even if you rename the column. The DATATABLE() will fail miserably as the string can'not provide the appropriate context transition

EACH COLUMN HAS ITS OWN DATA LINEAGE

DATA LINEAGE ENABLES FILTER PROPAGATION

TREATAS (forcing data lineage) returns the same input table, with each column tagged with the data lineage of the column references specified as arguments. If some of the values in the table contain values that do not correspond to a valid value in the column used to apply the data lineage change, then TREATAS removes the values from the inpu


EVALUATE
VAR Categories =
    DATATABLE (
        "Category", STRING,
        {
            { "Category" },
            { "Audio" },
            { "TV and Video" },
            { "Computers and geeky stuff" },
            { "Cameras and camcorders" },
            { "Cell phones" },
            { "Music, Movies and Audio Books" },
            { "Games and Toys" },
            { "Home Appliances" }
        }
    )
RETURN
    ADDCOLUMNS (
        TREATAS (
            Categories,
            'Product'[Category]
        ),
        "Amt", [Sales Amount]
    )






