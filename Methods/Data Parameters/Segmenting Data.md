#### <a name="active" href="#active">.active( *string* )</a>

Defines the key in your data associated with the number of "active" parts. This variable should be used in conjunction with the [Total Segments](#total) method to correctly display fill percentages inside of shapes (such as making each node in a scatter plot a pie chart).

#### <a name="activefunction" href="#activefunction">.active( *function* )</a>

You can also pass a function as a method of determining which objects are "active". **D3plus** will pass your function the data point in question, and the function should return the value requested.

#### <a name="activeobject" href="#activeobject">.active( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *function*, *array* | ```[]``` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *function*, *array* | ```[]``` |
| spotlight | Determines the behavior of inactive nodes, based on how the current visualization handles it. For example, when this is set to ```true``` for a [[Network]], all of the "inactive" nodes will be greyed out, giving more emphasis on the "active" nodes. | *boolean* | ```false``` |
| value | Defines the key in your data associated with the number of "active" parts. When passing only a *string* or *function* to the  method, this is the variable that actually gets set. <br><br> You can also pass a single keyed *object*, keyed by the appropriate nesting level's [[Unique ID]]. This will tell **D3plus** to look in that specific nesting level's attribute list for the active variable. Additionally, if the *object* you pass to this method does not contain any of the following keys, **D3plus** will use the *object* as this key. | *string*, *function*, *object*, ```false``` | ```false``` |

#### <a name="temp" href="#temp">.temp( *string* )</a>

Defines the key in your data associated with the number of "temporary" parts. This variable should be used in conjunction with the [Total Segments](#total) method to correctly display fill percentages inside of shapes (such as making each node in a scatter plot a pie chart).

#### <a name="tempfunction" href="#tempfunction">.temp( *function* )</a>

You can also pass a function as a method of determining which objects are "temporary". **D3plus** will pass your function the data point in question, and the function should return the value requested.

#### <a name="tempobject" href="#tempobject">.temp( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *function*, *array* | ```[]``` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *function*, *array* | ```[]``` |
| value | Defines the key in your data associated with the number of "temporary" parts. When passing only a *string*  or *function* to the this method, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [[Unique ID]]. This will tell **D3plus** to look in that specific nesting level's attribute list for the temporary variable. Additionally, if the *object* you pass tothis method does not contain any of the following keys, **D3plus** will use the *object* as this key. | *string*, *function*, *object*, ```false``` | ```false``` |

#### <a name="total" href="#total">.total( *string* )</a>

Defines the key in your data associated with the total number of parts of a data point. This variable should be used in conjunction with the [Active Segments](#active) method and/or the [Temporary Segments](#temp) method to correctly display fill percentages inside of shapes (such as making data nodes in a [[Scatter Plot]] appear as pie charts).

#### <a name="totalfunction" href="#totalfunction">.total( *function* )</a>

You can also pass a function as a method of determining the total number of parts of a data point. **D3plus** will pass your function the data point in question, and the function should return the value requested.

#### <a name="totalobject" href="#totalobject">.total( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *function*, *array* | ```[]``` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *function*, *array* | ```[]``` |
| value | Defines the key in your data associated with the total number of parts of a data point. When passing only a *string* or *function* to this method, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [[Unique ID]]. This will tell **D3plus** to look in that specific nesting level's attribute list for the total variable. Additionally, if the *object* you pass to this method does not contain any of the following keys, **D3plus** will use the *object* as this key. | *string*, *function*, *object*, ```false``` | ```false``` |
