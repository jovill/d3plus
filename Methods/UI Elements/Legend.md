#### <a name="boolean" href="#boolean">.legend( *boolean* )</a>

Displays a color legend that helps the user see how colors are associated with shapes.

When coloring shapes by *numbers*, the legend will show the appropriate color gradient used. Otherwise, it will show each individual color as a square block with a tooltip that contains information about that category.

Defaults to ```true```.

#### <a name="object" href="#object">.legend( *object* )</a>

This method also supports passing a keyed *object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| align | Determines the horizontal position of the legend. | ```"start"```, ```"middle"```, ```"end"``` | ```"middle"``` |
| font | [[Font Styles]] for the legend. Currently supports passing a keyed *object* with the following keys: "align", "color", "family", "size", "weight". | *object* | Default style |
| gradient | Styling of the gradient used for color scales. Currently supports passing a keyed *object* with the following keys: "height". | *object* | `{ "height": 10 }` |
| order | When passed a *string*, this sets the order of the color boxes in the timeline.<br><br>When passed an *object*, the "sort" value can be set to either "asc" or "desc". | ```color```, ```id```, ```size```, ```text```, *object* | ```color``` |
| size | *number* or *array* of value(s) for the width and height of color blocks. If an *array*, it should have 2 ordered values, the minimum and maximum. | *number*, *array* | ```[ 8 , 30 ]``` |
| value | Defines whether or not the legend is visible. When passing only a *boolean* to the method, this is the variable that actually gets set. | *boolean* | ```true``` |
