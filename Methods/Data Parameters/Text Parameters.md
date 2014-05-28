#### <a name="string" href="#wiki-string">.text( *string* )</a>

Defines the value used when labeling shapes and [[Tooltips]].

When not defined, **D3plus** defaults to using the [[Unique ID]] for all labeling.

#### <a name="array" href="#wiki-array">.text( *array* )</a>

Defines a list of value to try to use for labels. If the value of the first key does not fit in the allotted space (like a small square in a [[Tree Map]], **D3plus** will then try to fit the second value, and so on.

The first value in the *array* will always be used in [[Tooltips]].

#### <a name="function" href="#wiki-function">.text( *function* )</a>

You can also pass a function as a way of determining the text for each node. **D3plus** will pass your function the data point in question, and the function should return the value requested.

#### <a name="object" href="#wiki-object">.text( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Filtering-Data#mute). | **value**, *function*, *array* | ```[]``` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Filtering-Data#solo). | **value**, *function*, *array* | ```[]``` |
| value | When passing only a *string* or *array* to the method, this is the variable that actually gets set. <br><br> You can also pass a single keyed *object*, keyed by the appropriate nesting level's [[Unique ID]]. This will tell **D3plus** to look in that specific nesting level's attribute list for the value. | *string*, *array*, *function*, *object*, ```false``` | ```false``` |
