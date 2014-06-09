#### <a name="boolean" href="#boolean">.labels( *boolean* )</a>

Defines whether or not visualizations should attempt to label shapes based on the current [[Text Parameters]].

Defaults to ```true```.

#### <a name="object" href="#object">.labels( *object* )</a>

This method also supports passing a keyed *object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| align | Determines the text-anchor of the label. | ```"start"```, ```"middle"```, ```"end"``` | ```"middle"``` |
| font | [[Font Styles]] of the labels. Currently supports passing a keyed *object* with the following keys: "decoration", "family", "size", "transform", "weight". | *object* | Default style |
| padding | *number* value of how much pixel padding to allow on all sides of each label. | *number* | ```7``` |
| resize | Whether or not labels should be sized to fit the available space. | *boolean* | ```true``` |
| segments | *integer* value to determine how many segments to break an "area" shape into when analyzing positioning. | *integer* | ```2``` |
| value | Defines whether or not labels are visible. When passing only a *boolean* to the method, this is the variable that actually gets set. | *boolean* | ```true``` |
