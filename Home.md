**D3plus** is an extension to the **D3** library that allows fast and easy creation of popular visualizations.

##[Dependencies](wiki/Dependencies)
* [D3.js](wiki/Dependencies#wiki-d3)
* [Zoomable Tiles](wiki/Dependencies#wiki-tiles)
* [TopoJSON](wiki/Dependencies#wiki-topojson)
* [Modernizr](wiki/Dependencies#wiki-modernizr)

##[Getting Started](wiki/Getting-Started)
* [Installing](wiki/Getting-Started#installing)
* [Creating a Visualization](wiki/Getting-Started#wiki-viz)
* [Changing Variables](wiki/Getting-Started#wiki-variables)
* [Changing Data](wiki/Getting-Started#wiki-data)

##[Visualization Types](wiki/Visualization-Types)
* [Bubbles](wiki/Visualization-Types#wiki-bubbles)
* [Geo Map](wiki/Visualization-Types#wiki-geo_map)
* [Network](wiki/Visualization-Types#wiki-network)
* [Pie Scatter](wiki/Visualization-Types#wiki-pie_scatter)
* [Rings](wiki/Visualization-Types#wiki-rings)
* [Stacked](wiki/Visualization-Types#wiki-stacked)
* [Tree Map](wiki/Visualization-Types#wiki-tree_map)

##[Visualization Variables](wiki/Visualization-Variables)
* [d3plus.viz.active_var](wiki/Visualization-Variables#wiki-active_var) - variable used when defining active/inactive objects
* [d3plus.viz.attrs](wiki/Visualization-Variables#wiki-attrs) - dictionary of static attributes for the data
* [d3plus.viz.background](wiki/Visualization-Variables#wiki-background) - visualization background color
* [d3plus.viz.click_function](wiki/Visualization-Variables#wiki-click_function) - function that provides extra information for data on click
* [d3plus.viz.color_var](wiki/Visualization-Variables#wiki-color_var) - variable used to color each data point
* [d3plus.viz.csv_data](wiki/Visualization-Variables#wiki-csv_data) - returns data in .csv format
* [d3plus.viz.csv_columns](wiki/Visualization-Variables#wiki-csv_columns) - array of keys to be used when generating .csv_data()
* [d3plus.viz.coords](wiki/Visualization-Variables#wiki-coords) - topoJSON coordinates used in Geo Map
* [d3plus.viz.depth](wiki/Visualization-Variables#wiki-depth) - which level of nesting to display
* [d3plus.viz.descs](wiki/Visualization-Variables#wiki-descs) - key definitions for tooltips
* [d3plus.viz.dev](wiki/Visualization-Variables#wiki-dev) - boolean to show/hide developer console statements
* [d3plus.viz.donut](wiki/Visualization-Variables#wiki-donut) - boolean to show/hide inner donut in Bubble visualizations
* [d3plus.viz.else_var](wiki/Visualization-Variables#wiki-else_var) - variables for in cross-hatched area in Bubble visualizations
* [d3plus.viz.error](wiki/Visualization-Variables#wiki-error) - error message to display
* [d3plus.viz.filter](wiki/Visualization-Variables#wiki-filter) - IDs to filter out of the visualization
* [d3plus.viz.footer](wiki/Visualization-Variables#wiki-footer) - footer information for visualization
* [d3plus.viz.font](wiki/Visualization-Variables#wiki-font) - font family to be used for all text elements
* [d3plus.viz.font_weight](wiki/Visualization-Variables#wiki-font_weight) - font weight to be used for all text elements
* [d3plus.viz.group_bgs](wiki/Visualization-Variables#wiki-group_bgs) - boolean to show/hide group background circles in Bubble visualizations
* [d3plus.viz.grouping](wiki/Visualization-Variables#wiki-grouping) - variable used when grouping objects
* [d3plus.viz.height](wiki/Visualization-Variables#wiki-height) - overall height of visualization
* [d3plus.viz.highlight](wiki/Visualization-Variables#wiki-highlight) - ID of element being highlighted in visualization
* [d3plus.viz.icon_style](wiki/Visualization-Variables#wiki-icon_style) - style of icons
* [d3plus.viz.id_var](wiki/Visualization-Variables#wiki-id_var) - variable used as a unique ID
* [d3plus.viz.labels](wiki/Visualization-Variables#wiki-labels) - boolean to show/hide labels in Stacked visualization
* [d3plus.viz.layout](wiki/Visualization-Variables#wiki-layout) - Stacked visualization layout type
* [d3plus.viz.links](wiki/Visualization-Variables#wiki-links) - object of connections for Network/Rings nodes
* [d3plus.viz.info_style](wiki/Visualization-Variables#wiki-info_style) - text style for information messages
* [d3plus.viz.mirror_axis](wiki/Visualization-Variables#wiki-mirror_axis) - boolean to mirror axes in Pie Scatter visualization
* [d3plus.viz.name_array](wiki/Visualization-Variables#wiki-name_array) - array of keys to check when wrapping Tree Map labels
* [d3plus.viz.nesting](wiki/Visualization-Variables#wiki-nesting) - array of keys for the various depth levels
* [d3plus.viz.nesting_aggs](wiki/Visualization-Variables#wiki-nesting_aggs) - object with mathematical aggregation types
* [d3plus.viz.nodes](wiki/Visualization-Variables#wiki-nodes) - object of node positions for Network visualization
* [d3plus.viz.number_format](wiki/Visualization-Variables#wiki-number_format) - function used to format numbers
* [d3plus.viz.order](wiki/Visualization-Variables#wiki-order) - variable used to determine object ordering
* [d3plus.viz.scroll_zoom](wiki/Visualization-Variables#wiki-scroll_zoom) - boolean to allow zoom scrolling in visualizations
* [d3plus.viz.size_scale](wiki/Visualization-Variables#wiki-size_scale) - type of scale to use when sizing nodes
* [d3plus.viz.solo](wiki/Visualization-Variables#wiki-solo) - IDs to solo in the visualization
* [d3plus.viz.sort](wiki/Visualization-Variables#wiki-sort) - variable used to determine how to sort objects
* [d3plus.viz.spotlight](wiki/Visualization-Variables#wiki-spotlight) - boolean used to show/hide active objects
* [d3plus.viz.stack_type](wiki/Visualization-Variables#wiki-stack_type) - type of line interpolation to use in the Stacked visualization
* [d3plus.viz.static_axes](wiki/Visualization-Variables#wiki-static_axes) - boolean used to determine Pie Scatter axes min/max
* [d3plus.viz.sub_title](wiki/Visualization-Variables#wiki-sub_title) - visualization sub-title
* [d3plus.viz.text_format](wiki/Visualization-Variables#wiki-text_format) - function used to format strings
* [d3plus.viz.text_var](wiki/Visualization-Variables#wiki-text_var) - variable used to label objects and tooltips
* [d3plus.viz.title](wiki/Visualization-Variables#wiki-title) - visualization title
* [d3plus.viz.title_center](wiki/Visualization-Variables#wiki-title_center) - boolean used to always center title
* [d3plus.viz.title_height](wiki/Visualization-Variables#wiki-title_height) - minimum height needed for title
* [d3plus.viz.title_width](wiki/Visualization-Variables#wiki-title_width) - allowed width for title
* [d3plus.viz.tooltip_info](wiki/Visualization-Variables#wiki-tooltip_info) - keys to use in tooltips
* [d3plus.viz.total_bar](wiki/Visualization-Variables#wiki-total_bar) - boolean used to show data sub-total underneath visualization title
* [d3plus.viz.type](wiki/Visualization-Variables#wiki-type) - variable to set visualization type
* [d3plus.viz.value_var](wiki/Visualization-Variables#wiki-value_var) - variable used to size objects in visualizations
* [d3plus.viz.width](wiki/Visualization-Variables#wiki-width) - overall width of visualization
* [d3plus.viz.xaxis_domain](wiki/Visualization-Variables#wiki-xaxis_domain) - array to manual set x-axis domain
* [d3plus.viz.xaxis_var](wiki/Visualization-Variables#wiki-xaxis_var) - variable used for x-axis values
* [d3plus.viz.xaxis_scale](wiki/Visualization-Variables#wiki-xaxis_scale) - scale type for x-axis
* [d3plus.viz.yaxis_domain](wiki/Visualization-Variables#wiki-yaxis_domain) - array to manual set y-axis domain
* [d3plus.viz.yaxis_var](wiki/Visualization-Variables#wiki-yaxis_var) - variable used for y-axis values
* [d3plus.viz.yaxis_scale](wiki/Visualization-Variables#wiki-yaxis_scale) - scale type for y-axis
* [d3plus.viz.year](wiki/Visualization-Variables#wiki-year) - current year to be displayed
* [d3plus.viz.year_var](wiki/Visualization-Variables#wiki-year_var) - variable used to split the data into separate years

##[Global Variables](wiki/Global-Variables)
* [d3plus.version](wiki/Global-Variables#wiki-version) - displays current semantic version
* [d3plus.timing](wiki/Global-Variables#wiki-timing) - the timing of all animations
* [d3plus.ie](wiki/Global-Variables#wiki-ie) - returns true if the browser is Internet Explorer
* [d3plus.evt[event]](wiki/Global-Variables#wiki-evt) - touch/mouse events

##[Utilities](wiki/Utilities)
* [d3plus.utils.rand_color](wiki/Utilities#wiki-rand_color) - returns a random color
* [d3plus.utils.text_color](wiki/Utilities#wiki-text_color) - determines appropriate text color
* [d3plus.utils.darker_color](wiki/Utilities#wiki-darker_color) - darkens a color until it is legible on white
* [d3plus.utils.unique](wiki/Utilities#wiki-uniques) - finds unique values in an object
* [d3plus.utils.merge](wiki/Utilities#wiki-merge) - merges two objects
* [d3plus.utils.wordwrap](wiki/Utilities#wiki-wordwrap) - wraps long lines of SVG text