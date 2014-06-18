#### <a name="string" href="#string">.size( *string* )</a>

Defines the value to use when sizing data nodes. The value should always be a *float* or *integer*.

#### <a name="array" href="#array">.size( *array* )</a>

[[Text Wrapping]] allows passing an *array* of 2 *numbers* to be used as a minimum and maximum font size when [[resizing|Automatic Resizing]] text.

#### <a name="function" href="#function">.size( *function* )</a>

You can also pass a function as a way of determining the size of a node. **D3plus** will pass your function the data point in question, and the function should return the value requested.

#### <a name="object" href="#object">.size( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *function*, *array* | `[]` |
| rendering | The default shape-rending used for the SVG objects. | `"auto"`, `"optimizeSpeed"`, `"crispEdges"`, `"geometricPrecision"` | `"auto"` |
| scale | Determines the scaling of nodes. | *function* | `d3.scale.sqrt()` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *function*, *array* | `[]` |
| threshold | Whether or not visualizations (if applicable) should automatically group data into an "other" object. This is especially helpful in [[Stacked Area]] when there is a lot of thin data slices. | *boolean* | `true` |
| value | Defines the key to use when sizing data nodes. When passing only a *string* or *function* to the method, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [[Unique ID]]. This will tell **D3plus** to look in that specific nesting level's attribute list for the value. | *string*, *function*, *object*, *array*, `false` | **visualization**:`false` <br> **textwrap**:`[ 9 , 40 ]` |
