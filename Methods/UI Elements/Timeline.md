#### <a name="boolean" href="#boolean">.timeline( *boolean* )</a>

Displays a timeline slider that allows the user to change the soloed [[Time Parameters]]. Defaults to `true`.

#### <a name="object" href="#object">.timeline( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| align | Determines the horizontal position of the timeline. | `"start"`, `"middle"`, `"end"` | `"middle"` |
| hover | The cursor style for when hovering over the handle. | `"all-scroll"`, `"col-resize"`, `"crosshair"`, `"default"`, `"grab"`, `"grabbing"`, `"move"`, `"pointer"` | `"pointer"` |
| handles | Toggles the visibility of the handles on the selected timeline range. <br><br> If passed an object, you can define the following style keys: "color", "hover" (color), "opacity", "size", and "stroke" | *boolean*, *object* | `true` |
| height | The pixel height of the timeline. | *number* | `23` |
| tick | The style of each "tick" in between each value on the timeline. | *color* | `"#818181"` |
| value | The key that gets set when only passing a *boolean* to the method. | *boolean* | `true` |
