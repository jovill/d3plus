#### <a name="boolean" href="#wiki-boolean">.timeline( *boolean* )</a>

Displays a timeline slider that allows the user to change the soloed [[Time Parameters]]. Defaults to ```true```.

#### <a name="object" href="#wiki-object">.timeline( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| align | Determines the horizontal position of the timeline. | ```"start"```, ```"middle"```, ```"end"``` | ```"middle"``` |
| background | The background color of the timeline. | *color* | ```"#eeeeee"``` |
| brush | Style attributes for the brush. Supported keys are: "color" and "opacity" | *object* | Default style |
| handles | Toggles the visibility of the handles on the selected timeline range. <br><br> If passed an object, you can define the following style keys: "color", "hover", "opacity", "size", and "stroke" | *boolean*, *object* | ```true``` |
| height | The pixel height of the timeline. | *number* | ```20``` |
| tick | [[Font Styles]] for each tick label on the timeline. Currently supports passing a keyed *object* with the following keys: "align", "color", "family", "size", "weight". | *object* | Default style |
| value | The key that gets set when only passing a *boolean* to the method. | *boolean* | ```true``` |
