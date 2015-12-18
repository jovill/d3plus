The crux of **d3plus** is it's easy-to-use visualizations. By passing your data and setting a few methods that describe your data, **d3plus** effortlessly creates interactive visualizations to help your explore your data. You get a lot for free here: nesting, tooltips, timelines, legends, just to name a few. Here are the visualizations currently supported by **d3plus**:

| Tree Map | Scatter Plot | Stacked Area | Line Plot |
| :-: | :-: | :-: | :-: |
| <a href="http://d3plus.org/examples/basic/9029130/"><img src="https://gist.githubusercontent.com/davelandry/9029130/raw/thumbnail.png" width="100px"><br>Example</a> | <a href="http://d3plus.org/examples/basic/9029781/"><img src="https://gist.githubusercontent.com/davelandry/9029781/raw/thumbnail.png" width="100px"><br>Example</a> | <a href="http://d3plus.org/examples/basic/9029462/"><img src="https://gist.githubusercontent.com/davelandry/9029462/raw/thumbnail.png" width="100px"><br>Example</a> |<a href="http://d3plus.org/examples/basic/9037371/"><img src="https://gist.githubusercontent.com/davelandry/9037371/raw/thumbnail.png" width="100px"><br>Example</a> |
| [Documentation](Tree Map) | [Documentation](Scatter Plot) | [Documentation](Stacked Area) | [Documentation](Line Plot) |

| Network | Rings | Geo Map | Boxplot
| :-: | :-: | :-: | :-: | 
| <a href="http://d3plus.org/examples/basic/9042919/"><img src="https://gist.githubusercontent.com/davelandry/9042919/raw/thumbnail.png" width="100px"><br>Example</a> | <a href="http://d3plus.org/examples/basic/9034389/"><img src="https://gist.githubusercontent.com/davelandry/9034389/raw/thumbnail.png" width="100px"><br>Example</a> | <a href="http://d3plus.org/examples/basic/9042807/"><img src="https://gist.githubusercontent.com/davelandry/9042807/raw/thumbnail.png" width="100px"><br>Example</a> | <a href="http://d3plus.org/examples/basic/78018ce8c3787d4e30d9/"><img src="http://i.imgur.com/qj5ZzkG.png" width="100px"><br>Example</a>
| [Documentation](Network) | [Documentation](Rings) | [Documentation](Geo Map) | [Documentation](Box Plot)

# Getting Started

Given this data array:

```js
var data = [
  {"value": 100, "name": "alpha"},
  {"value": 70, "name": "beta"}
]
```

A simple [Tree Map](Tree Map) can be generated with the following code:

```js
d3plus.viz()
  .data(data)
  .type("tree_map")
  .id("name")
  .size("value")
  .draw()
```

# Available Methods

### <a name="active" href="#active">.active( *String* | *Function* | *Object* )</a>

Defines the key in your data associated with the number of "active" parts. This variable should be used in conjunction with the [.total( )](#total) method to correctly display fill percentages inside of shapes (such as making each node in a scatter plot a pie chart). You can also pass a function as a method of determining which objects are "active". **d3plus** will pass your function the data point in question, and the function should return the value requested.

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *Function*, *Array* | `[]` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *Function*, *Array* | `[]` |
| spotlight | Determines the behavior of inactive nodes, based on how the current visualization handles it. For example, when this is set to `true` for a [[Network]], all of the "inactive" nodes will be greyed out, giving more emphasis on the "active" nodes. | *Boolean* | `false` |
| value | Defines the key in your data associated with the number of "active" parts. When passing only a *String* or *Function* to the  method, this is the variable that actually gets set. <br><br> You can also pass a single keyed *Object*, keyed by the appropriate nesting level's [.id( )](#id). This will tell **d3plus** to look in that specific nesting level's attribute list for the active variable. Additionally, if the *Object* you pass to this method does not contain any of the following keys, **d3plus** will use the *Object* as this key. | *String*, *Function*, *Object*, `false` | `false` |

---

### <a name="aggs" href="#aggs">.aggs( *Object* )</a>

Defines how specific values should be aggregated when the **d3plus** aggregates your data. The *Object* passed should contain key/value pairs that match the keys in your data with the aggreagation value requested. For example, if you wanted all values of the key "wage" to use D3's "mean" comparator, then you would pass the following:

```js
.aggs({"wage": "mean"})
```

The *String* value passed with each key needs to be one of D3's predefined [array comparators](https://github.com/mbostock/d3/wiki/Arrays#d3_min), such as "mean", "median", "min", or "max". By default, all keys use [d3.sum()](https://github.com/mbostock/d3/Arrays#d3_sum). Additionally, you can also pass a *Function* as an aggregation method for a key. D3plus will pass the *Function* the array of data objects needing aggregation, and the *Function* should return the final aggregated value.

---

### <a name="attrs" href="#attrs">.attrs( *Array* | *Object* | *url* [, *callback*] )</a>

Defines a set of data points that are associated with the primary [.data( )](#data), but that do not change as the data changes. For example, Attribute Data could include colors and names that are static throughout all [.time( )](#time) while your [.data( )](#data) includes properties that change over time. The [.id( )](#id) that you set **MUST** be present inside of your attribute array, otherwise **d3plus** will have no way of matching attributes to data.

If it suits your needs, you may also pass an *Object* keyed by each [.id( )](#id). If your visualization uses nesting, you may want to pass a different attribute list for each nesting level. This can be achieved by passing an object that is keyed based on the nesting levels supplied to the [.id( )](#id) method.

When passing a *URL* to this method, **d3plus** will use it to load the data dynamically for you. Additionally, if a *callback* function is provided, the downloaded data will be passed through the function for formatting (which should then return the correctly formatted data).

---

### <a name="axes" href="#axes">.axes( *Object* )</a>

Defines specific parameters for visualizations that use X and Y axes. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| background | Styling for the background of the X/Y plot. Accepts the following keys: "color", "rendering", and a "stroke" *Object* with "color" and "width". | *Object* | Default style. |
| mirror | Tells the visualization to use the same range for both axes. **d3plus** will calculate both axes' domains, and then combine them into a final matched domain. | *Boolean* | `false` |

---

### <a name="background" href="#background">.background( *String* )</a>

The color of the overall background for the visualization.

---

### <a name="color" href="#color">.color( *String* | *Function* | *Object* )</a>

Defines the value in your data associated with the color of each node. If the value is a hexadecimal color *String* (eg. `"#cc0000"`), **d3plus** will simply use that as the node's color. If it returns a non-color *sting*, a random color based on that string will be used. Finally, if the key returns a *Number*, **d3plus** will map the values to a heat map. You can also pass a function as a way of determining the color of a node. **d3plus** will pass your function the data point in question, and the function should return the value requested.

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| focus | A color to use for the [.focus( )](#focus). | *color* | `"#444444"` |
| heatmap | An *Array* of colors to use when color values are all positive *numbers*. Can be any number of colors. | *Array* of colors | `["#282F6B", "#419391", "#AFD5E8", "#EACE3F", "#B35C1E", "#B22200"]` |
| missing | A color to use for when a shape has no data associated with it. | *color* | `"#eeeeee"` |
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *Function*, *Array* | `[]` |
| primary | A color to use for primary connections in the [.edges( )](#edges). | *color* | `"#d74b03"` |
| range | An *Array* of colors to use when the [[Color Parameters]] range from negative to positive. Must be an array of 3 colors. | *Array* of colors | `["#B22200", "#FFEE8D", "#759143"]` |
| scale | The color scale used when assigning random colors to objects. Supports the d3plus default color scale, the default d3 color scales, your own scale, or an array of values to use to create a scale. | *Array*, *Function*, `"d3plus"`, `"category10"`, `"category20"`, `"category20b"`, `"category20c"` | `"d3plus"` |
| secondary | A color to use for secondary connections in the [.edges( )](#edges). | *color* | `"#e5b3bb"` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *Function*, *Array* | `[]` |
| value | Defines the key in your data associated with the color of each node. When passing only a *String* or *Function* to the method, this is the variable that actually gets set. <br><br> You can also pass a single keyed *Object*, keyed by the appropriate nesting level's [.id( )](#id). This will tell **d3plus** to look in that specific nesting level's attribute list for the value. | *String*, *Function*, *Object*, `false` | **visualization**:`false` <br> **form**:`"color"` |

---

### <a name="cols" href="#cols">.cols( *Array* | *String* | *Function* | *Object* )</a>

Specify the columns displayed in the [table visualization](Table). If passed an object, here are the accessible keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| index | Whether or not the top-left column header should be displayed. | *Boolean* | `true` |
| value | When passing only an *Array*, *Function*, or *String* to the this method, this is the variable that actually gets set. | *Array*, *Function*, *String* | `false` |

---

### <a name="config" href="#config">.config( *Object* )</a>

When creating multiple visualizations, they often share the same basic set of method values. Using this method, multiple methods can be set using a pre-defined javascript Object that matches the structure of the various other methods. In this example, the [.id( )](#id), [.depth( )](#depth), and [.text( )](#text) methods are all being set by using only the .config( ) method:

```js
var defaults = {
  "id": ["country", "state"],
  "depth": 1,
  "text": "name"
}

d3plus.viz()
  .config(defaults)
```

---

### <a name="container" href="#container">.container( *selector* )</a>

Tells **d3plus** which page element to build the visualization inside of. This is a required method for every visualization. It supports all of the [D3 Selection Methods](https://github.com/mbostock/d3/wiki/Selections#selecting-elements), including D3 elements.

For example, to select an element with the ID of "box", you could say:

```js
.container( "#box" )
```

Or alternatively, you could also say:

```js
.container( d3.select("#box") )
```

Before creating a visualization, **d3plus** will remove all contents of the specified container element.

---

### <a name="coords" href="#coords">.coords( *Topojson* | *url* | *Object* [, *callback*] )</a>

For visualizations that use geography, you can pass a [Topojson](https://github.com/mbostock/topojson) object to **d3plus**. Each feature inside of your topojson must have a [.id( )](#id) value that matches your data. When passing a *URL* to this method, **d3plus** will use it to load the data dynamically for you. If a *callback* function is provided, the downloaded data will be passed through the function for formatting (which should then return the correctly formatted data).

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| center | The position, in coordinate degrees, of the center of the map projection. | *Array* | `[0,0]` |
| fit | Determines how coordinate bounds will be positioned within the dimensions of the visualization. | `"auto"`, `"width"`, `"height"` | `"auto"` |
| mute | Hides specific coordinate objects from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *Function*, *Array* | `[]` |
| padding | How many pixels of padding should be applied to the bounds of a zoomed object. | *Number* | `20` |
| projection | Which geographical projection should be used. | `"equirectangular"`, `"mercator"` | `"mercator"` |
| solo | Shows only specific coordinate objects to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *Function*, *Array* | `[]` |
| threshold | The minimum area required to be displayed. | *Number* | `0.1` |
| value | The [Topojson](https://github.com/mbostock/topojson) *Object* that gets set when just passing *Topojson* to this method. | *Topojson*, `false` | `false` |

---

### <a name="csv" href="#csv">.csv( *String* | *Array* | `true` )</a>

Whether or not a value is passed to this method, it will download a .csv file of the currently displayed data to the user's computer. If [.title( )](#title) is defined, it will use that for the filename (replacing spaces with hyphens). Otherwise, the file will be called "My-D3plus-App-Data.csv". A javascript version of the data (an *Array* of arrays) is also returned to javascript when this method is called.

If a *String* or *Array* of keys is passed to the method, **d3plus** will return a .csv file with only the key(s) specified as the columns.

If the *Boolean* `true` is passed to the method, the full un-edited raw user data will be returned as a .csv file, not just what is being currently displayed in the visualization.

---

### <a name="data" href="#data">.data( *Array* | *url* | *Object* [, *callback*] )</a>

Sets the data associated with your visualization. Each item in the array needs to be an object with keys that match what you have defined using other methods. Here is a simple example of what your data array could look like:

```js
.data([
  { "id": "alpha", "size": 52 },
  { "id": "beta", "size": 23 }
])
```

When passing a *URL* to the data method, **d3plus** will use it to load the data dynamically for you. If a *callback* function is provided, the downloaded data will be passed through the function for formatting (which should then return the correctly formatted data).

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| delimiter | The string delimiter used when parsing DSV files from a *url*. | *String* | "&#124;" |
| donut | Sets styling for "donut" shapes. Currently supports passing a keyed *Object* with a "size" parameter. | *Object* | `{ "size": 0.35 }` |
| filetype | The file extension when loading data from a *url*. If set to `false`, **d3plus** will try to auto-detect. | `false`, `"json"`, `"xml"`, `"html"`, `"csv"`, `"dsv"`, `"tsv"`, `"txt"` | `false` |
| large | If the number of data nodes drawn on the screen exceeds this number, all transitions animations will be disabled. This is prevents lag and stuttering with large datasets. | *integer* | `400` |
| opacity | Sets default shape opacity. Currently supports passing a *float* between  `0` and `1`. | *float* | `0.9` |
| padding | Defines padding in between shapes. Currently used in the Tree Map. | *Number* | `1` |
| stroke | Sets styling for a shape's outer stroke. Currently supports passing a keyed *Object* with a "width" parameter. | *Object* | `{ "width": 1 }` |
| value | When passing only an *Array* or *url* to this method, this is the variable that actually gets set. | *Array*, *url* | `false` |

---

### <a name="depth" href="#depth">.depth( *Integer* | *Function* )</a>

If you have specified nesting while setting your [.id( )](#id), then this method allows you to switch between those nesting levels. It accepts integer values that match the desired position in the nesting array. For example, given the following nesting:

```js
.id(["country", "state", "city"])
```

You would show `"state"` aggregations by setting the depth as follows:

```js
.depth(1)
```

---

### <a name="descs" href="#descs">.descs( *Object* | *Function* )</a>

Sets descriptions for each specified value. Currently, these descriptions are visible in static tooltips as a small question mark that appears next to the value name. If passed a *Function*, the value name will be passed and it is expected to return the description.

---

### <a name="dev" href="#dev">.dev( *Boolean* )</a>

Toggles verbose development mode, which displays logs and timers in the browser's console related to the activity on screen. Defaults to `false`.

---

### <a name="draw" href="#draw">.draw( )</a>

Draws the visualization inside of the specified [.container( )](#container). When the visualization gets drawn for the first time, or if the container has changed, all previous contents of the element will be removed. This method should also be called after changing/updating other methods in order to update the content being displayed.

---

### <a name="edges" href="#edges">.edges( *Array* | *Object* | *url* )</a>

Sets the list of edges between objects for visualizations that require edges (such as [Network](Network) and [Rings](Rings)). The *Array* passed to this method must be in the following format, with the "source" and "target" matching the [.id( )](#id) value.

```js
.edges([
  {
    "source": 1,
    "target": 2
  },
  {
    "source": 3,
    "target": 1
  }
])
```

When passing a *URL* to this method, **d3plus** will use it to load the data dynamically for you. If a *callback* function is provided, the downloaded data will be passed through the function for formatting (which should then return the correctly formatted data).

This method also supports passing an *Object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| arrows | Determines whether or not arrows should be drawn at the end of each link.<br><br>When passing a *Boolean*, the arrows will be toggled on/off with a default width of `10` pixels.<br><br>When passing a *Number*, that number will be used as the width of the arrow.<br><br>When passing an *Object*, the user can define both the "value" (which is what gets set when not passing an *Object*) and the "direction" of the arrows, which is either `"source"` or `"target"` (defaults to `"target"`) | *Boolean*, *Number*, *Object* | `false` |
| color | The color of each edge. | *color* | `"#d0d0d0"` |
| delimiter | The string delimiter used when parsing DSV files from a *url*. | *String* | "&#124;" |
| filetype | The file extension when loading data from a *url*. If set to `false`, **d3plus** will try to auto-detect. | `false`, `"json"`, `"xml"`, `"html"`, `"csv"`, `"dsv"`, `"tsv"`, `"txt"` | `false` |
| interpolate | Changes the line interpolation type for curved lines (like in [Rings](Rings)). | `"linear"`, `"step"`, `"basis"`, `"cardinal"`, `"monotone"` | `"basis"` |
| label | Value within each edge object to be used as a label for the connection. | *String*, `false` | `false` |
| large | The cutoff for a "large" network. When there are more than this number of edges displayed on screen, certain transitions and styles will be disabled because it becomes too computationally heavy to modify the large amount of edges on the fly (for example, when highlighting specific connections on hover). | *integer* | `100` |
| limit | Limits the number of primary connections to be shown in Rings and the maximum number of paths in Paths. | *integer*, `false` | `false` |
| opacity | Sets default link opacity. Supports a number, a user-defined function that gets passed the edge data and expects an opacity in return, or a string key of the edges to run through a linear scale. The type of scale being used is accessible from the "scale" key inside of opacity. | *Number*, *String*, *Function* | `1` |
| size | Static number or a key to a value within each link object to be used to size the stroke width of each connection. Additionally, there is a "scale" number accessible that defines what percentage of the smallest node's diameter to allow for the max edge width (there is also a "min" key). | *Number*, *String*, `false` | `false` |
| source | Sets the key associated with the edge "source". | *String* | `"source"` |
| strength | The value associated with the strength of the edge to be used when automatically calculating node positions. | `false`, **Function**, **Number**, *String* | `false` |
| target | Sets the key associated with the edge "target". | *String* | `"target"` |
| value | When passing only an *Array* to this method, this is the variable that actually gets set. | *Array* | `false` |
| width | *Number* that represents the stroke-width of each link. | *Number* | `1` |

---

### <a name="error" href="#error">.error( *String* | *Boolean* )</a>

Sets an error message to override the visualization. This halts the visualization and displays your message instead.

---

### <a name="focus" href="#focus">.focus( `false` | *String* | *Number* | *Array* | *Object* )</a>

If the visualization supports it, this defines which data node to focus on. For example, this sets the center node in [Rings](Rings). The value(s) passed much match a [.id( )](#id) in your data.

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| tooltip | Whether or not to show the large tooltip on the right side of the visualization relating to the focus element. | *Boolean* | `true` |
| value | The key that gets set when you only pass a value to the method. | *String*, *Number*, *Array*, `false` | `false` |

---

### <a name="font" href="#font">.font( *String* | *Array* | *Object* )</a>

Sets the default overall font family(s) to be used. This method also supports passing a keyed *Object*. Here are the accepted keys:

| Key | Description | Accepted Value(s) | Default Value |
| --- | --- | --- | --- |
| align | Sets the global font alignment. | `"left"`, `"center"`, `"right"` | `"left"` |
| color | Sets the color of all fonts used in the visualization. | *color* | `"#444444"` |
| decoration | Sets the text-decoration of all fonts used in the visualization. | `"line-through"`, `"none"`, `"overline"`, `"underline"` | `"none"` |
| family | Sets the font-family used throughout the entire visualization. Can be a single *String*, *Array*, or comma-separated font-families (like with CSS). | *Array*, *String* | `[ "Helvetica Neue" , "HelveticaNeue" ` `, "Helvetica" , "Arial" , "sans-serif" ]` |
| secondary | Defines a secondary font style (only used in [interface elements](#ui)). | *Object* | Same as primary font style. |
| size | General pixel font size. | *Number* | `12` |
| spacing | General pixel letter spacing. | *Number* | `0` |
| transform | Sets the text-transform of all fonts used in the visualization. | `"capitalize"`, `"lowercase"`, `"none"`, `"uppercase"` | `"none"` |
| weight | Sets the font-weight of all fonts used in the visualization. | *String* or *Number* | `200` |

---

### <a name="footer" href="#footer">.footer( `false` | *String* | *Object* )</a>

Defines footer text to be displayed underneath a visualization (and in large tooltips). To remove the footer, simply pass `false` to the method.

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| font | Defines font styles specific to the footer. The supported [[Font Styles]] are: "align", "color", "decoration", "family", "size", "transform", "weight" | *Object* | Default style |
| link | A URL for the footer to open when clicked. The page will open in a new window/tab. | *String*, `false` | `false` |
| padding | Pixel padding to be given around the footer. | *Number* | `0` |
| position | What side of the visualization the footer should be positioned on. | `"top"`, `"bottom"` | `"bottom"` |
| value | When passing only a *String* or `false` to the method, this is the variable that actually gets set. | *String*, `false` | `false` |

---

### <a name="format" href="#format">.format( *String* | *Function* | *Object* )</a>

Passing a *String* to the method changes the current [locale](Localization) used to display text and numbers. Passing a *Function* overrides the default behavior, which tests whether a value is a *String* or a *Number*, and then passes it through the correct formatting function. It is not recommended that you change this *Function*, but rather edit the specific text and number functions in the object, as seen below when passing an *Object*.

This method also supports passing a keyed *Object*. This is what gives you access to the specific text and number formatting functions. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| affixes | A keyed object of affixes to use when formatting numbers. | *Object* | `{}` |
| locale | When passing only a *String* to the method, this is the variable that actually gets set. | *String* | `"en_US"` |
| number | The function that formats all *Number* values displayed on the screen. <br><br> This is helpful when you would like specific variables to always be formatted a certain way, whether it's to a certain decimal place or replacing commas with periods for international usage. **d3plus** passes 2 variables to the function you provide: the number that needs to be formatted, and the key associated with that number. | *Function* | Custom formatting function. |
| text | The function that formats all *String* values displayed on the screen. <br><br> This is helpful for displaying certain short javascript keys as their full capitalized names, and also enables you to implement full localization for your visualizations. **d3plus** passes 2 variables to the function you provide: the *String* that needs to be formatted, and the key associated with that *String*. | *Function* | Custom formatting function. |
| value | When passing only a *Function* to the method, this is the variable that actually gets set. | *Function* | Custom formatting function. |

Say for instance, you wanted all numbers for the key "year" to return as-is, and all other numbers formatted to 2 decimal places. You would pass the following *Function* to the "number" key:

```js
.format({ "number" : function( number , key ) {

    if (key === "year") {
      return number;
    }
    else {
      return d3.round(number,2);
    }

  }
})
```

In addition, if you wanted to display the key "export_val" as "Export Value" and capitalize all other strings. You would pass the following function to the text key:

```js
.format({ "text" : function( text , key ) {

    if (key === "export_val") {
      return "Export Value";
    }
    else {
      return text.charAt(0).toUpperCase() + text.substr(1).toLowerCase();
    }

  }
})
```

---

### <a name="height" href="#height">.height( *Number* | *Object* )</a>

Sets the height, in pixels, of the current output. This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| max | Sets the max-height of secondary elements, such as the dropdown window in the "drop" Form. | *Number*, `false` | `600` |
| secondary | Sets the height of secondary elements, such as the dropdown window in the "drop" Form. <br><br> If set to `false`, the height will be calculated based on the available space inside of the current window. | *Number*, `false` | `false` |
| small | When the height of a visualization is less than or equal to this *Number*, it will enter "small" mode, where some functionality is disabled. | *Number* | `200` |
| value | When passing only a *Number* to the method, this is the variable that actually gets set. | *Number* | The height of the [.container( )](#container), if defined. Otherwise: `window.innerHeight` |

---

### <a name="history" href="#history">.history( *Boolean* )</a>

Displays a back button in the top left of the visualization when the user has zoomed to a deeper nesting level. Defaults to `true`.

---

### <a name="icon" href="#icon">.icon( *String* | *Function* | *Object* )</a>

Defines the value for a data point's icon URL (shown in [tooltips](#tooltip) and the [legend](#legend)). This is a great example of where you would probably want to pass the icon URL with [.attrs( )](#attrs), as the icon probably does not change throughout time. You can also pass a *Function* as a method of determining the icon URL for a data point. D3plus will pass the *Function* the data point in question, and the function should return the value requested.

This method also supports passing a keyed *Object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| back | Defines the graphic used with nested drop down menus. The *String* can either be an HTML entity or a Font Awesome class. | `false`, *String* | **Font&nbsp;Awesome**:`"fa-angle-left"` <br> **HTML Entity**:`"&#x276e;"`|
| style | Defines the icon style used in tooltips. `"default"` mode just shows the icon as is, while `"knockout"` will assume that the icon is an image with a transparent background, so **d3plus** will fill the background area with the object's current color. <br><br> You can also pass a single keyed *Object*, keyed by the appropriate nesting level's [.id( )](#id), to define different styles for each nesting level. | `"default"`, `"knockout"` | `"default"` |
| value | When passing only a *String* or *Array* to the method, this is the variable that actually gets set. <br><br> You can also pass a single keyed *Object*, keyed by the appropriate nesting level's [.id( )](#id). This will tell **d3plus** to look in that specific nesting level's attribute list for the value. | *String*, *Array*, *Object* | `"icon"` |

---

### <a name="id" href="#id">.id( *String* | *Array* | *Object* )</a>

Defines the accessor key to be used as each data point's unique identifier. This is the key that **d3plus** will use when cross-referencing the data with all sources of data, such as [.attrs( )](#attrs) and [.coords( )](#coords). When passing an *Array* to this method, **d3plus** will use each item in the *Array* as a different level of nesting for the data. For example, if you were using data on cities, you could pass the following array of keys (given these keys are present in your data somewhere):

```js
.id( [ "state" , "county" , "city" ] )
```

In this case, if the current visualization supports nesting, the shapes in the visualization would be nested first by State, then by County, and finally by City. Each *String* in the *Array* has to match a key in one of the defined data methods, usually the main [.data( )](#data).

As with some of the other methods, an *Object* can be passed to this method. Here are the keys accessible by the user:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| grouping | Whether or not the visualization should group shapes based on the supplied nesting. | *Boolean* | `true`
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *Function*, *Array* | `[]` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *Function*, *Array* | `[]` |
| value | Defines the accessor key to be used as each data point's unique identifier. When passing only a *String* or *Array* to this method, this is the variable that actually gets set. | *String*, *Array* | `"id"` |

---

### <a name="labels" href="#labels">.labels( *Boolean* | *Object* )</a>

Defines whether or not visualizations should attempt to label shapes based on [.text( )](#text). Defaults to `true`.

This method also supports passing a keyed *Object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| align | Determines the horizontal text-anchor of the label. | `"left"`, `"center"`, `"right"`, `"start"`, `"middle"`, `"end"` | `"middle"` |
| font | [[Font Styles]] of the labels. Currently supports passing a keyed *Object* with the following keys: "decoration", "family", "size", "transform", "weight". | *Object* | Default style |
| padding | *Number* value of how much pixel padding to allow on all sides of each label. | *Number* | `7` |
| resize | Whether or not labels should be sized to fit the available space. | *Boolean* | `true` |
| text | Overrides the default [.text( )](#text) behavior by provided a different key to use for labels. | `false`, *Function*, *String* | `false` |
| segments | *integer* value to determine how many segments to break an "area" shape into when analyzing positioning. | *integer* | `2` |
| valign | Determines the vertical text-anchor of the label. | `"top"`, `"middle"`, `"bottom"` | `"middle"` |
| value | Defines whether or not labels are visible. When passing only a *Boolean* to the method, this is the variable that actually gets set. | *Boolean* | `true` |

---

### <a name="legend" href="#legend">.legend( *Boolean* | *Object* )</a>

Displays a color legend that helps the user see how colors are associated with shapes. When coloring shapes by *numbers*, the legend will show the appropriate color gradient used. Otherwise, it will show each individual color as a square block with a tooltip that contains information about that category. Defaults to `true`.

This method also supports passing a keyed *Object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| align | Determines the horizontal position of the legend. | `"start"`, `"middle"`, `"end"` | `"middle"` |
| filters | Enables show/hide filters for the groups in the legend tooltips. | *Boolean* | `false` |
| font | [[Font Styles]] for the legend. Currently supports passing a keyed *Object* with the following keys: "align", "color", "family", "size", "weight". | *Object* | Default style |
| gradient | Styling of the gradient used for color scales. Currently supports passing a keyed *Object* with the following keys: "height". | *Object* | `{ "height": 10 }` |
| icons | Whether or not icons should be shown in the legend. | *Boolean* | `true` |
| order | When passed a *String*, this sets the order of the color boxes in the timeline.<br><br>When passed an *Object*, the "sort" value can be set to either "asc" or "desc". | `color`, `id`, `size`, `text`, *Object* | `color` |
| size | *Number* or *Array* of value(s) for the width and height of color blocks. If an *Array*, it should have 2 ordered values, the minimum and maximum. | *Number*, *Array* | `[ 8 , 30 ]` |
| text | Overrides the default [.text( )](#text) behavior by provided a different key to use inside the legend. | `false`, *Function*, *String* | `false` |
| value | Defines whether or not the legend is visible. When passing only a *Boolean* to the method, this is the variable that actually gets set. | *Boolean* | `true` |

---

### <a name="links" href="#links">.links( *Object* )</a>

This method only supports passing a keyed *Object*. Here are the accepted keys:

| Key | Description | Accepted Value(s) | Default Value |
| --- | --- | --- | --- |
| font | Sets the [[Font Styles]] for all hyperlinks. The following values can be set: "color", "decoration", "family", "transform", "weight". | *Object* | Default style |
| hover | Defines font information for when hovering over a link. All of the same values in "font" can be defined. | *Object* | Default style |

---

### <a name="margin" href="#margin">.margin( *Number* | *String* )</a>

Defines the pixel margins, on all sides, of the overall element. You can also pass a standard **CSS** *String* to define the margin. For example, to set the top and bottom margins to `10` and the left and right margins to `20`, you would pass the following:

```js
.margin( "10px 20px" )
```

---

### <a name="messages" href="#messages">.messages( *Boolean* | *String* | *Object* )</a>

Displays status messages, telling the user what is happening behind the scenes as the visualization is being drawn/redrawn. Defaults to `true`. When passed a *String*, the specified *String* will be used for all messages. In this example, we want all messages displayed as `"Loading..."`:

```js
.messages( "Loading..." )
```

This method supports passing a keyed *Object*. Here are the accepted keys:

| Key | Description | Accepted Value(s) | Default Value |
| --- | --- | --- | --- |
| font | Sets information pertaining to the font used to render links. The following values can be set: "color", "decoration", "family", "size", "transform", "weight". | *Object* | Default style |
| padding | The pixel padding around the container. | *Number* | `5` |
| style | Defines the positioning of messages. `"small"` means that the message will be displayed on top of one of the titles/footer. `"large"` means that the message will be dispalyed centered on top of the visualization. If `false`, then the behavior is determined automatically based on what is currently being shown. | `false`, `"small"`, `"large"` | `false` |
| value | The key that gets set when you pass a *String* or *Boolean* to the method. | *String*, *Boolean* | `true` |

---

### <a name="mouse" href="#mouse">.mouse( *Boolean* | *Object* [, *callback*] )</a>

Acts as a global toggle for all mouse events. Defaults to `true`.

By passing a keyed *Object*, it is possible to overwrite individual mouse events, either toggling them off or providing a completely custom function:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| click | If passed a *Boolean*, this will activate or deactivate all click events.<br><br>If passed a *Function*, all default click behavior will be overwritten. The custom *Function* gets passed 2 variable, the data point of the clicked object and the current instance of `d3plus.viz`.  | *Boolean*, *Function* | `true` |
| move | If passed a *Boolean*, this will activate or deactivate all mousemove events.<br><br>If passed a *Function*, all default mousemove behavior will be overwritten. The custom *Function* gets passed 2 variable, the data point of the clicked object and the current instance of `d3plus.viz`.  | *Boolean*, *Function* | `true` |
| out | If passed a *Boolean*, this will activate or deactivate all mouseout events.<br><br>If passed a *Function*, all default mouseout behavior will be overwritten. The custom *Function* gets passed 2 variable, the data point of the clicked object and the current instance of `d3plus.viz`.  | *Boolean*, *Function* | `true` |
| over | If passed a *Boolean*, this will activate or deactivate all mouseover events.<br><br>If passed a *Function*, all default climouseoverck behavior will be overwritten. The custom *Function* gets passed 2 variable, the data point of the clicked object and the current instance of `d3plus.viz`.  | *Boolean*, *Function* | `true` |
| value | The value that gets set when just passing a *Boolean* to this method. | *Boolean* | `true` |

---

### <a name="nodes" href="#nodes">.nodes( *Array* | *url* | *Object* [, *callback*] )</a>

Sets a lookup object that contains "x" and "y" coordinates for each data point to be used in the [[Network]]. The *Array* passed must be in the following format, with each node containing a key/value pair that matches our [.id( )](#id). In this example, our [.id( )](#id) is set to `"city"`.

```js
.nodes([
  {
    "x": 255.3,
    "y": 365.7,
    "city": 1
  },
  {
    "x": 954.2,
    "y": 476.5,
    "city": 2
  }
])
```

When passing a *URL* to this method, **d3plus** will use it to load the data dynamically for you. If a *callback* function is provided, the downloaded data will be passed through the function for formatting (which should then return the correctly formatted data).

This method also supports passing an *Object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| delimiter | The string delimiter used when parsing DSV files from a *url*. | *String* | "&#124;" |
| filetype | The file extension when loading data from a *url*. If set to `false`, **d3plus** will try to auto-detect. | `false`, `"json"`, `"xml"`, `"html"`, `"csv"`, `"dsv"`, `"tsv"`, `"txt"` | `false` |
| overlap | A value, between `0` and `1` which dictates the percentage between the closest nodes that a node's radius shold extent. <br><br>For example, to insure that all nodes never overlap, this value should be set to `0.5`. The default value is slightly higher than this, because when sizing nodes, the 2 closest nodes usually do not share the largest radius. | *Number* | `0.6` |
| value | When passing only an *Array* to this method, this is the variable that actually gets set. | *Array* | `false` |

---

### <a name="order" href="#order">.order( *String* | *Object* )</a>

Sets the value to use when trying to order data points. This method also supports passing a keyed *Object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| agg | The aggregation method used when ordering groups of data (like on a Bar Chart). If `false`, defaults to the normal [.aggs( )](#aggs) method. | `false`, *Function*, `"sum"`, `"min"`, `"max"`, `"mean"`, `"median"` | `false` |
| sort | Changes the sort order of the data between ascending and descending. | `"asc"`, `"desc"` | `"desc"` |
| value | When passing only a *String* to the method, this is the variable that actually gets set. <br><br> You can also pass a single keyed *Object*, keyed by the appropriate nesting level's [.id( )](#id). This will tell **d3plus** to look in that specific nesting level's attribute list for the value. | *String*, *Object*, `false` | `false` |

---

### <a name="shape" href="#shape">.shape( *String* | *Object* )</a>

Sets the shape used to display data. If the shape specified is not supported in the current visualization, **d3plus** will fallback to the primary shape for that visualization.

This method also supports passing an *Object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| interpolate | If the shape supports it, you can change the line interpolation type. This is particularly useful in [[Stacked Area]]. | `"linear"`, `"step"`, `"step-before"`, `"step-after"`, `"basis"`, `"basis-open"`, `"cardinal"`, `"cardinal-open"`, `"monotone"` | `"linear"` |
| rendering | The SVG shape-rendering used on all data shapes. | `"auto"`, `"optimizeSpeed"`, `"crispEdges"`, `"geometricPrecision"` | `"crispEdges"` |
| value | When passing only a *String* to the method, this is the variable that actually gets set. | Defined by the current visualization. | The first defined shape of the visualization. |

---

### <a name="size" href="#size">.size( `false` | *String* | *Number* | *Function* | *Object* )</a>

Defines the value to use when sizing data nodes. If passed a *String*, it should match a key in the data point to a *Number*. If passed a *Number*, it will be used to size all data nodes. You can also pass a function as a way of determining the size of a node. **d3plus** will pass your function the data point in question, and the function should return the value requested.

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *Function*, *Array* | `[]` |
| scale | Determines the scaling of nodes.<br><br>By passing an *Object*, the "min" and "max" pixel values of the size scale can also be accessed. | *Function*, *Object* | `d3.scale.sqrt()` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *Function*, *Array* | `[]` |
| threshold | Whether or not visualizations (if applicable) should automatically group data into an "other" object. | *Boolean*, *Function*, *Number* | `false` |
| value | Defines the key to use when sizing data nodes. When passing only a *String* or *Function* to the method, this is the variable that actually gets set.<br><br>You can also pass a single keyed *Object*, keyed by the appropriate nesting level's [.id( )](#id). This will tell **d3plus** to look in that specific nesting level's attribute list for the value. | *String*, *Number*, *Function*, *Object*, `false` | `false` |

---

### <a name="temp" href="#temp">.temp( *String* | *Function* | *Object* )</a>

Defines the key in your data associated with the number of "temporary" parts. This variable should be used in conjunction with the [Total Segments](#total) method to correctly display fill percentages inside of shapes (such as making each node in a scatter plot a pie chart). You can also pass a function as a method of determining which objects are "temporary". **d3plus** will pass your function the data point in question, and the function should return the value requested.

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *Function*, *Array* | `[]` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *Function*, *Array* | `[]` |
| value | Defines the key in your data associated with the number of "temporary" parts. When passing only a *String*  or *Function* to the this method, this is the variable that actually gets set.<br><br>You can also pass a single keyed *Object*, keyed by the appropriate nesting level's [.id( )](#id). This will tell **d3plus** to look in that specific nesting level's attribute list for the temporary variable. Additionally, if the *Object* you pass tothis method does not contain any of the following keys, **d3plus** will use the *Object* as this key. | *String*, *Function*, *Object*, `false` | `false` |

---

### <a name="text" href="#text">.text( `false` | *String* | *Array* | *Function* | *Object* )</a>

Defines the value used when labeling [shapes](#shape) and [tooltips](#tooltip). When not defined, **d3plus** defaults to using the [.id( )](#id) for all labeling. Passing an *Array* defines a list of value to try to use for labels. If the value of the first key does not fit in the allotted space (like a small square in a [tree map](Tree Map), **d3plus** will then try to fit the next value, and so on. The first value in the *Array* will always be used in [tooltips](#tooltip).

You can also pass a function as a way of determining the text for each node. **d3plus** will pass your function the data point in question, and the function should return the value requested.

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *Function*, *Array* | `[]` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *Function*, *Array* | `[]` |
| value | When passing only a *String* or *Array* to the method, this is the variable that actually gets set. <br><br> You can also pass a single keyed *Object*, keyed by the appropriate nesting level's [.id( )](#id). This will tell **d3plus** to look in that specific nesting level's attribute list for the value. | *String*, *Array*, *Function*, *Object*, `false` | `false` |

---

### <a name="time" href="#time">.time( `false` | *String* | *Function* | *Object* )</a>

Defines the value to be used for slicing the data into different time periods. All values will be parsed into *Javascript Date Objects*, unless they are already in that format. We suggest using time formats specified in the first table on [this page](http://dygraphs.com/date-formats.html). You can also pass a *Function* as a method of determining the time value for a node. **d3plus** will pass your function the data point in question, and the function should return the value requested.

This method also supports passing an *Object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| fixed | When set to `false`, the axes will remain static as you change the time visible (using mute/solo or a [[Timeline]]). <br><br> This makes it easier to see trends over time. If you would like the axes to change as time changes, set this to `true`. | `false`, `true` | `false` |
| format | A [D3 time format](https://github.com/mbostock/d3/wiki/Time-Formatting) function that will override the default behavior of **d3plus**. | `false`, *Array*, *String*, `d3.time.format` | `false` |
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *Function*, *Array* | `[]` |
| solo | Shows only specific data points to the viewer. Useful for only displaying specific time periods of data. Full documentation can be found [here](Data-Filtering#solo). | **value**, *Function*, *Array* | `[]` |
| value | When passing only a *String* or *Function* to the method, this is the variable that actually gets set.<br><br>You can also pass a single keyed *Object*, keyed by the appropriate nesting level's [.id( )](#id). This will tell **d3plus** to look in that specific nesting level's attribute list for the value.  | *String*, *Function*, *Object*, `false` | `false` |

---

### <a name="timeline" href="#timeline">.timeline( *Boolean* | *Object* )</a>

Displays a timeline slider when [.time( )](#time) has been defined.  Defaults to `true`.

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| align | Determines the horizontal position of the timeline. | `"start"`, `"middle"`, `"end"` | `"middle"` |
| hover | The cursor style for when hovering over the handle. | `"all-scroll"`, `"col-resize"`, `"crosshair"`, `"default"`, `"grab"`, `"grabbing"`, `"move"`, `"pointer"` | `"pointer"` |
| handles | Toggles the visibility of the handles on the selected timeline range. <br><br> If passed an object, you can define the following style keys: "color", "hover" (color), "opacity", "size", and "stroke" | *Boolean*, *Object* | `true` |
| height | The pixel height of the timeline. If `false`, the height will be determined automatically based on the height of the text. | `false`, *Number* | `false` |
| tick | The style of each "tick" in between each value on the timeline. | *color* | `"#818181"` |
| value | The key that gets set when only passing a *Boolean* to the method. | *Boolean* | `true` |

---

### <a name="timing" href="#timing">.timing( *Object* )</a>

This method only supports passing a keyed *Object*. Here are the accepted keys:

| Key | Description | Default |
| --- | --- | ---|
| mouseevents | The time, in milliseconds, for hover events. | `60` |
| transitions | The time, in milliseconds, for general movement. | `600` |
| ui | The time, in milliseconds, for UI elements (ex. dropdown open/close). | `200` |

---

### <a name="title" href="#title">.title( `false` | *String* | *Function* | *Object* )</a>

Defines the title of the visualization. **d3plus** will place the supplied *String* above the visualization, wrapping the lines if they are too long to fit. To remove the title, simply pass `false` to the method.

If passed a *Function*, the function will execute on every redraw.

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| font | [[Font Styles]] for the main title. Currently supports passing a keyed *Object* with the following keys: "align", "color", "decoration", "family", "size", "transform", "weight". | *Object* | Default style |
| height | Minimum pixel height for the main title. If `false`, **d3plus** determines the appropriate amount of vertical space automatically. | *Number*, `false` | `false` |
| link | A URL for the title to open when clicked. The page will open in a new window/tab. | *String* | `false` |
| padding | Pixel padding for the main title. If `false`, **d3plus** determines the appropriate amount of vertical space automatically. | *Number* | `2` |
| position | What side of the visualization the title should be positioned on. | `"top"`, `"bottom"` | `"top"` |
| sub | Defines the sub-title of the visualization. This is a smaller title that gets positioned directly under the main title.<br><br>Can be removed by passing `false`. <br><br> Can also be provided the following keys similar to the main title: "font", "padding", "position", "link". | *String*, `false`, *Function*, *Object* | `false` |
| total | Toggles a title line that appears underneath both the main title and sub-title that displays the total value of all of the data currently being shown (using whichever [[Custom Aggregations]] are defined for the current [[Sizing Data]] value). <br><br> Instead of passing `true`, you can pass an *Object* with "prefix" and/or "suffix" keys, whose values will be displayed on either side of the calculated total value. Will be removed by passing `false`. <br><br> Can also be provided the following keys similar to the main title: "font", "padding", "position", "link". | *Boolean*, *Object* | `false` |
| width | Minimum pixel width for the main title. If `false`, **d3plus** determines the appropriate amount of horizontal space automatically. | *Number*, `false` | `false` |
| value | Defines the title of the visualization. When passing only a *String* to the method, this is the variable that actually gets set.<br><br>Can be removed by passing `false`. | *String*, `false` | `false` |

---

### <a name="tooltip" href="#tooltip">.tooltip( *Array* | *Object* )</a>

Defines a list of values to be displayed in the tooltip created for each node. Also has the the ability to accept an *Object* that contains "short" and "long" keys, to define separate *Arrays* for both on hover ("short") and on click ("long") tooltips.

This method also supports passing a keyed object with advanced parameters. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| anchor | The anchor point on the node for the floating tooltip. | Should be defined as two words, the first representing vertically "top", "middle", or "bottom" and the second representing horizontal "left", "center", or "right". | `"top center"` |
| background | The background color for the tooltip. | *color* | `"#ffffff"` |
| children | Whether or not visualization tooltips should include a list of the top 3 nested data objects inside of a shape. | *Boolean* | `true` |
| connections | Whether or not visualization tooltips should include a list of the primary connected nodes, if an [.edges( )](#edges) is defined. | *Boolean* | `true` |
| curtain | Styles for the full page "curtain" that is displayed behind a large tooltip and behind focused elements in zoomable visualizations. Accepted keys are: "color" and "opacity". | *Object* | Default styles |
| extent | Whether or not Box Plot tooltips should display the values of the whiskers. | *Boolean* | `true` |
| font | [[Font Styles]] for the tooltips. Currently supports passing a keyed *Object* with the following keys: "color", "family", "size", "transform", and "weight". | *Object* | Default style |
| html | Defines HTML content to be displayed in a large tooltip underneath the specified tooltip keys. If passed a *Function*, **d3plus** will call the *Function*, passing the current data point to the function, and will expect a *String* in return. <br><br> If passed an *Object* with "url" and "callback" keys, **d3plus** will make a [d3.json](https://github.com/mbostock/d3/Requests#d3_json) request using the "url" provided, and call the "callback" *Function* once data is returned. The "callback" *Function* should then return a valid HTML *String*.| *String*, *Function*, *Object*, `false` | `false` |
| iqr | Whether or not Box Plot tooltips should display the values of the interquartile range. | *Boolean* | `true` |
| large | *Number* width for large tooltips created inside a visualization. | *Number* | `250` |
| share | Whether or not visualization tooltips, when applicable, should show the current shape's share percentage (as in [[Tree Maps|Tree Map]]). | *Boolean* | `true` |
| size | Whether or not visualization tooltips should, when defined, display the current "sizing" value. In most cases, this corresponds to [.size( )](https://github.com/alexandersimoes/d3plus/wiki/Visualizations#size), but in the case of a Geo Map is corresponds to [.color( )](https://github.com/alexandersimoes/d3plus/wiki/Visualizations#color).  | *Boolean* | `true` |
| small | *Number* width for small tooltips created inside a visualization. | *Number* | `200` |
| sub | A key in the data to use as the sub-title for all tooltips. | `false`, *String* | `false` |
| value | When passing only an *Array* or an *Object* with either "short" and "long" keys or nesting levels, this is the value that gets set. | *Array*, *Object*, `false` | `false` |

---

### <a name="total" href="#total">.total( *String* | *Function* | *Object* )</a>

Defines the key in your data associated with the total number of parts of a data point. This variable should be used in conjunction with the [Active Segments](#active) method and/or the [Temporary Segments](#temp) method to correctly display fill percentages inside of shapes (such as making data nodes in a [[Scatter Plot]] appear as pie charts). You can also pass a function as a method of determining the total number of parts of a data point. **d3plus** will pass your function the data point in question, and the function should return the value requested.

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *Function*, *Array* | `[]` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *Function*, *Array* | `[]` |
| value | Defines the key in your data associated with the total number of parts of a data point. When passing only a *String* or *Function* to this method, this is the variable that actually gets set.<br><br>You can also pass a single keyed *Object*, keyed by the appropriate nesting level's [.id( )](#id). This will tell **d3plus** to look in that specific nesting level's attribute list for the total variable. Additionally, if the *Object* you pass to this method does not contain any of the following keys, **d3plus** will use the *Object* as this key. | *String*, *Function*, *Object*, `false` | `false` |

---

### <a name="type" href="#type">.type( *String* | *Object* )</a>

Sets the current visualization type. This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mode | Sets the "mode" for the current visualization, if supported | Depends on the visualization. | First defined value in the visualization's list. |
| value | What actually gets set when you only pass a *String* to the method. | Any supported visualization type ([see top of page](#)) | `"tree_map"` |

---

### <a name="ui" href="#ui">.ui( `false` | *Array* | *Object* )</a>

Creates UI elements, using [d3plus forms](Forms), that help the modify behavior of the visualization. The *Array* of objects passed should contain methods and values, which correspond to how the UI element should behave. For example, if you wanted to create a toggle that switches the "size" method from "export" to "import", you would pass the following:

```js
.ui([{"method": "size", "value": [ "export" , "import" ]}])
```

The UI can be removed by passing `false`. This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| align | Sets the horizontal alignment of the UI elements. | `"left"`, `"center"`, `"right"` | `"center"` |
| border | Pixel border for all UI elements. | *Number* | `1` |
| color | Object that sets the "primary" and "secondary" UI colors. <br><br> When only setting a "primary" color, the "secondary" is automatically calculated based on the "primary". | *Object* | Default style |
| display | The display behavior of the UI elements. | `"block"`, `"inline-block"` | `"inline-block"` |
| font | [[Font Styles]] for the UI elements. Currently supports passing a keyed *Object* with the following keys: "align", "color", "decoration", "family", "size", "transform", and "weight". | *Object* | Default style |
| margin | Pixel margin for all UI elements. | *Number* | `5` |
| padding | Pixel padding for all UI elements. | *Number* | `5` |
| position | The position of the container for all UI elements. | `"top"` , `"right"` , `"bottom"` , `"left"` | `"bottom"` |
| value | When passing only an *Array* to the method, this is the variable that actually gets set. | *Array*, `false` | `false` |

---

### <a name="width" href="#width">.width( *Number* | *Object* )</a>

Sets the width, in pixels, of the current output. This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| secondary | Sets the width of secondary elements, such as the dropdown window in the "drop" Form. <br><br> If set to `false`, the width will be calculated based on the width of the primary element. | *Number*, `false` | `false` |
| small | When the width of a visualization is less than or equal to this *Number*, it will enter "small" mode, where some functionality is disabled. | *Number* | `200` |
| value | When passing only a *Number* to the method, this is the variable that actually gets set. | *Number* | The width of the [.container( )](#container), if defined. Otherwise: `window.innerWidth` |

---

### <a name="x" href="#x">.x( `false` | *String* | *Function* | *Object* )</a>

Defines the value in your data to be associated with the axis in visualizations that use an X/Y plot. You can also pass a *Function* as a way of determining the axis value. **d3plus** will pass your function the data point in question, and the function should return the value requested.

This method also supports passing a keyed *Object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| axis | Toggles on/off the grid line for the zeroline. Additional object parameters for styling are: "color", "font", and "rendering". | *Boolean*, *Object* | `true` |
| domain | Defines the domain to be used when drawing the axis. If passed `false`, **d3plus** will calculate the domain based on the data available (which it does by default). | *Array*, `false` | `false` |
| grid | Toggles on/off the grid lines for this specific axis. Additional object parameters for styling are: "color" and "rendering". | *Boolean*, *Object* | `true` |
| label | Overrides the default axis label text. Additional object parameters for styling are: "color", "decoration", "family", "padding", "size", "transform", and "weight". | *Boolean*, *String*, *Object* | `true` |
| lines | Will plot the values passed as static lines on the axis. If the value is a single keyed *Object*, **d3plus** will use the key as a label for the line and the value as the position. <br><br> In addition to passing values, various parameters can be set by using a specific keyed object. Here are the available keys: "dasharray", "color", "font", "rendering", "width". | *Number*, *Object*, or *Array* of values | `false` |
| mouse | Styles for the lines that eminant out of a data node and point to the values on each axis, for visualizations that support it. Here are the accepted keys: "dasharray", "rendering", and "width". <br><br>Can also be toggled using a *Boolean* value. | *Boolean*, *Object* | `true` |
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *Function*, *Array* | `false` |
| padding | Defines the padding between grouped data for the specific axis. For example, this number is used in Bar Charts to define the space between each group of bars. If the number is less than `1`, it is used as a percentage of the available space. If it is larger than `1`, it is used as a set pixel value (unless there is not enough space, then it reverts to the default). | *Number* | `0.1`
| range | Sets a static range of values to be used for the axis. | `false`, *Array* | `false` |
| scale | Defines the scale to use when plotting points on the axis. <br><br> A `"discrete"` scale will assume each value is unique, and will create a tick for each instance of that value (for example, when using [[Time Parameters]]). <br><br> A `"share"` scale will plot values as percentages out of all of the available values. | `"linear"`, `"log"`, `"discrete"`, `"share"` | `"linear"` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo).|**value**, *Function*, *Array* | `false` |
| stacked | Determines whether or not axis values should be stacked on top of each other. | *Boolean* | `false` |
| ticks | Style properties for the axis ticks. Accepted keys are: "color", "font", "rendering", "size", and "width". | *Object* | Default style. |
| value | When passing only a *String* or *Function* to the method, this is the variable that actually gets set. <br><br> You can also pass a single keyed *Object*, keyed by the appropriate nesting level's [.id( )](#id). This will tell **d3plus** to look in that specific nesting level's attribute list for the value.  | *String*, *Function*, *Object*, `false` | `false` |
| zerofill | If scale is `"discrete"`, this determines whether or not **d3plus** should fill gaps in the axis with `0` values. | *Boolean* | `false` |

---

### <a name="y" href="#y">.y( `false` | *String* | *Function* | *Object* )</a>

Contains all of the same properties and behavior as [.x( )](#x).

---

### <a name="zoom" href="#zoom">.zoom( *Boolean* | *Object* )</a>

Enables/disables visualization zooming. This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| click | Toggles the ability to double-click and right-click to zoom in/out. | *Boolean* | `true` |
| pan | Toggles the ability to pan the visualization while zoomed in. | *Boolean* | `true` |
| scroll | Toggles the ability zoom in/out using a mouse scrollwheel/trackpad. | *Boolean* | `true` |
| value | When passing only a *Boolean* to the .**zoom**() function, this is the variable that actually gets set. | *Boolean* | `true` |