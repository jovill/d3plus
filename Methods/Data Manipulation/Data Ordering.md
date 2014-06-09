#### <a name="string" href="#string">.order( *string* )</a>

Sets the value to use when trying to order data points.

#### <a name="object" href="#object">.order( *object* )</a>

This method also supports passing a keyed *object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| sort |Changes the sort order of the data between ascending and descending. | ```"asc"```, ```"desc"``` |```"asc"``` |
| value | When passing only a *string* to the method, this is the variable that actually gets set. <br><br> You can also pass a single keyed *object*, keyed by the appropriate nesting level's [[Unique ID]]. This will tell **D3plus** to look in that specific nesting level's attribute list for the value. | *string*, *object*, ```false``` | ```false``` |
