#### <a name="string" href="#string">.font( *string* )</a>

Sets the default overall font family to be used.

#### <a name="object" href="#object">.font( *object* )</a>

This method also supports passing a keyed *object*. Here are the accepted keys:

| Key | Description | Accepted Value(s) | Default Value |
| --- | --- | --- | --- |
| align | Sets the global font alignment. | ```"left"```, ```"center"```, ```"right"``` | ```"left"``` |
| color | Sets the color of all fonts used in the visualization. | *color* | ```"#444444"``` |
| decoration | Sets the text-decoration of all fonts used in the visualization. | ```"line-through"```, ```"none"```, ```"overline"```, ```"underline"``` | ```"none"``` |
| family | Sets the font-family used throughout the entire visualization. Can be a single *string*, *array*, or comma-separated font-families (like with CSS). | *array*, *string* | ```[ "Helvetica Neue" , "HelveticaNeue" ``` ```, "Helvetica" , "Arial" , "sans-serif" ]``` |
| secondary | Defines a secondary font style. For example, the drop down menu. | *object* | Same as primary font style. |
| size | General pixel font size. | *number* | ```12``` |
| spacing | General pixel letter spacing. | *number* | ```0``` |
| transform | Sets the text-transform of all fonts used in the visualization. | ```"capitalize"```, ```"lowercase"```, ```"none"```, ```"uppercase"``` | ```"none"``` |
| weight | Sets the font-weight of all fonts used in the visualization. | *string* or *number* | ```200``` |
