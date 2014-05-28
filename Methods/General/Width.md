#### <a name="integer" href="#wiki-integer">.width( *integer* )</a>

Sets the width, in pixels, of the current output.

#### <a name="object" href="#wiki-object">.width( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| secondary&nbsp;<sup>***new***</sup> | Sets the width of secondary elements, such as the dropdown window in the "drop" Form. <br><br> If set to ```false```, the width will be calculated based on the width of the primary element. | *number*, ```false``` | ```false``` |
| small | When the width of a visualization is less than or equal to this *number*, it will enter "small" mode, where some functionality is disabled. | *number* | ```400``` |
| value | When passing only a *number* to the method, this is the variable that actually gets set. | *number* | The width of the [[Container Element]], if defined. Otherwise: ```window.innerWidth``` |
