Here is a list of all of the currently supported style parameters. These may all be modified on an individual visualization basis by invoking the [.**style**()](wiki/Visualization-Methods#style-obj) method. [Click here](Visualization-Methods#style-obj) for an example on how to change specific parameters.

***

<a name="background" href="#wiki-background">#</a> **background**

Defines the overall visualization background color. Accepts a color *string*.

***

<a name="color" href="#wiki-color">#</a> **color**

Sets various visual styles of the color ranges used to display your data. Here are the accepted keys:

|Key|Description|
|---|---|
|heatmap|An *array* of colors to use when the [.**color**()](wiki/Visualization-Methods#color) values are all positive. Can be any number of colors.|
|missing|An *color* to use for when a shape has no data associated with it.|
|range|An *array* of colors to use when the [.**color**()](wiki/Visualization-Methods#color) values range from negative to position. Must be an array of 3 colors.|

***

<a name="data" href="#wiki-data">#</a> **data**

Sets various visual styles of the shapes drawn to represent your data. Here are the accepted keys:

|Key|Description|
|---|---|
|donut|Sets styling for "donut" shapes. Currently supports passing a keyed *object* with the following parameters: {"size": *number*}|
|opacity|Sets default shape opacity. Currently supports passing a *float* between  <code>**0**</code> and <code>**1**</code>.|
|stroke|Sets styling for shapes' outer stroke. Currently supports passing a keyed *object* with the following parameters: {"width": *number*}|

***

<a name="edges" href="#wiki-edges">#</a> **edges**

Sets variables regarding the styling of network edges. Here are the accepted keys:

|Key|Description|
|---|---|
|arrows|Width of direcitonal arrows. Accepts a *number* value.|
|color|The color of each link.|
|opacity|Sets default link opacity. Currently supports passing a *float* between  <code>**0**</code> and <code>**1**</code>.|
|width|*number* that represents the stroke-width of each link.|

***

<a name="font" href="#wiki-font">#</a> **font**

Sets various global font styles. Here are the accepted keys:

|Key|Description|
|---|---|
|color|Sets the color of all fonts used in the visualization.|
|decoration|Sets the text-decoration of all fonts used in the visualization.|
|family|Sets the font-family used throughout the entire visualization. Can be a single *string*, *array*, or comma-separated font-families (like with CSS).|
|transform|Sets the text-transform of all fonts used in the visualization.|
|weight|Sets the font-weight of all fonts used in the visualization.|

***

<a name="footer" href="#wiki-footer">#</a> **footer**

Defines various styles for the visualization footer. Here are the accepted keys:

|Key|Description|
|---|---|
|font-align|Horizontal alignment. Accepts "left", "center", and "right".|
|font-color|Color of the font used.|
|font-family|Family of the font used.|
|font-size|Size of the font used. Only accepts *number* values.|
|font-weight|Weight of the font.|
|padding|Pixel padding. Only accepts *number* values.|
|position|Where the fiiter should be placed, either above or below the visualization. Accepts <code>"top"</code> or <code>"bottom"</code>.|
|text-decoration|CSS style property.|
|text-transform|CSS style property.|

***

<a name="group" href="#wiki-group">#</a> **group**

Sets variables regarding data grouping, like in the [Bubbles](Visualization-Types#bubbles) visualization. Here are the accepted keys:

|Key|Description|
|---|---|
|background|*boolean* value that determines whether or not to show group nodes behind the data nodes.|

***

<a name="highlight" href="#wiki-highlight">#</a> **highlight**

Sets variables regarding the colors used to highlight data nodes and links. Here are the accepted keys:

|Key|Description|
|---|---|
|focus|Color used to highlight focus nodes and edges.|
|primary|Color used to highlight primary nodes and edges.|
|secondary|Color used to highlight secondary nodes and edges.|

***

<a name="labels" href="#wiki-labels">#</a> **labels**

Sets variables regarding the labels displayed over shapes. Here are the accepted keys:

|Key|Description|
|---|---|
|align|Determines the text-anchor of the label. Accepted values are: "start", "middle", and "end".|
|padding|*number* value of how much padding to allow on all sides of each label.|
|segments|*integer* value to determine how many segments to break an "area" shape into when analyzing positioning.|
|font|Font styling of the labels. Currently supports passing a keyed *object* with the following keys: "family", "weight", and "size".|

***

<a name="legend" href="#wiki-legend">#</a> **legend**

Sets styles regarding the color legend. Here are the accepted keys:

|Key|Description|
|---|---|
|align|Determines the horizontal position of the legend. Accepted values are: "start", "middle", and "end".|
|gradient|Styling of the gradient used for color scales. Currently supports passing a keyed *object* with the following keys: "height".|
|label|Styling of the label for the legend. Currently supports passing a keyed *object* with the following keys: "color", "family", "weight", "size".|
|padding|*number* value of how much padding to use for all elements in the legend.|
|size|*number* or *array* of value(s) for the width and height of color blocks. If an *array*, it should have 2 ordered values, the minimum and maximum.|
|tick|Styling of the tick marks and fonts for the legend. Currently supports passing a keyed *object* with the following keys: "align", "color", "family", "weight", "size".|

***

<a name="link" href="#wiki-link">#</a> **link**

Defines various styles for anchor links. Here are the accepted keys:

|Key|Description|
|---|---|
|font-color|Color of the font used.|
|font-family|Family of the font used.|
|font-weight|Weight of the font used.|
|hover|Style for when the cursor is hovering over the link. Has the following properties: "font-color", "font-family", "font-weight", "text-decoration", and "text-transform".|
|text-decoration|CSS style property.|
|text-transform|CSS style property.|

***

<a name="message" href="#wiki-message">#</a> **message**

Defines various styles for the visualization status message. Here are the accepted keys:

|Key|Description|
|---|---|
|font-color|Color of the font used|
|font-family|Family of the font used.|
|font-size|Size of the font used. Only accepts *number* values.|
|font-weight|Weight of the font used.|
|opacity|CSS style property.|
|padding|Pixel padding. Only accepts *number* values.|
|text-decoration|CSS style property.|
|text-transform|CSS style property.|

***

<a name="rendering" href="#wiki-rendering">#</a> **rendering**

The default shape-rending used for the SVG objects.

***

<a name="ticks" href="#wiki-ticks">#</a> **ticks**

Sets variables that change the styling of axis ticks. Here are the accepted keys:

|Key|Description|
|---|---|
|color|Stroke color of the ticks.|
|font|Font styling of the ticks. Currently supports passing a keyed *object* with the following parameters: {"color": *color*, "size": *number*}|
|size|Pixel length of the ticks.|
|width|Stroke width of the ticks.|

***

<a name="timeline" href="#wiki-timeline">#</a> **timeline**

Sets styles regarding the timeline. Here are the accepted keys:

|Key|Description|
|---|---|
|align|Determines the horizontal position of the timeline. Accepted values are: "start", "middle", and "end".|
|background|Background *color* of the timeline.|
|brush|Styling of the highlight brush for the timeline. Currently supports passing a keyed *object* with the following keys: "color", "opacity".|
|handles|Styling of the brush handles in the timeline. Currently supports passing a keyed *object* with the following keys: "color", "hover", "size".|
|height|*number* value of the height of timeline slider.|
|label|Styling of the label for the timeline. Currently supports passing a keyed *object* with the following keys: "color", "family", "weight", "size".|
|padding|*number* value of how much padding to use for all elements in the timeline.|
|tick|Styling of the tick marks and fonts for the timeline. Currently supports passing a keyed *object* with the following keys: "align", "color", "family", "weight", "size".|

***

<a name="timing" href="#wiki-timing">#</a> **timing**

Defines various transition type timings. Here are the accepted keys:

|Key|Description|
|---|---|
|mouseevents|Time, in milliseconds, of the mouse events (hover, etc).|
|transitions|Time, in milliseconds, of normal shape transitions.|

***

<a name="title" href="#wiki-title">#</a> **title**

Defines various styles for the visualization title(s). Here are the accepted keys:

|Key|Description|
|---|---|
|font-align|Horizontal alignment of the title. Accepts "left", "center", and "right".|
|font-color|Color of the font used in the main title.|
|font-family|Family of the font used in the main title.|
|font-size|Size of the font used in the main title. Only accepts *number* values.|
|font-weight|Weight of the font used in the main title.|
|height|How much vertical space, in pixels, required for the title. This is only taken into account if the "height" is larger than what the title needs, which will position the title vertically centered in that space. Only accepts *number* values.|
|padding|Pixel padding around the main title. Only accepts *number* values.|
|position|Where the main title should be placed, either above or below the visualization. Accepts <code>"top"</code> or <code>"bottom"</code>.|
|sub|Style object for the sub-title. Has the following properties: "font-align", "font-color", "font-family", "font-size", "font-weight", "padding", "position", "text-decoration", and "text-transform".|
|text-decoration|CSS style property.|
|text-transform|CSS style property.|
|total|Style object for the total bar. Has the following properties: "font-align", "font-color", "font-family", "font-size", "font-weight", "padding", "position", "text-decoration", and "text-transform".|
|width|How much horizontal space, in pixels, required for the title. Only accepts *number* values.|

***

<a name="tooltip" href="#wiki-tooltip">#</a> **tooltip**

Defines various styles for the tooltips. Here are the accepted keys:

|Key|Description|
|---|---|
|anchor|The anchor point on the node for the floating tooltip. Should be defined as two words, the first representing vertically "top", "middle", or "bottom" and the second representing horizontal "left", "center", or "right".|
|background|The background color for the tooltip.|
|font|Font styling of the tooltips. Currently supports passing a keyed *object* with the following keys: "color", "family", and "weight".|
|small|*number* width for small tooltips created inside the visualization.|
|large|*number* width for large tooltips created inside the visualization.|
