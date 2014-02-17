**D3plus** is an extension to the **D3** library that allows fast and easy creation of data visualizations.

##[Dependencies](wiki/Dependencies)
* [D3.js](wiki/Dependencies#wiki-d3) [**REQUIRED**]
* [Font Awesome](wiki/Dependencies#wiki-fontawesome)
* [Modernizr](wiki/Dependencies#wiki-modernizr)
* [TopoJSON](wiki/Dependencies#wiki-topojson)

##[Getting Started](wiki/Getting-Started)
* [Environment Setup](wiki/Getting-Started#setup)
* [Creating a Visualization](wiki/Getting-Started#wiki-viz)
* [Changing Variables](wiki/Getting-Started#wiki-variables)

##[Visualization Types](wiki/Visualization-Types)
* [Bubbles](wiki/Visualization-Types#wiki-bubbles)
* [Chart](wiki/Visualization-Types#wiki-chart)
* [Geo Map](wiki/Visualization-Types#wiki-geo_map)
* [Line Plot](wiki/Visualization-Types#wiki-line)
* [Network](wiki/Visualization-Types#wiki-network)
* [Rings](wiki/Visualization-Types#wiki-rings)
* [Stacked Area](wiki/Visualization-Types#wiki-stacked)
* [Tree Map](wiki/Visualization-Types#wiki-tree_map)

##[Visualization Methods](wiki/Visualization-Methods)
* [viz.active](wiki/Visualization-Methods#wiki-active) - key for partially filling shapes
* [viz.aggs](wiki/Visualization-Methods#wiki-aggs) - aggregation methods for specific keys
* [viz.axes](wiki/Visualization-Methods#wiki-axes) - various axes styles
* [viz.attrs](wiki/Visualization-Methods#wiki-attrs) - data attribute lists
* [viz.color](wiki/Visualization-Methods#wiki-color) - key for coloring shapes
* [viz.container](wiki/Visualization-Methods#wiki-container) - parent DOM object [**REQUIRED**]
* [viz.coords](wiki/Visualization-Methods#wiki-coords) - topojson coordinates
* [viz.csv](wiki/Visualization-Methods#wiki-csv) - download visualization data as .csv file
* [viz.data](wiki/Visualization-Methods#wiki-data) - visualization data [**REQUIRED**]
* [viz.draw](wiki/Visualization-Methods#wiki-draw) - draw the visualization [**REQUIRED**]
* [viz.depth](wiki/Visualization-Methods#wiki-depth) - shape aggregation
* [viz.descs](wiki/Visualization-Methods#wiki-descs) - key descriptions for tooltips
* [viz.dev](wiki/Visualization-Methods#wiki-dev) - development console statements
* [viz.error](wiki/Visualization-Methods#wiki-error) - user-defined error message
* [viz.focus](wiki/Visualization-Methods#wiki-focus) - selected node in visualization
* [viz.footer](wiki/Visualization-Methods#wiki-footer) - overall footer text/link
* [viz.height](wiki/Visualization-Methods#wiki-height) - visualization height
* [viz.html](wiki/Visualization-Methods#wiki-html) - tooltip html content
* [viz.icon](wiki/Visualization-Methods#wiki-icon) - key for tooltip icons
* [viz.id](wiki/Visualization-Methods#wiki-id) - unique key for each data point
* [viz.labels](wiki/Visualization-Methods#wiki-labels) - toggles text labels for shapes
* [viz.legend](wiki/Visualization-Methods#wiki-legend) - visual color legend
* [viz.links](wiki/Visualization-Methods#wiki-links) - node connection data
* [viz.nodes](wiki/Visualization-Methods#wiki-nodes) - node positioning data
* [viz.number_format](wiki/Visualization-Methods#wiki-number_format) - custom number display
* [viz.order](wiki/Visualization-Methods#wiki-order) - key for ordering shapes
* [viz.shape](wiki/Visualization-Methods#wiki-shape) - shape used to visualize the data
* [viz.size](wiki/Visualization-Methods#wiki-size) - key for sizing shapes
* [viz.style](wiki/Visualization-Methods#wiki-style) - graphical styling of the visualization
* [viz.temp](wiki/Visualization-Methods#wiki-temp) - key for partially filling shapes
* [viz.text](wiki/Visualization-Methods#wiki-text) - keys for labels and tooltip titles
* [viz.text_format](wiki/Visualization-Methods#wiki-text_format) - custom text display
* [viz.time](wiki/Visualization-Methods#wiki-time) - key for slicing data by time
* [viz.timeline](wiki/Visualization-Methods#wiki-timeline) - timeline slider
* [viz.title](wiki/Visualization-Methods#wiki-title) - visualization title(s)
* [viz.tooltip](wiki/Visualization-Methods#wiki-tooltip) - tooltip data keys
* [viz.total](wiki/Visualization-Methods#wiki-total) - key for partially filling shapes
* [viz.type](wiki/Visualization-Methods#wiki-type) - visualization type
* [viz.width](wiki/Visualization-Methods#wiki-width) - visualization width
* [viz.x](wiki/Visualization-Methods#wiki-x) - x-axis variables
* [viz.y](wiki/Visualization-Methods#wiki-y) - y-axis variables

##[Filtering Data](wiki/Filtering-Data)
* [Mute](wiki/Filtering-Data#wiki-mute) - hides specific data points
* [Solo](wiki/Filtering-Data#wiki-solo) - only shows specific data points
* [Values](wiki/Filtering-Data#wiki-methods) - acceptable values for each filter

##[Basic Utilities](wiki/Basic-Utilities)
* [utils.buckets](wiki/Basic-Utilities#wiki-buckets) - fills out an array into specified buckets
* [utils.closest](wiki/Basic-Utilities#wiki-closest) - finds closest numeric value in array
* [utils.copy](wiki/Basic-Utilities#wiki-copy) - copies an object
* [utils.merge](wiki/Basic-Utilities#wiki-merge) - merges two objects
* [utils.strip](wiki/Basic-Utilities#wiki-strip) - removes non-ascii characters from a string
* [utils.unqiues](wiki/Basic-Utilities#wiki-unqiues) - finds unique key values in a data array
* [utils.wordwrap](wiki/Basic-Utilities#wiki-wordwrap) - resizing and wraps svg text

##[Color Utilities](wiki/Color-Utilities)
* [color.darker](wiki/Color-Utilities#wiki-darker) - darkens a color
* [color.legible](wiki/Color-Utilities#wiki-legible) - makes a color legible on white
* [color.lighter](wiki/Color-Utilities#wiki-lighter) - lightens a color
* [color.mix](wiki/Color-Utilities#wiki-mix) - mixes 2 colors
* [color.random](wiki/Color-Utilities#wiki-random) - returns a random color
* [color.text](wiki/Color-Utilities#wiki-text) - analyzes a color to determine best text color

##[Global Variables](wiki/Global-Variables)
* [d3plus.evt](wiki/Global-Variables#wiki-evt) - mouse/touch event detection
* [d3plus.fontawesome](wiki/Global-Variables#wiki-fontawesome) - Font Awesome detection
* [d3plus.ie](wiki/Global-Variables#wiki-ie) - Internet Explorer detection
* [d3plus.rtl](wiki/Global-Variables#wiki-rtl) - Right-to-Left Text detection
* [d3plus.scrollbar()](wiki/Global-Variables#wiki-scrollbar) - Browser scrollbar width
* [d3plus.version](wiki/Global-Variables#wiki-version) - current **D3plus** version number

##[Style Parameters](wiki/Style-Parameters)
* [background](wiki/Style-Parameters#wiki-background) - visualization background color
* [color](wiki/Style-Parameters#wiki-color) - color scales
* [data](wiki/Style-Parameters#wiki-data) - data nodes
* [font](wiki/Style-Parameters#wiki-font) - global fonts
* [group](wiki/Style-Parameters#wiki-group) - node grouping
* [icon](wiki/Style-Parameters#wiki-icon) - icon type
* [info](wiki/Style-Parameters#wiki-info) - "error" text
* [labels](wiki/Style-Parameters#wiki-labels) - node text
* [legend](wiki/Style-Parameters#wiki-legend) - legend styles
* [links](wiki/Style-Parameters#wiki-links) - network connections
* [highlight](wiki/Style-Parameters#wiki-highlight) - highlight colors
* [rendering](wiki/Style-Parameters#wiki-rendering) - SVG line rendering
* [ticks](wiki/Style-Parameters#wiki-ticks) - axis ticks
* [timing](wiki/Style-Parameters#wiki-timing) - transition durations
* [timeline](wiki/Style-Parameters#wiki-timeline) - timeline styles
* [title](wiki/Style-Parameters#wiki-title) - visualization title
* [tooltip](wiki/Style-Parameters#wiki-tooltip) - data tooltip

##[Style Sheets](wiki/Style-Sheets)
* [default](wiki/Style-Sheets#wiki-default) - default **D3plus** style