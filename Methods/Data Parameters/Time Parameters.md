#### <a name="string" href="#string">.time( *string* )</a>

Defines the value to be used for slicing the data into different time periods. All values will be parsed into *Javascript Date Objects*, unless they are already in that format. We suggest using time formats specified in the first table on [this page](http://dygraphs.com/date-formats.html).

#### <a name="function" href="#function">.time( *function* )</a>

You can also pass a *function* as a method of determining the time value for a node. **D3plus** will pass your function the data point in question, and the function should return the value requested.

#### <a name="object" href="#object">.time( *object* )</a>

This method also supports passing an *object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| fixed | When set to `false`, the axes will remain static as you change the time visible (using mute/solo or a [[Timeline]]). <br><br> This makes it easier to see trends over time. If you would like the axes to change as time changes, set this to `true`. | `false`, `true` | `false` |
| format | A [D3 time format](https://github.com/mbostock/d3/wiki/Time-Formatting) function that will override the default behavior of **D3plus**. | `false`, `[d3.time.format](https://github.com/mbostock/d3/wiki/Time-Formatting)` | `false` |
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *function*, *array* | `[]` |
| solo | Shows only specific data points to the viewer. Useful for only displaying specific time periods of data. Full documentation can be found [here](Data-Filtering#solo). | **value**, *function*, *array* | `[]` |
| value | When passing only a *string* or *function* to the method, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [[Unique ID]]. This will tell **D3plus** to look in that specific nesting level's attribute list for the value.  | *string*, *function*, *object*, `false` | `false` |
