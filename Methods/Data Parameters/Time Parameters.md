#### <a name="string" href="#wiki-string">.time( *string* )</a>

Defines the value to be used for slicing the data into different time periods. Currently, **D3plus** has very rudimentary time capabilities. It assumes all time variables to be integers, and places the responsibility of formatting onto the user.

#### <a name="function" href="#wiki-function">.time( *function* )</a>

You can also pass a *function* as a method of determining the time value for a node. **D3plus** will pass your function the data point in question, and the function should return the value requested.

#### <a name="object" href="#wiki-object">.time( *object* )</a>

This method also supports passing an *object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| fixed | When set to ```false```, the axes will remain static as you change the time visible (using mute/solo or a [[Timeline]]). <br><br> This makes it easier to see trends over time. If you would like the axes to change as time changes, set this to ```true```. | ```false```, ```true``` | ```false``` |
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Filtering-Data#mute). | **value**, *function*, *array* | ```[]``` |
| solo | Shows only specific data points to the viewer. Useful for only displaying specific time periods of data. Full documentation can be found [here](Filtering-Data#solo). | **value**, *function*, *array* | ```[]``` |
| value | When passing only a *string* or *function* to the method, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [[Unique ID]]. This will tell **D3plus** to look in that specific nesting level's attribute list for the value.  | *string*, *function*, *object*, ```false``` | ```false``` |
