#### <a name="string" href="#string">.shape( *string* )</a>

Sets the shape used to display data. If the shape specified is not supported in the current visualization, **D3plus** will fallback to the primary shape for that visualization.

#### <a name="object" href="#object">.shape( *object* )</a>

This method also supports passing an *object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| interpolate | If the shape supports it, you can change the line interpolation type. This is particularly useful in [[Stacked Area]]. | ```"linear"```, ```"step"```, ```"step-before"```, ```"step-after"```, ```"basis"```, ```"basis-open"```, ```"cardinal"```, ```"cardinal-open"```, ```"monotone"``` | ```"linear"``` |
| value | When passing only a *string* to the method, this is the variable that actually gets set. | ```"circle"```, ```"donut"```, ```"line"```, ```"square"```, ```"area"```, ```"coordinates"```| The primary shape of the initial visualization. |
