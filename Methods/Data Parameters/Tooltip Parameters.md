#### <a name="array" href="#array">.tooltip( *array* )</a>

Defines a list of values to be displayed in the tooltip created for each node.

#### <a name="lengths" href="#lengths">.tooltip( { "short": *array* , "long": *array* } )</a>

Creates separate lists of values to be displayed in small tooltips and large tooltips.

#### <a name="object" href="#object">.tooltip( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| anchor | The anchor point on the node for the floating tooltip. | Should be defined as two words, the first representing vertically "top", "middle", or "bottom" and the second representing horizontal "left", "center", or "right". | ```"top center"``` |
| background | The background color for the tooltip. | *color* | ```"#ffffff"``` |
| curtain | Styles for the full page "curtain" that is displayed behind a large tooltip. Accepted keys are: "color" and "opacity". | *object* | Default styles |
| font | [[Font Styles]] for the tooltips. Currently supports passing a keyed *object* with the following keys: "color", "family", "size", "transform", and "weight". | *object* | Default style |
| html | Defines HTML content to be displayed in a large tooltip underneath the specified tooltip keys. If passed a *function*, **D3plus** will call the *function*, passing the current data point to the function, and will expect a *string* in return. <br><br> If passed an *object* with "url" and "callback" keys, **D3plus** will make a [d3.json](https://github.com/mbostock/d3/Requests#d3_json) request using the "url" provided, and call the "callback" *function* once data is returned. The "callback" *function* should then return a valid HTML *string*.| *string*, *function*, *object*, ```false``` | ```false``` |
| large | *number* width for large tooltips created inside a visualization. | *number* | ```250``` |
| small | *number* width for small tooltips created inside a visualization. | *number* | ```200``` |
| value | When passing only an *array* or an *object* with either "short" and "long" keys or nesting levels, this is the value that gets set. | *array*, *object*, ```false``` | ```false``` |
