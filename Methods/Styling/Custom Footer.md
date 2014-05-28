#### <a name="string" href="#wiki-string">.footer( *string* )</a>

Defines footer text to be displayed underneath a visualization (and in large tooltips).

To remove the footer, simply pass ```false``` to the method.

#### <a name="object" href="#wiki-object">.footer( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| link | A URL for the footer to open when clicked. The page will open in a new window/tab. | *string*, ```false``` | ```false``` |
| font | Defines font styles specific to the footer. The supported [[Font Styles]] are: "align", "color", "decoration", "family", "size", "transform", "weight" | *object* | Default style |
| padding | Pixel padding to be given around the footer. | *number* | ```0``` |
| position | What side of the visualization the footer should be positioned on. | ```"top"```, ```"bottom"``` | ```"bottom"``` |
| value | When passing only a *string* to the method, this is the variable that actually gets set. | *string*, ```false``` | ```false``` |
