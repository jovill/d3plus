#### <a name="topojson" href="#wiki-topojson">.coords( *topojson* )</a>

For visualizations that use geography, you can pass a [Topojson](https://github.com/mbostock/topojson) object to **D3plus**. Each feature inside of your topojson must have a [[Unique ID]] value that matches your data.

#### <a name="object" href="#wiki-object">.coords( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| center | The position, in coordinate degrees, of the center of the map projection. | *array* | ```[0,0]``` |
| fit | Determines how coordinate bounds will be positioned within the dimensions of the visualization. | ```"auto"```, ```"width"```, ```"height"``` | ```"auto"``` |
| mute | Hides specific coordinate objects from the viewer. Full documentation can be found [here](Filtering-Data#mute). | **value**, *function*, *array* | ```[]``` |
| padding | How many pixels of padding should be applied to the bounds of a zoomed object. | *number* | ```20``` |
| projection | Which geographical projection should be used. | ```"equirectangular"```, ```"mercator"``` | ```"mercator"``` |
| solo | Shows only specific coordinate objects to the viewer. Full documentation can be found [here](Filtering-Data#solo). | **value**, *function*, *array* | ```[]``` |
| threshold | The minimum area required to be displayed. | *number* | ```0.1``` |
| value | The [Topojson](https://github.com/mbostock/topojson) *object* that gets set when just passing *topojson* to this method. | *topojson*, ```false``` | ```false``` |

#### <a name="url" href="#wiki-url">.coords( *URL* )</a>

When passing a *URL* to this method, **D3plus** will use it to load the data dynamically for you.

If a *callback* function is provided, the downloaded data will be passed through the function for formatting (which should then return the correctly formatted data).
