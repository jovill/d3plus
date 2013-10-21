**D3plus** is an extension to the **D3** library that allows fast and easy creation of popular visualizations.

##[Dependencies](wiki/Dependencies)
* [D3.js](wiki/Dependencies#d3)
* [Zoomable Tiles](wiki/Dependencies#tiles)
* [TopoJSON](wiki/Dependencies#topojson)
* [Modernizr](wiki/Dependencies#modernizr)

##[Getting Started](wiki/Getting-Started)
* [Creating a Visualization](wiki/Getting-Started#viz)
* [Changing Variables](wiki/Getting-Started#variables)
* [Changing Data](wiki/Getting-Started#data)

##[Visualization Types](wiki/Visualization-Types)
* [Bubbles](wiki/Visualization-Types#bubbles)
* [Geo Map](wiki/Visualization-Types#geo_map)
* [Network](wiki/Visualization-Types#network)
* [Pie Scatter](wiki/Visualization-Types#pie_scatter)
* [Rings](wiki/Visualization-Types#rings)
* [Stacked](wiki/Visualization-Types#stacked)
* [Tree Map](wiki/Visualization-Types#tree_map)

##[Visualization Variables](wiki/Visualization-Variables)
* [d3plus.viz.active_var](wiki/Visualization-Variables#active_var) - variable used when defining active/inactive objects
* [d3plus.viz.attrs](wiki/Visualization-Variables#attrs) - dictionary of static attributes for the data
* [d3plus.viz.background](wiki/Visualization-Variables#background) - visualization background color
* [d3plus.viz.click_function](wiki/Visualization-Variables#click_function) - function that provides extra information for data on click
* [d3plus.viz.color_var](wiki/Visualization-Variables#color_var) - variable used to color each data point
* [d3plus.viz.csv_data](wiki/Visualization-Variables#csv_data) - returns data in .csv format
* [d3plus.viz.csv_columns](wiki/Visualization-Variables#csv_columns) - array of keys to be used when generating .csv_data()
* [d3plus.viz.coords](wiki/Visualization-Variables#coords) - topoJSON coordinates used in Geo Map
* [d3plus.viz.depth](wiki/Visualization-Variables#depth) - which level of nesting to display
* [d3plus.viz.descs](wiki/Visualization-Variables#descs) - key definitions for tooltips
* [d3plus.viz.dev](wiki/Visualization-Variables#dev) - boolean to show/hide developer console statements
* [d3plus.viz.donut](wiki/Visualization-Variables#wiki-donut) - boolean to show/hide inner donut in Bubble visualizations
* [d3plus.viz.else_var](wiki/Visualization-Variables#else_var) - variables for in cross-hatched area in Bubble visualizations
* [d3plus.viz.error](wiki/Visualization-Variables#error) - error message to display
* [d3plus.viz.filter](wiki/Visualization-Variables#filter) - IDs to filter out of the visualization
* [d3plus.viz.footer](wiki/Visualization-Variables#footer) - footer information for visualization
* [d3plus.viz.font](wiki/Visualization-Variables#font) - font family to be used for all text elements
* [d3plus.viz.font_weight](wiki/Visualization-Variables#font_weight) - font weight to be used for all text elements
* [d3plus.viz.group_bgs](wiki/Visualization-Variables#group_bgs) - boolean to show/hide group background circles in Bubble visualizations
* [d3plus.viz.grouping](wiki/Visualization-Variables#grouping) - variable used when grouping objects
* [d3plus.viz.height](wiki/Visualization-Variables#height) - overall height of visualization
* [d3plus.viz.highlight](wiki/Visualization-Variables#highlight) - ID of element being highlighted in visualization
* [d3plus.viz.icon_style](wiki/Visualization-Variables#icon_style) - style of icons
* [d3plus.viz.id_var](wiki/Visualization-Variables#id_var) - variable used as a unique ID
* [d3plus.viz.labels](wiki/Visualization-Variables#labels) - boolean to show/hide labels in Stacked visualization
* [d3plus.viz.layout](wiki/Visualization-Variables#layout) - Stacked visualization layout type
* [d3plus.viz.links](wiki/Visualization-Variables#links) - object of connections for Network/Rings nodes
* [d3plus.viz.info_style](wiki/Visualization-Variables#info_style) - text style for information messages
* [d3plus.viz.mirror_axis](wiki/Visualization-Variables#mirror_axis) - boolean to mirror axes in Pie Scatter visualization
* [d3plus.viz.name_array](wiki/Visualization-Variables#name_array) - array of keys to check when wrapping Tree Map labels
* [d3plus.viz.nesting](wiki/Visualization-Variables#nesting) - array of keys for the various depth levels
* [d3plus.viz.nesting_aggs](wiki/Visualization-Variables#nesting_aggs) - object with mathematical aggregation types
* [d3plus.viz.nodes](wiki/Visualization-Variables#nodes) - object of node positions for Network visualization
* [d3plus.viz.number_format](wiki/Visualization-Variables#number_format) - function used to format numbers
* [d3plus.viz.order](wiki/Visualization-Variables#order) - variable used to determine object ordering
* [d3plus.viz.scroll_zoom](wiki/Visualization-Variables#scroll_zoom) - boolean to allow zoom scrolling in visualizations
* [d3plus.viz.size_scale](wiki/Visualization-Variables#size_scale) - type of scale to use when sizing nodes
* [d3plus.viz.solo](wiki/Visualization-Variables#solo) - IDs to solo in the visualization
* [d3plus.viz.sort](wiki/Visualization-Variables#sort) - variable used to determine how to sort objects
* [d3plus.viz.spotlight](wiki/Visualization-Variables#spotlight) - boolean used to show/hide active objects
* [d3plus.viz.stack_type](wiki/Visualization-Variables#stack_type) - type of line interpolation to use in the Stacked visualization
* [d3plus.viz.static_axes](wiki/Visualization-Variables#static_axes) - boolean used to determine Pie Scatter axes min/max
* [d3plus.viz.sub_title](wiki/Visualization-Variables#sub_title) - visualization sub-title
* [d3plus.viz.text_format](wiki/Visualization-Variables#text_format) - function used to format strings
* [d3plus.viz.text_var](wiki/Visualization-Variables#text_var) - variable used to label objects and tooltips
* [d3plus.viz.title](wiki/Visualization-Variables#title) - visualization title
* [d3plus.viz.title_center](wiki/Visualization-Variables#title_center) - boolean used to always center title
* [d3plus.viz.title_height](wiki/Visualization-Variables#title_height) - minimum height needed for title
* [d3plus.viz.title_width](wiki/Visualization-Variables#title_width) - allowed width for title
* [d3plus.viz.tooltip_info](wiki/Visualization-Variables#tooltip_info) - keys to use in tooltips
* [d3plus.viz.total_bar](wiki/Visualization-Variables#total_bar) - boolean used to show data sub-total underneath visualization title
* [d3plus.viz.type](wiki/Visualization-Variables#type) - variable to set visualization type
* [d3plus.viz.value_var](wiki/Visualization-Variables#value_var) - variable used to size objects in visualizations
* [d3plus.viz.width](wiki/Visualization-Variables#width) - overall width of visualization
* [d3plus.viz.xaxis_domain](wiki/Visualization-Variables#xaxis_domain) - array to manual set x-axis domain
* [d3plus.viz.xaxis_var](wiki/Visualization-Variables#xaxis_var) - variable used for x-axis values
* [d3plus.viz.xaxis_scale](wiki/Visualization-Variables#xaxis_scale) - scale type for x-axis
* [d3plus.viz.yaxis_domain](wiki/Visualization-Variables#yaxis_domain) - array to manual set y-axis domain
* [d3plus.viz.yaxis_var](wiki/Visualization-Variables#yaxis_var) - variable used for y-axis values
* [d3plus.viz.yaxis_scale](wiki/Visualization-Variables#yaxis_scale) - scale type for y-axis
* [d3plus.viz.year](wiki/Visualization-Variables#year) - current year to be displayed
* [d3plus.viz.year_var](wiki/Visualization-Variables#year_var) - variable used to split the data into separate years

##[Global Variables](wiki/Global-Variables)
* [d3plus.version](wiki/Global-Variables#version) - displays current semantic version
* [d3plus.timing](wiki/Global-Variables#timing) - the timing of all animations
* [d3plus.ie](wiki/Global-Variables#ie) - returns true if the browser is Internet Explorer
* [d3plus.evt[event]](wiki/Global-Variables#evt) - touch/mouse events

##[Utilities](wiki/Utilities)
* [d3plus.utils.rand_color](wiki/Utilities#rand_color) - returns a random color
* [d3plus.utils.text_color](wiki/Utilities#text_color) - determines appropriate text color
* [d3plus.utils.darker_color](wiki/Utilities#darker_color) - darkens a color until it is legible on white
* [d3plus.utils.unique](wiki/Utilities#uniques) - finds unique values in an object
* [d3plus.utils.merge](wiki/Utilities#merge) - merges two objects
* [d3plus.utils.wordwrap](wiki/Utilities#wordwrap) - wraps long lines of SVG text