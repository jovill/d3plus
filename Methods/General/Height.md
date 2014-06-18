#### <a name="number" href="#number">.height( *number* )</a>

Sets the height, in pixels, of the current output.

#### <a name="object" href="#object">.height( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| secondary | Sets the height of secondary elements, such as the dropdown window in the "drop" Form. <br><br> If set to `false`, the height will be calculated based on the available space inside of the current window. | *number*, `false` | `false` |
| small | When the height of a visualization is less than or equal to this *number*, it will enter "small" mode, where some functionality is disabled. | *number* | `300` |
| max | Sets the max-height of secondary elements, such as the dropdown window in the "drop" Form. | *number*, `false` | `600` |
| value | When passing only a *number* to the method, this is the variable that actually gets set. | *number* | The height of the [[Container Element]], if defined. Otherwise: `window.innerHeight` |
