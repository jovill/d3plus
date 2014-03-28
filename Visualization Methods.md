The visualizations in **D3plus** have numerous methods for you to tweak in order to get the perfect visualization that suits your needs. Some methods are specific for only one visualization type, while other are used across multiple visualizations.

If you call any of the following methods without passing any variables you will be returned an object with the current method's settings.

***

<a name="active" href="#wiki-active">#</a> viz.**active**(*string*)

Defines the key in your data associated with the number of "active" parts. This variable should be used in conjunction with [.**total**()](#total") to correctly display fill percentages inside of shapes (such as making each node in a scatter plot a pie chart).

<a name="active-func" href="#wiki-active-func">#</a> viz.**active**(*function*)

You can also pass a function as a method of determining which objects are "active". D3plus will pass your function the data point in question, and the function should return the value requested.

<a name="active-obj" href="#wiki-active-obj">#</a> viz.**active**(*object*)

.**active**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|key|Defines the key in your data associated with the number of "active" parts. When passing only a *string* or *function* to the .**active**() function, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [.**id**()](#id). This will tell **D3plus** to look in that specific nesting level's attribute list for the .**active**() variable. Additionally, if the *object* you pass to .**active**() does not contain any of the following keys, **D3plus** will use the *object* as this key.|*string*, *function*, *object*, <code>**null**</code>, <code>**false**</code>|<code>**null**</code>|
|mute|Hides specific data points from the viewer. Full documentation can be found [here](Filtering-Data#mute).|**value**, *function*, *array*|<code>**null**</code>|
|solo|Shows only specific data points to the viewer. Full documentation can be found [here](Filtering-Data#solo).|**value**, *function*, *array*|<code>**null**</code>|
|spotlight|Determines the behavior of inactive nodes, based on how the current [Visualization Type](Visualization-Types) handles it. For example, when .**spotlight**() is set to <code>**true**</code> for a [Network](Visualization-Types#wiki-network), all of the "inactive" nodes will be greyed out, giving more emphasis on the "active" nodes.|<code>**true**</code>, <code>**false**</code>|<code>**false**</code>|

***

<a name="aggs" href="#wiki-aggs">#</a> viz.**aggs**({"key": *string*, ... })

Defines how specific key values should be aggregated when the visualization nests or groups your data. The *string* value passed with each key needs to be one of D3's predefined [array comparators](https://github.com/mbostock/d3/Arrays#wiki-d3_min), such as "mean", "median", "min", or "max". By default, all keys use [d3.sum()](https://github.com/mbostock/d3/Arrays#wiki-d3_sum).

<a name="aggs-func" href="#wiki-aggs-func">#</a> viz.**aggs**({"key": *function*, ... })

You can also pass a *function* as an aggregation method for a key. D3plus will pass the *function* the array of data objects needing aggregation, and the *function* should return the final aggregated value.

***

<a name="axes" href="#wiki-axes">#</a> viz.**axes**(*object*)

Defines specific parameters for visualizations that use X and Y axes. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|mirror|Tells the visualization to use the same range for both axes. D3plus will calculate both axes' domains, and then combine them into a final matched domain.|<code>**true**</code>, <code>**false**</code>|<code>**false**</code>|

***

<a name="attrs" href="#wiki-attrs">#</a> viz.**attrs**(*array*)

Defines a set of data points that are associated with the primary data, but that do not change as the data changes. For example, this could include colors and names that are static throughout all time while your primary data includes values that change over time.

The [.**id**()](#wiki-id) key that you set **MUST** be present inside of your attribute array, otherwise **D3plus** will have no way of matching attributes to data.

<a name="attrs-obj" href="#wiki-attrs-obj">#</a> viz.**attrs**(*object*)

If it suits your needs, you may also pass .**attrs**() an object keyed by [.**id**()](#wiki-id).

<a name="attrs-key" href="#wiki-attrs-key">#</a> viz.**attrs**({"key": *array*, ... })

If your visualization uses nesting, you may want to pass a different attribute list for each nesting level. This can be achieved by passing .**attrs**() an object that is keyed based on the keys supplied to [.**id**()](#wiki-id) for each nesting level.

<a name="attrs-key2" href="#wiki-attrs-key2">#</a> viz.**attrs**({"key": *object*, ... })

As with un-nested attribute data, you can also pass keyed objects for each level's attribute list.

***

<a name="color" href="#wiki-color">#</a> viz.**color**(*string*)

Defines the key in your data associated with the color of each node. If the key returns a hexadecimal color, **D3plus** will simply use that as the node's color. If it returns a *sting*, a random color based on that string will be used. Finally, if the key returns a *number*, **D3plus** will map the values to a heat map.

<a name="color-func" href="#wiki-color-func">#</a> viz.**color**(*function*)

You can also pass a function as a method of determining the color of a node. D3plus will pass your function the data point in question, and the function should return the value requested.

<a name="color-obj" href="#wiki-color-obj">#</a> viz.**color**(*object*)

.**color**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|key|Defines the key in your data associated with the color of each node. When passing only a *string* or *function* to the .**color**() function, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [.**id**()](#id). This will tell **D3plus** to look in that specific nesting level's attribute list for the .**color**() variable. Additionally, if the *object* you pass to .**color**() does not contain any of the following keys, **D3plus** will use the *object* as this key.|*string*, *function*, *object*, <code>**null**</code>, <code>**false**</code>|<code>**null**</code>|
|mute|Hides specific data points from the viewer. Full documentation can be found [here](Filtering-Data#mute).|**value**, *function*, *array*|<code>**null**</code>|
|solo|Shows only specific data points to the viewer. Full documentation can be found [here](Filtering-Data#solo).|**value**, *function*, *array*|<code>**null**</code>|

***

<a name="container" href="#wiki-container">#</a> viz.**container**(*selector*)

Tells **D3plus** which page element to build the visualization inside of. This is a required method for every visualization. We support all of the [D3 Selection Methods](https://github.com/mbostock/d3/Selections#selecting-elements). For examples, to select an element with the ID of "box", you would say:

```js
viz.container("#box")
```

Before creating a visualization, **D3plus** will remove all contents of the specified container element.

***

<a name="coords" href="#wiki-coords">#</a> viz.**coords**(*topojson*)

For visualizations that use geography, you can pass a [Topojson](https://github.com/mbostock/topojson) object to **D3plus**. Each feature inside of your topojson must have an "id" value that matches the [.**id**()](#wiki-id) used in your data.

<a name="coords-obj" href="#wiki-coords-obj">#</a> viz.**coords**(*object*)

.**coords**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|center|The position, in coordinate degrees, of the center of the map projection.|*array*|<code>[0,0]</code>|
|fit|Determines how coordinate bounds will be positioned within the dimensions of the visualization.|<code>"auto"</code>, <code>"width"</code>, <code>"height"</code>|<code>"auto"</code>|
|mute|Hides specific coordinate objects from the viewer. Full documentation can be found [here](Filtering-Data#mute).|**value**, *function*, *array*|<code>**null**</code>|
|padding|How many pixels of padding should be applied to the bounds of a zoomed object.|*number*|<code>20</code>|
|projection|Which geographical projection should be used.|<code>"equirectangular"</code>, <code>"mercator"</code>|<code>"mercator"</code>|
|solo|Shows only specific coordinate objects to the viewer. Full documentation can be found [here](Filtering-Data#solo).|**value**, *function*, *array*|<code>**null**</code>|
|threshold|The minimum area required to be displayed.|*number*|<code>0.1</code>|
|value|The [Topojson](https://github.com/mbostock/topojson) *object* that gets set when just passing *topojson* to .**coords**().|*topojson*|<code>**null**</code>|

***

<a name="csv" href="#wiki-csv">#</a> viz.**csv**()

Downloads a .csv file of the currently displayed data to the user's computer. If a [.**title**()](#title) is defined, it will use that for the title (replacing spaces with hyphens). Otherwise, the file will be called "My-D3plus-App-Data.csv".

A javascript version of the data (an *array* of *arrays*) is also returned to javascript when this method is called.

<a name="csv" href="#wiki-csv">#</a> viz.**csv**(*array*)

If an *array* of keys is passed to .**csv**(), **D3plus** will return a .csv file with only those specified keys present.

***

<a name="data" href="#wiki-data">#</a> viz.**data**(*array*)

Sets the data associated with your visualization.

<a name="data-obj" href="#wiki-data-obj">#</a> viz.**data**(*object*)

.**data**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|large|If the number of data nodes drawn on the screen exceeds this number, all transitions animations will be disabled. This is prevents lag and stuttering with large datasets.|*integer*|<code>**400**</code>|
|value|When passing only an *array* to the .**data**() function, this is the variable that actually gets set.|*array*|<code>[]</code>|

***

<a name="depth" href="#wiki-depth">#</a> viz.**depth**(*integer*)

If you have specified nesting with [.**id**()](#wiki-id), then this method allows you to switch between those nesting levels. .**depth**() accepts integer values that match the desired position in the nesting array.

***

<a name="descs" href="#wiki-descs">#</a> viz.**descs**({"key": *string*, ... })

Sets tooltip descriptions for specified keys. These descriptions become visible on hover.

***

<a name="dev" href="#wiki-dev">#</a> viz.**dev**(*boolean*)

Toggles development mode, which displays verbose comments in the browser's console. It can be helpful to see what the visualization is doing when you get an error message. Defaults to <code>false</code>.

***

<a name="draw" href="#wiki-draw">#</a> viz.**draw**()

Draws the visualization inside of the specified [.**container**()](#container). When the visualization gets drawn for the first time, or if the [.**container**()](#container) has changed, .**draw**() will remove all previous contents of the [.**container**()](#container).

.**draw**() should to be called after updating any other method in order to update the visualization.

Where our [.**container**()](#container) has an id of "container", and our instance of d3plus.viz() is called "visualization", .**draw**() would the equivalent of saying:

```js
d3.select("#container").call(visualization)
```

***

<a name="edges" href="#wiki-edges">#</a> viz.**edges**(*array*)

Sets the list of edges between objects for visualizations that require edges (such as [Network](Visualization-Types#network) and [Rings](Visualization-Types#rings)). The *array* passed to .**edges**() must be in the following format, with the "source" and "target" keys matching the key used for [.**id**()](#id).

```js
[
	{
		"source": 1,
		"target": 2
	},
	{
		"source": 3,
		"target": 1
	},

	...

]
```

<a name="edges-obj" href="#wiki-edges-obj">#</a> viz.**edges**(*object*)

When passing an object to .**edges**(), you have access to additional constraints of the edges. Here are the variables available to modify:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|arrows|Determines whether or not arrows should be drawn at the end of each link.<br><br>When passing a *boolean*, the arrows will be toggled on/off with a default width of <code>**10**</code> pixels.<br><br>When passing a *number*, that number will be used as the width of the arrow.<br><br>When passing an *object*, the user can define both the "value" (which is what gets set when not passing an *object*) and the "direction" of the arrows, which is either "source" or "target" (defaults to "target).")|*boolean*, *number*, *object*|<code>**false**</code>|
|label|Key within each link object to be used to label the connection.|*string*|<code>**false**</code>|
|large|The cutoff for a "large" network. When there are more than this number of edges displayed on screen, certain transitions and styles will be disabled because it becomes too computationally heavy to modify the large amount of edges on the fly (for example, when highlighting specific connections on hover).|*integer*|<code>**100**</code>|
|limit|Limits the number of primary connections to be shown.|*integer*, <code>**null**</code>|<code>**null**</code>|
|source|Sets the key associated with the edge "source".|*string*|<code>"source"</code>|
|target|Sets the key associated with the edge "target".|*string*|<code>"target"</code>|
|value|Sets the list of edges to use. When passing only an *array* to the .**link**() function, this is the variable that actually gets set.|*array*|<code>**null**</code>|

***

<a name="error" href="#wiki-error">#</a> viz.**error**(*string*)

Sets an error message to override the visualization. This halts the visualization and displays your message instead.

***

<a name="focus" href="#wiki-focus">#</a> viz.**focus**(**value**)

If the visualization supports it, this defines which data node to focus on. For example, this) sets the center node in [Rings](Visualization-Types#wiki-rings). The **value** passed to .**focus**() much match an id in your data.

<a name="focus-obj" href="#wiki-focus-obj">#</a> viz.**focus**(*object*)

When passing an object to .**focus**(), you have access to additional constraints. Here are the variables available to modify:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|tooltip|Whether or not to show the large tooltip on the right side of the visualization relating to the focus element.|*boolean*|<code>**true**</code>|
|value|The key that gets set when you only pass a *value* to .**focus**().|*value*|<code>**null**</code>|

***

<a name="footer" href="#wiki-footer">#</a> viz.**footer**(*string*)

Defines footer text to be displayed underneath the visualization (and in large tooltips). The string passed can have an HTML anchor tag within it, and the link will be displayed properly.

To remove the footer, simply pass <code>**false**</code> or <code>**null**</code> to .**footer**().

<a name="footer-obj" href="#wiki-footer-obj">#</a> viz.**footer**(*object*)

.**footer**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|link|A URL for the footer to open when clicked. The page will open in a new window/tab.|*string*|<code>**null**</code>|
|value|When passing only a *string* to the .**footer**() function, this is the variable that actually gets set.|*string*|<code>**false**</code>|

***

<a name="height" href="#wiki-height">#</a> viz.**height**(*number*)

Sets the height, in pixels, of the current visualization.

<a name="height-obj" href="#wiki-height-obj">#</a> viz.**height**(*object*)

.**height**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|small|When the height of the visualization is less than or equal to this *number*, it will enter "small" mode, where some functionality (such as tooltips) is disabled.|*number*|<code>**250**</code>|
|value|When passing only a *number* to the .**height**() function, this is the variable that actually gets set.|*number*|The height of the [.**container**()](#container), if defined. Otherwise, <code>window.innerHeight</code>|

***

<a name="history" href="#wiki-history">#</a> viz.**history**(*boolean*)

Displays a back button in the top left of the visualization when the user has zoomed to a deeper nesting level. Defaults to <code>**true**</code>.

***

<a name="html" href="#wiki-html">#</a> viz.**html**(*string*)

Defines HTML content to be displayed in a large tooltip underneath the specified tooltip keys. Can be removed by passing either <code>**false**</code> or <code>**null**</code>.

<a name="html-func" href="#wiki-html-func">#</a> viz.**html**(*function*)

If passed a *function*, **D3plus** will call the *function*, passing the current data point to the function, and will expect a *string* in return.

<a name="html-obj" href="#wiki-html-obj">#</a> viz.**html**(*object*)

If passed an *object* with "url" and "callback" keys, **D3plus** will make a [d3.json](https://github.com/mbostock/d3/Requests#wiki-d3_json) request using the "url" provided, and call the "callback" *function* once data is returned. The "callback" *function* should then return a valid HTML *string*.

***

<a name="icon" href="#wiki-icon">#</a> viz.**icon**(*string*)

Defines the accessor key for a data point's icon to be shown in tooltips. **D3plus** will search both the data and the attributes when trying to locate a node's icon, and this is a great example of where you would probably want to pass the icon URL with attributes rather than data, as the icon probably does not change throughout time.

<a name="icon-func" href="#wiki-icon-func">#</a> viz.**icon**(*function*)

You can also pass a function as a method of determining the icon URL for a data point. D3plus will pass your function the data point in question, and the function should return the value requested.

<a name="icon-obj" href="#wiki-icon-obj">#</a> viz.**icon**(*object*)

As with some of the other methods, an *object* can be passed to .**icon**(). Here are the keys accessible by the user:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|key|When passing only a *string* or *array* to the .**icon**() function, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [.**id**()](#id). This will tell **D3plus** to look in that specific nesting level's attribute list for the .**icon**() variable.|*string*, *array*, *object*|<code>"icon"</code>|
|style|Defines the icon style used in tooltips. <code>"default"</code> mode just shows the icon as is, while <code>"knockout"</code> will assume that the icon is an image with a transparent background, so **D3plus** will fill the background area with the object's current color.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [.**id**()](#id), to define different styles for each nesting level.|<code>"default"</code>, <code>"knockout"</code>|<code>"default"</code>|

***

<a name="id" href="#wiki-id">#</a> viz.**id**(*string*)

Defines the accessor key to be used as each data point's unique identifier. This is the key that **D3plus** will use when cross-referencing the data with other sources for data, including the data passed to [.**attrs**()](#attrs) and the ids of the TopoJSON passed to [.**coords**()](#coords).

<a name="id-arr" href="#wiki-id-arr">#</a> viz.**id**(*array*)

When passing an *array* of *strings* to .**id**(), **D3plus** will use each *string* in the *array* as a different level of nesting for the data. For example, if you were using data on cities, you could pass .**id**() the following array of keys:

```js
["state","county","city"]
```

In this case, if the current visualization supports nesting, the shapes in the visualization would be nested first by State, then by County, and finally by City. Each *string* in the *array* has to match a key in either the .**data**() or the .**attrs**().

<a name="id-obj" href="#wiki-id-obj">#</a> viz.**id**(*object*)

As with some of the other methods, an *object* can be passed to .**id**(). Here are the keys accessible by the user:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|key|Defines the accessor key to be used as each data point's unique identifier. When passing only a *string* or *array* to the .**id**() function, this is the variable that actually gets set.|*string*, *array*|<code>"id"</code>|
|mute|Hides specific data points from the viewer. Full documentation can be found [here](Filtering-Data#mute).|**value**, *function*, *array*|<code>**null**</code>|
|solo|Shows only specific data points to the viewer. Full documentation can be found [here](Filtering-Data#solo).|**value**, *function*, *array*|<code>**null**</code>|

***

<a name="labels" href="#wiki-labels">#</a> viz.**labels**(*boolean*)

Defines whether or not visualizations should attempt to label nodes based on the current [.**text**()](#text) variables. Defaults to <code>**true**</code>.

***

<a name="legend" href="#wiki-legend">#</a> viz.**legend**(*boolean*)

Displays a color legend that helps the user see how colors are associated with shapes. When coloring shapes by *numbers*, the legend will show the appropriate color gradient used. Otherwise, it will show each individual color used as a block with a tooltip that contains information about that category. Defaults to <code>**true**</code>.

<a name="legend-obj" href="#wiki-legend-obj">#</a> viz.**legend**(*object*)

As with some of the other methods, an *object* can be passed to .**legend**(). Here are the keys accessible by the user:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|order|When passed a *string*, this sets the order of the color boxes in the timeline.<br><br>When passed an *object*, the "sort" key can be set to either "sac" or "desc".|<code>"alpha"</code>, <code>"color"</code>, *object*|<code>"color"</code>|
|value|Defines whether or not the legend is visible. When passing only a *boolean* to the .**legend**() function, this is the variable that actually gets set.|*boolean*|<code>**true**</code>|

***

<a name="messages" href="#wiki-messages">#</a> viz.**messages**(*boolean*)

Displays status messages, telling the user what is happening behind the scenes as the visualization is being drawn/redrawn. Defaults to <code>**true**</code>.

***

<a name="nodes" href="#wiki-nodes">#</a> viz.**nodes**(*array*)

For visualizations that require static positioning of nodes (such as the [Network](Visualization-Types#network)), you need to pass a lookup object that contains "x" and "y" coordinates for each data point. The *array* passed to .**nodes**() must be in the following format, with each node containing a key that matches it to the key used for [.**id**()](#id). In this example, our [.**id**()](#id) is set to "city".

```js
[
	{
		"x": 255.3,
		"y": 365.7,
		"city": 1
	},
	{
		"x": 954.2,
		"y": 476.5,
		"city": 2
	},

	...

]
```

***

<a name="number_format" href="#wiki-number_format">#</a> viz.**number_format**(*function*)

Defines a function to use when formatting all *integers* and *floats* for displaying on screen. This is helpful when you would like specific variables to always be formatted a certain way, whether it's to a certain decimal place or replacing commas with periods for international usage. **D3plus** passes 2 variables to the function you provide: the number that needs to be formatted, and the key associated with that number. Say for instance, you wanted all numbers for the key "year" to return normal and all other numbers should be formatted to 2 decimal places, this would be your function:

```js
function format(number,key) {

	if (key == "year") {
		return number;
	}
	else {
		return d3.round(number,2);
	}

}
```

***

<a name="order" href="#wiki-order">#</a> viz.**order**(*function*)

Sets the key to use when trying to order shapes, such as in a [Stacked Area Chart](Visualization-Types#stacked).

<a name="order-obj" href="#wiki-order-obj">#</a> viz.**order**(*object*)

When passing an object to .**order**(), you have access to an additional constraint of the ordering. Here are the variables available to modify:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|key|Sets the key to use when trying to order shapes. When passing only a *string* to the .**order**() function, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [.**id**()](#id). This will tell **D3plus** to look in that specific nesting level's attribute list for the .**order**() variable. Additionally, if the *object* you pass to .**order**() does not contain any of the following keys, **D3plus** will use the *object* as this key.|*string*, *object*|<code>**null**</code>|
|sort|Changes the sort order of the shapes between ascending and descending.|<code>"asc"</code>, <code>"desc"</code>|<code>"asc"</code>|

***

<a name="shape" href="#wiki-shape">#</a> viz.**shape**(*string*)

Sets the shape used to display data. If the shape specified is not supported in the current visualization, **D3plus** will fallback to the primary shape for that visualization (and display some helpful messages in the browser console).

<a name="shape-obj" href="#wiki-shape-obj">#</a> viz.**shape**(*object*)

An *object* can also be passed to .**shape**(). Here are the accepted parameters:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|key|Sets the shape used to display data. When passing only a *string* to the .**shape**() function, this is the variable that actually gets set.|<code>"circle"</code>, <code>"donut"</code>, <code>"line"</code>, <code>"square"</code>, <code>"area"</code>, <code>"coordinates"</code>|The primary shape of the initial visualization.|
|interpolate|If the shape supports it, you can change the line interpolation type. This is particularly useful in [Stacked Area Charts](Visualization-Types#stacked).|<code>"linear"</code>, <code>"step"</code>, <code>"step-before"</code>, <code>"step-after"</code>, <code>"basis"</code>, <code>"basis-open"</code>, <code>"cardinal"</code>, <code>"cardinal-open"</code>, <code>"monotone"</code>|<code>"linear"</code>|

***

<a name="size" href="#wiki-size">#</a> viz.**size**(*string*)

Defines the key to use when sizing data nodes. The key's value should always be a *float* or *integer*.

<a name="size-func" href="#wiki-size-func">#</a> viz.**size**(*function*)

You can also pass a function as a method of determining the size variable. D3plus will pass your function the data point in question, and the function should return the value requested.

<a name="size-obj" href="#wiki-size-obj">#</a> viz.**size**(*object*)

.**size**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|key|Defines the key to use when sizing data nodes. When passing only a *string* or *function* to the .**size**() function, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [.**id**()](#id). This will tell **D3plus** to look in that specific nesting level's attribute list for the .**size**() variable. Additionally, if the *object* you pass to .**size**() does not contain any of the following keys, **D3plus** will use the *object* as this key.|*string*, *function*, *object*, <code>**null**</code>, <code>**false**</code>|<code>**null**</code>|
|mute|Hides specific data points from the viewer. Full documentation can be found [here](Filtering-Data#mute).|**value**, *function*, *array*|<code>**null**</code>|
|solo|Shows only specific data points to the viewer. Full documentation can be found [here](Filtering-Data#solo).|**value**, *function*, *array*|<code>**null**</code>|
|threshold|Whether or not visualizations (if applicable) should automatically group data into an "other" object. This is especially helpful in [Stacked](Visualization-Types#wiki-stacked) when there is a lot of thin data slices.|*boolean*|<code>**true**</code>|

***

<a name="style" href="#wiki-style">#</a> viz.**style**(*string*)

Sets the overall visual style of your visualization to the specified style. [Click here](Styles-Sheets) for a list of all of the styles included with **D3plus**.

<a name="style-obj" href="#wiki-style-obj">#</a> viz.**style**(*object*)

Additionally, specific elements of the current style can be modified on the fly by passing a keyed object with the style elements you would like to change. For example, to change the font family of your visualization named "viz" to "Helvetica", you would call this:

```js
viz.style({"font": "family": "Helvetica"});
```

[Click here](Style-Parameters) for the full list of style parameters.

***

<a name="temp" href="#wiki-temp">#</a> viz.**temp**(*string*)

Defines the key in your data associated with the number of "temporary" parts. This variable should be used in conjunction with [.**total**()](#total") to correctly display fill percentages inside of shapes (such as making each node in a scatter plot a pie chart).

<a name="temp-func" href="#wiki-temp-func">#</a> viz.**temp**(*function*)

You can also pass a function as a method of determining which objects are "temporary". D3plus will pass your function the data point in question, and the function should return the value requested.

<a name="temp-obj" href="#wiki-temp-obj">#</a> viz.**temp**(*object*)

.**temp**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|key|Defines the key in your data associated with the number of "temporary" parts. When passing only a *string*  or *function*to the .**temp**() function, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [.**id**()](#id). This will tell **D3plus** to look in that specific nesting level's attribute list for the .**temp**() variable. Additionally, if the *object* you pass to .**temp**() does not contain any of the following keys, **D3plus** will use the *object* as this key.|*string*, *function*, *object*, <code>**null**</code>, <code>**false**</code>|<code>**null**</code>|
|mute|Hides specific data points from the viewer. Full documentation can be found [here](Filtering-Data#mute).|**value**, *function*, *array*|<code>**null**</code>|
|solo|Shows only specific data points to the viewer. Full documentation can be found [here](Filtering-Data#solo).|**value**, *function*, *array*|<code>**null**</code>|

***

<a name="text" href="#wiki-text">#</a> viz.**text**(*string*)

Defines the key to be used for labeling shapes and titling tooltips. Without defining the .**text**() key, **D3plus** defaults to using the [.**id**()](#id) key for labeling shapes and tooltips.

<a name="text" href="#wiki-text">#</a> viz.**text**(*array*)

Defines a list of keys to use when trying to label a shape. For example, if the value of the first key does not fit in the allotted space (like a small square in a [Tree Map](Visualization-Types#tree_map)), **D3plus** will then try to fit the value of the second key, and so on. The value of the first key of the *array* will always be the node's tooltip title.

<a name="text-func" href="#wiki-text-func">#</a> viz.**text**(*function*)

You can also pass a function as a method of determining the text for a node. D3plus will pass your function the data point in question, and the function should return the value requested.

<a name="text-obj" href="#wiki-text-obj">#</a> viz.**text**(*object*)

.**text**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|key|Defines the key to be used for labeling shapes and titling tooltips. When passing only a *string* or *array* to the .**text**() function, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [.**id**()](#id). This will tell **D3plus** to look in that specific nesting level's attribute list for the .**text**() variable. Additionally, if the *object* you pass to .**text**() does not contain any of the following keys, **D3plus** will use the *object* as this key.|*string*, *array*, *function*, *object*, <code>**null**</code>, <code>**false**</code>|<code>**null**</code>|
|mute|Hides specific data points from the viewer. Full documentation can be found [here](Filtering-Data#mute).|**value**, *function*, *array*|<code>**null**</code>|
|solo|Shows only specific data points to the viewer. Full documentation can be found [here](Filtering-Data#solo).|**value**, *function*, *array*|<code>**null**</code>|

***

<a name="text_format" href="#wiki-text_format">#</a> viz.**text_format**(*function*)

Defines a function to use when formatting all *strings* for displaying on screen. This is helpful for displaying certain short javascript keys as their full capitalized names, and also enables you to implement full localization for your visualizations. **D3plus** passes 2 variables to the function you provide: the *string* that needs to be formatted, and the key associated with that *string*. Say for instance, you wanted to display "export_val" as "Export Value" and capitalize all other strings, this would be your function:

```js
function format(text,key) {

	if (key == "export_val") {
		return "Export Value";
	}
	else {
		return text.charAt(0).toUpperCase() + text.substr(1).toLowerCase();
	}

}
```

***

<a name="time" href="#wiki-time">#</a> viz.**time**(*string*)

Defines the key to be used for slicing the data into different time periods. Currently, **D3plus** has very rudimentary time capabilities. It assumes all time variables to be integers, and places the responsibility of formatting onto the user.

<a name="time-func" href="#wiki-time-func">#</a> viz.**time**(*function*)

You can also pass a function as a method of determining the .**time**() value for a node. D3plus will pass your function the data point in question, and the function should return the value requested.

<a name="time-obj" href="#wiki-time-obj">#</a> viz.**time**(*object*)

.**time**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|fixed|When set to <code>**false**</code>, the axes will remain static as you change the .**time**() scope (using mute and solo). This makes it easier to see trends over time. If you would like the axes to change as time changes, set this to <code>**true**</code>.|<code>**false**</code>, <code>**true**</code>|<code>**false**</code>|
|key|Defines the key to be used for slicing the data into different time periods. When passing only a *string* or *function* to the .**time**() function, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [.**id**()](#id). This will tell **D3plus** to look in that specific nesting level's attribute list for the .**time**() variable. Additionally, if the *object* you pass to .**time**() does not contain any of the following keys, **D3plus** will use the *object* as this key.|*string*, *function*, *object*, <code>**null**</code>, <code>**false**</code>|<code>**null**</code>|
|mute|Hides specific data points from the viewer. Full documentation can be found [here](Filtering-Data#mute).|**value**, *function*, *array*|<code>**null**</code>|
|solo|Shows only specific data points to the viewer. Useful for only displaying specific time periods of data. Full documentation can be found [here](Filtering-Data#solo).|**value**, *function*, *array*|<code>**null**</code>|

***

<a name="timeline" href="#wiki-timeline">#</a> viz.**timeline**(*boolean*)

Displays a timeline slider that allows the user to change the [.**time**()](#time-obj) "solo" key. Defaults to <code>**true**</code>.

***

<a name="title" href="#wiki-title">#</a> viz.**title**(*string*)

Defines the title of the visualization. **D3plus** will place the supplied *string* above the visualization, wrapping the lines if they are too long to fit.

To remove the title, simply pass <code>**false**</code> or <code>**null**</code> to .**title**().

<a name="title-obj" href="#wiki-title-obj">#</a> viz.**title**(*object*)

.**title**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|link|A URL for the title to open when clicked. The page will open in a new window/tab.|*string*|<code>**null**</code>|
|sub|Defines the sub-title of the visualization. This is a smaller title that gets positioned directly under the main title.<br><br>Can be removed by passing either <code>**false**</code> or <code>**null**</code>. Can also be provided a "link", just like the main title.|*string*, <code>**false**</code>, <code>**null**</code>|<code>**null**</code>|
|total|Toggles a title line that appears underneath both the main title and sub-title that displays the total value of all of the data currently being shown (using whichever [.**aggs**()](#aggs) method is defined for the current [.**size**()](#size) key).<br><br>Instead of passing <code>**true**</code>, you can pass an *object* with "prefix" and/or "suffix" keys, whose values will be displayed on either side of the calculated total value.<br><br>Will be removed by passing either <code>**false**</code> or <code>**null**</code>. Can also be provided a "link", just like the main title.|*boolean*, *object*, <code>**false**</code>, <code>**null**</code>|<code>**false**</code>|
|value|Defines the title of the visualization. When passing only a *string* to the .**title**() function, this is the variable that actually gets set.<br><br>Can be removed by passing either <code>false</code> or <code>null</code>.|*string*, <code>**false**</code>, <code>**null**</code>|<code>**null**</code>|

***

<a name="tooltip" href="#wiki-tooltip">#</a> viz.**tooltip**(*array*)

Defines a list of keys to be displayed in the tooltip created for each node.

<a name="tooltip" href="#wiki-tooltip">#</a> viz.**tooltip**({"short": *array*, "long": *array*})

Defines separate lists of keys to be displayed in small tooltips and large tooltips.

<a name="tooltip-obj" href="#wiki-tooltip-obj">#</a> viz.**tooltip**(*object*)

If passed an object keyed by the various nesting levels defined in [.**id**()](#id), **D3plus** will use the value defined for the current [.**depth**()](#depth) level.

***

<a name="total" href="#wiki-total">#</a> viz.**total**(*string*)

Defines the key in your data associated with the total number of parts of a data point. This variable should be used in conjunction with [.**active**()](#active") and/or [.**temp**()](#temp") to correctly display fill percentages inside of shapes (such as making each node in a scatter plot a pie chart).

<a name="total-func" href="#wiki-total-func">#</a> viz.**total**(*function*)

You can also pass a function as a method of determining the total number of parts of a data point. D3plus will pass your function the data point in question, and the function should return the value requested.

<a name="total-obj" href="#wiki-total-obj">#</a> viz.**total**(*object*)

.**total**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|key|Defines the key in your data associated with the total number of parts of a data point. When passing only a *string* or *function* to the .**total**() function, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [.**id**()](#id). This will tell **D3plus** to look in that specific nesting level's attribute list for the .**total**() variable. Additionally, if the *object* you pass to .**total**() does not contain any of the following keys, **D3plus** will use the *object* as this key.|*string*, *function*, *object*, <code>**null**</code>, <code>**false**</code>|<code>**null**</code>|
|mute|Hides specific data points from the viewer. Full documentation can be found [here](Filtering-Data#mute).|**value**, *function*, *array*|<code>**null**</code>|
|solo|Shows only specific data points to the viewer. Full documentation can be found [here](Filtering-Data#solo).|**value**, *function*, *array*|<code>**null**</code>|

***

<a name="type" href="#wiki-type">#</a> viz.**type**(*string*)

Sets the current visualization type. [Click here](Visualization-Types) to view the different visualization types provided by **D3plus**.

<a name="type-obj" href="#wiki-type-obj">#</a> viz.**type**(*object*)

.**type**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|mode|Sets the "mode" for the current visualization. Currently only used in [Tree Map](wiki/Visualization-Types#wiki-tree_map).|<code>"squarify"</code>,<code>"slice"</code>,<code>"dice"</code>,<code>"slice-dice"</code>|<code>"squarify"</code>|
|value|What actually gets set when you only pass .**type**() a *string*.|*string*|<code>"tree_map"</code>|

***

<a name="width" href="#wiki-width">#</a> viz.**width**(*integer*)

Sets the width, in pixels, of the current visualization.

<a name="width-obj" href="#wiki-width-obj">#</a> viz.**width**(*object*)

.**width**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|small|When the width of the visualization is less than or equal to this *number*, it will enter "small" mode, where some functionality (such as tooltips) is disabled.|*number*|<code>**300**</code>|
|value|When passing only a *number* to the .**width**() function, this is the variable that actually gets set.|*number*|The width of the [.**container**()](#container), if defined. Otherwise, <code>window.innerWidth</code>|

***

<a name="x" href="#wiki-x">#</a> viz.**x**(*string*)

Defines the key in your data to be associated with the x-axis, for visualizations that support it.

<a name="x-func" href="#wiki-x-func">#</a> viz.**x**(*function*)

You can also pass a function as a method of determining the x-axis value. D3plus will pass your function the data point in question, and the function should return the value requested.

<a name="x-obj" href="#wiki-x-obj">#</a> viz.**x**(*object*)

.**x**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|domain|Defines the domain to be used when drawing the x-axis. If passed <code>**null**</code> or <code>**false**</code>, **D3plus** will calculate the x-axis domain based on the data available (which it does by default).|*array*|<code>**null**</code>|
|key|Defines the key in your data to be associated with the x-axis. When passing only a *string* or *function* to the .**x**() function, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [.**id**()](#id). This will tell **D3plus** to look in that specific nesting level's attribute list for the .**x**() variable. Additionally, if the *object* you pass to .**x**() does not contain any of the following keys, **D3plus** will use the *object* as this key.|*string*, *function*, *object*, <code>**null**</code>, <code>**false**</code>|<code>**null**</code>|
|lines|Will plot the values passed as static vertical lines on the x-axis. If the value is a single keyed *object*, **D3plus** will use the key as a label for the line (where the value is the x position of the line).|*array* containing *numbers* and/or *objects*|<code>**null**</code>|
|mute|Hides specific data points from the viewer. Full documentation can be found [here](Filtering-Data#mute).|**value**, *function*, *array*|<code>**null**</code>|
|scale|Defines the scale to use for plotting the x-axis.<br><br>A <code>"continuous"</code> scale will assume each value is unique, and will create a tick for each instance of that value (for example, the [.**time**()](#time) variable).<br><br>A <code>"share"</code> scale will plot values as percentages out of all of the available values.|<code>"linear"</code>, <code>"log"</code>, <code>"continuous"</code>, <code>"share"</code>|<code>"linear"</code>|
|stacked|Determines whether or not x-axis values should be stacked on top of each other. Ordering can be determined using [.**order**()](#order).|*boolean*|<code>**false**</code>|
|solo|Shows only specific data points to the viewer. Full documentation can be found [here](Filtering-Data#solo).|**value**, *function*, *array*|<code>**null**</code>|
|zerofill|If scale is <code>"continuous"</code>, this determines whether or not **D3plus** should fill gaps in the x-axis with <code>**0**</code> values.|*boolean*|<code>**false**</code>|

***

<a name="y" href="#wiki-y">#</a> viz.**y**(*string*)

Defines the key in your data to be associated with the y-axis, for visualizations that support it.

<a name="y-func" href="#wiki-y-func">#</a> viz.**y**(*function*)

You can also pass a function as a method of determining the y-axis value. D3plus will pass your function the data point in question, and the function should return the value requested.

<a name="y-obj" href="#wiki-y-obj">#</a> viz.**y**(*object*)

.**y**() also supports passing a keyed object. Here are the supported keys:

|Key|Description|Accepted Values|Default Value|
|---|---|---|---|
|domain|Defines the domain to be used when drawing the y-axis. If passed <code>**null**</code> or <code>**false**</code>, **D3plus** will calculate the y-axis domain based on the data available (which it does by default).|*array*|<code>**null**</code>|
|key|Defines the key in your data to be associated with the y-axis. When passing only a *string* or *function* to the .**y**() function, this is the variable that actually gets set.<br><br>You can also pass a single keyed *object*, keyed by the appropriate nesting level's [.**id**()](#id). This will tell **D3plus** to look in that specific nesting level's attribute list for the .**y**() variable. Additionally, if the *object* you pass to .**y**() does not contain any of the following keys, **D3plus** will use the *object* as this key.|*string*, *function*, *object*, <code>**null**</code>, <code>**false**</code>|<code>**null**</code>|
|lines|Will plot the values passed as static vertical lines on the y-axis. If the value is a single keyed *object*, **D3plus** will use the key as a label for the line (where the value is the y position of the line).|*array* containing *numbers* and/or *objects*|<code>**null**</code>|
|mute|Hides specific data points from the viewer. Full documentation can be found [here](Filtering-Data#mute).|**value**, *function*, *array*|<code>**null**</code>|
|scale|Defines the scale to use for plotting the y-axis.<br><br>A <code>"continuous"</code> scale will assume each value is unique, and will create a tick for each instance of that value (for example, the [.**time**()](#time) variable).<br><br>A <code>"share"</code> scale will plot values as percentages out of all of the available values.|<code>"linear"</code>, <code>"log"</code>, <code>"continuous"</code>, <code>"share"</code>|<code>"linear"</code>|
|stacked|Determines whether or not y-axis values should be stacked on top of each other. Ordering can be determined using [.**order**()](#order).|*boolean*|<code>**false**</code>|
|solo|Shows only specific data points to the viewer. Full documentation can be found [here](Filtering-Data#solo).|**value**, *function*, *array*|<code>**null**</code>|
|zerofill|If scale is <code>"continuous"</code>, this determines whether or not **D3plus** should fill gaps in the y-axis with <code>**0**</code> values.|*boolean*|<code>**false**</code>|

***

<a name="zoom" href="#wiki-zoom">#</a> viz.**zoom**(*boolean*)

Enables/disables visualization zooming.
