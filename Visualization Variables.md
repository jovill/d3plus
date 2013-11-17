The visualizations in **D3plus** have numerous variables for you to tweak in order to get the perfect visualization that suits your needs. Some variables are only for 1 visualization type, while other are used across multiple types.

##<a name="active_var" href="#wiki-active_var">#</a> d3plus.viz.active_var
variable used when defining active/inactive objects

##<a name="aggs" href="#wiki-aggs">#</a> d3plus.viz.aggs
Object with mathematical aggregation types. The following aggregation functions are available: 
*   max
*   mean
*   median
*   min
*   sum
The following is an example of how this would be used:
```js
.aggs({"value_variable":"median"})
```

##<a name="attrs" href="#wiki-attrs">#</a> d3plus.viz.attrs
dictionary of static attributes for the data

##<a name="background<" href="#wiki-background<">#</a> d3plus.viz.background
visualization background color

##<a name="click_function" href="#wiki-click_function">#</a> d3plus.viz.click_function
function that provides extra information for data on click

##<a name="color_var" href="#wiki-color_var">#</a> d3plus.viz.color_var
variable used to color each data point

##<a name="csv_data" href="#wiki-csv_data">#</a> d3plus.viz.csv_data
returns data in .csv format

##<a name="csv_columns" href="#wiki-csv_columns">#</a> d3plus.viz.csv_columns
array of keys to be used when generating .csv_data()

##<a name="coords" href="#wiki-coords">#</a> d3plus.viz.coords
topoJSON coordinates used in Geo Map

##<a name="depth" href="#wiki-depth">#</a> d3plus.viz.depth
which level of nesting to display

##<a name="descs" href="#wiki-descs">#</a> d3plus.viz.descs
key definitions for tooltips

##<a name="dev" href="#wiki-dev">#</a> d3plus.viz.dev
boolean to show/hide developer console statements

##<a name="donut" href="#wiki-donut">#</a> d3plus.viz.donut
boolean to show/hide inner donut in Bubble visualizations

##<a name="else_var" href="#wiki-else_var">#</a> d3plus.viz.else_var
variables for in cross-hatched area in Bubble visualizations

##<a name="error" href="#wiki-error">#</a> d3plus.viz.error
error message to display

##<a name="filter" href="#wiki-filter">#</a> d3plus.viz.filter
IDs to filter out of the visualization

##<a name="footer" href="#wiki-footer">#</a> d3plus.viz.footer
footer information for visualization

##<a name="font" href="#wiki-font">#</a> d3plus.viz.font
font family to be used for all text elements

##<a name="font_weight" href="#wiki-font_weight">#</a> d3plus.viz.font_weight
font weight to be used for all text elements

##<a name="group_bgs" href="#wiki-group_bgs">#</a> d3plus.viz.group_bgs
boolean to show/hide group background circles in Bubble visualizations

##<a name="grouping" href="#wiki-grouping">#</a> d3plus.viz.grouping
variable used when grouping objects

##<a name="height" href="#wiki-height">#</a> d3plus.viz.height
overall height of visualization

##<a name="highlight" href="#wiki-highlight">#</a> d3plus.viz.highlight
ID of element being highlighted in visualization

##<a name="icon_style" href="#wiki-icon_style">#</a> d3plus.viz.icon_style
style of icons

##<a name="id_var" href="#wiki-id_var">#</a> d3plus.viz.id_var
variable(s) used as a unique ID

##<a name="labels" href="#wiki-labels">#</a> d3plus.viz.labels
boolean to show/hide labels in Stacked visualization

##<a name="layout" href="#wiki-layout">#</a> d3plus.viz.layout
Stacked visualization layout type

##<a name="links" href="#wiki-links">#</a> d3plus.viz.links
object of connections for Network/Rings nodes

##<a name="info_style" href="#wiki-info_style">#</a> d3plus.viz.info_style
text style for information messages

##<a name="mirror_axis" href="#wiki-mirror_axis">#</a> d3plus.viz.mirror_axis
boolean to mirror axes in Pie Scatter visualization

##<a name="nodes" href="#wiki-nodes">#</a> d3plus.viz.nodes
object of node positions for Network visualization

##<a name="number_format" href="#wiki-number_format">#</a> d3plus.viz.number_format
function used to format numbers

##<a name="order" href="#wiki-order">#</a> d3plus.viz.order
variable used to determine object ordering

##<a name="scroll_zoom" href="#wiki-scroll_zoom">#</a> d3plus.viz.scroll_zoom
boolean to allow zoom scrolling in visualizations

##<a name="size_scale" href="#wiki-size_scale">#</a> d3plus.viz.size_scale
type of scale to use when sizing nodes

##<a name="solo" href="#wiki-solo">#</a> d3plus.viz.solo
IDs to solo in the visualization

##<a name="sort" href="#wiki-sort">#</a> d3plus.viz.sort
variable used to determine how to sort objects

##<a name="spotlight" href="#wiki-spotlight">#</a> d3plus.viz.spotlight
boolean used to show/hide active objects

##<a name="stack_type" href="#wiki-stack_type">#</a> d3plus.viz.stack_type
type of line interpolation to use in the Stacked visualization

##<a name="static_axes" href="#wiki-static_axes">#</a> d3plus.viz.static_axes
boolean used to determine Pie Scatter axes min/max

##<a name="sub_title" href="#wiki-sub_title">#</a> d3plus.viz.sub_title
visualization sub-title

##<a name="text_format" href="#wiki-text_format">#</a> d3plus.viz.text_format
function used to format strings

##<a name="text_var" href="#wiki-text_var">#</a> d3plus.viz.text_var
variable used to label objects and tooltips

##<a name="title" href="#wiki-title">#</a> d3plus.viz.title
visualization title

##<a name="title_center" href="#wiki-title_center">#</a> d3plus.viz.title_center
boolean used to always center title

##<a name="title_height" href="#wiki-title_height">#</a> d3plus.viz.title_height
minimum height needed for title

##<a name="title_width" href="#wiki-title_width">#</a> d3plus.viz.title_width
allowed width for title

##<a name="tooltip" href="#wiki-tooltip">#</a> d3plus.viz.tooltip
keys to use in tooltips

##<a name="total_bar" href="#wiki-total_bar">#</a> d3plus.viz.total_bar
boolean used to show data sub-total underneath visualization title

##<a name="type" href="#wiki-type">#</a> d3plus.viz.type
variable to set visualization type

##<a name="value_var" href="#wiki-value_var">#</a> d3plus.viz.value_var
variable used to size objects in visualizations

##<a name="width" href="#wiki-width">#</a> d3plus.viz.width
overall width of visualization

##<a name="xaxis_domain" href="#wiki-xaxis_domain">#</a> d3plus.viz.xaxis_domain
array to manual set x-axis domain

##<a name="xaxis_var" href="#wiki-xaxis_var">#</a> d3plus.viz.xaxis_var
variable used for x-axis values

##<a name="xaxis_scale" href="#wiki-xaxis_scale">#</a> d3plus.viz.xaxis_scale
scale type for x-axis

##<a name="yaxis_domain" href="#wiki-yaxis_domain">#</a> d3plus.viz.yaxis_domain
array to manual set y-axis domain

##<a name="yaxis_var" href="#wiki-yaxis_var">#</a> d3plus.viz.yaxis_var
variable used for y-axis values

##<a name="yaxis_scale" href="#wiki-yaxis_scale">#</a> d3plus.viz.yaxis_scale
scale type for y-axis

##<a name="year" href="#wiki-year">#</a> d3plus.viz.year
current year to be displayed

##<a name="year_var" href="#wiki-year_var">#</a> d3plus.viz.year_var
variable used to split the data into separate years