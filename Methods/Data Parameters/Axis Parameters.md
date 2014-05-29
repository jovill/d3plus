#### <a name="string" href="#wiki-string">.x( *string* ) and .y( *string* )</a>

Defines the value in your data to be associated with the axis in the [[Chart]] visualization.

#### <a name="function" href="#wiki-function">.x( *function* ) and .y( *function* )</a>

You can also pass a *function* as a way of determining the axis value. **D3plus** will pass your function the data point in question, and the function should return the value requested.

#### <a name="object" href="#wiki-object">.x( *object* ) and .y( *object* )</a>

This method also supports passing a keyed *object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| domain | Defines the domain to be used when drawing the axis. If passed ```false```, **D3plus** will calculate the domain based on the data available (which it does by default). | *array*, ```false``` | ```false``` |
| lines | Will plot the values passed as static lines on the axis. If the value is a single keyed *object*, **D3plus** will use the key as a label for the line and the value as the position. | *array* containing *numbers* and/or *objects* | ```false``` |
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *function*, *array* | ```false``` |
|s cale | Defines the scale to use when plotting points on the axis. <br><br> A ```"continuous"``` scale will assume each value is unique, and will create a tick for each instance of that value (for example, when using [[Time Parameters]]). <br><br> A ```"share"``` scale will plot values as percentages out of all of the available values. | ```"linear"```, ```"log"```, ```"continuous"```, ```"share"``` | ```"linear"``` |
| stacked | Determines whether or not axis values should be stacked on top of each other. | *boolean* | ```false``` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo).|**value**, *function*, *array* | ```false``` |
| value | When passing only a *string* or *function* to the method, this is the variable that actually gets set. <br><br> You can also pass a single keyed *object*, keyed by the appropriate nesting level's [[Unique ID]]. This will tell **D3plus** to look in that specific nesting level's attribute list for the value.  | *string*, *function*, *object*, ```false``` | ```false``` |
| zerofill | If scale is ```"continuous"```, this determines whether or not **D3plus** should fill gaps in the axis with ```0``` values. | *boolean* | ```false``` |

#### <a name="axes" href="#wiki-axes">.axes( *object* )</a>

Defines specific parameters for visualizations that use X and Y axes. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mirror | Tells the visualization to use the same range for both axes. **D3plus** will calculate both axes' domains, and then combine them into a final matched domain. | *boolean* | ```false``` |
| ticks<sup>***new***</sup> | Defines different aspects of the tick marks on both axes. The allowed keys are: "color", "font", "size", and "width". | *object* | Style defaults |
