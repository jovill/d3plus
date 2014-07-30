#### <a name="string" href="#string">.color( *string* )</a>

Defines the value in your data associated with the color of each node.

If the value is a hexadecimal color *string* (eg. `"#cc0000"`), **D3plus** will simply use that as the node's color.

If it returns a non-color *sting*, a random color based on that string will be used.

Finally, if the key returns a *number*, **D3plus** will map the values to a heat map.

#### <a name="function" href="#function">.color( *function* )</a>

You can also pass a function as a way of determining the color of a node. **D3plus** will pass your function the data point in question, and the function should return the value requested.

#### <a name="object" href="#object">.color( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| heatmap | An *array* of colors to use when color values are all positive *numbers*. Can be any number of colors. | *array* of colors | `[ "#27366c" , "#7b91d3" , "#9ed3e3" ` `, "#f3d261" , "#c9853a" , "#d74b03" ]` |
| focus | A color to use for the [[Focus Element]]. | *color* | `"#444444"` |
| missing | A color to use for when a shape has no data associated with it. | *color* | `"#eeeeee"` |
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *function*, *array* | `[]` |
| primary | A color to use for primary connections in the [[Edges List]]. | *color* | `"#d74b03"` |
| range | An *array* of colors to use when the [[Color Parameters]] range from negative to positive. Must be an array of 3 colors. | *array* of colors | `[ "#d74b03" , "#eeeeee" , "#94b153" ]` |
| secondary | A color to use for secondary connections in the [[Edges List]]. | *color* | `"#e5b3bb"` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *function*, *array* | `[]` |
| value | Defines the key in your data associated with the color of each node. When passing only a *string* or *function* to the method, this is the variable that actually gets set. <br><br> You can also pass a single keyed *object*, keyed by the appropriate nesting level's [[Unique ID]]. This will tell **D3plus** to look in that specific nesting level's attribute list for the value. | *string*, *function*, *object*, `false` | **visualization**:`false` <br> **form**:`"color"` |
