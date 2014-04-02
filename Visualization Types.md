**D3plus** currently features 8 different visualization types. Here are overviews for all of them.

***

###<a name="bubbles" href="#wiki-bubbles">#</a> Bubbles

Draws data as bubbles that can be grouped together. Here are the specific features of **D3plus** that are supported:

|Feature|Description|
|---|---|
|Shape Fill|Bubbles can be filled like pie charts using the [.**active**()](Visualization-Methods#active), [.**temp**()](Visualization-Methods#temp), and [.**total**()](Visualization-Methods#total) methods.|
|Static Tooltip|When small tooltips are created, they will be anchored to each node and not follow the X and Y position of the mouse cursor.|
|Supported Shapes|Bubbles supports the following shapes from the [.**shape**()](Visualization-Methods#shape) method:<br>**"circle", "donut"**|

***

###<a name="chart" href="#wiki-chart">#</a> Chart

A standard X and Y plot. This is the basis for the [Line Plot](#line) and [Stacked Area](#stacked) visualizations. Here are the specific features of **D3plus** that are supported:

|Feature|Description|
|---|---|
|Required Keys|Chart requires the following keys to be set: [.**x**()](Visualization-Methods#x), [.**y**()](Visualization-Methods#y)|
|Shape Fill|Nodes can be filled like pie charts using the [.**active**()](Visualization-Methods#active), [.**temp**()](Visualization-Methods#temp), and [.**total**()](Visualization-Methods#total) methods.|
|Static Tooltip|When small tooltips are created, they will be anchored to each node and not follow the X and Y position of the mouse cursor.|
|Supported Shapes|Chart supports the following shapes from the [.**shape**()](Visualization-Methods#shape) method:<br>**"circle", "donut", "line", "square", "area"**|

***

###<a name="geo_map" href="#wiki-geo_map">#</a> Geo Map

A geographical map colored by data. Here are the specific features of **D3plus** that are supported:

|Feature|Description|
|---|---|
|Required Keys|Geo Map requires the following keys to be set: [.**color**()](Visualization-Methods#color), [.**coords**()](Visualization-Methods#coords)|
|Required Libraries|Geo Map requires the following external libraries to be loaded: [TopoJSON](Dependencies#topojson)|
|Follow Tooltip|When small tooltips are created, they will be anchored to the X and Y position of the mouse cursor.|
|Supported Shapes|Chart supports the following shapes from the [.**shape**()](Visualization-Methods#shape) method:<br>**"coords"**|

***

###<a name="line" href="#wiki-line">#</a> Line Plot

A line plot that builds off of the capabilities of the [Chart](#chart). Here are the specific features of **D3plus** that are supported:

|Feature|Description|
|---|---|
|Required Keys|Chart requires the following keys to be set: [.**x**()](Visualization-Methods#x), [.**y**()](Visualization-Methods#y)|
|Static Tooltip|When small tooltips are created, they will be anchored to each node and not follow the X and Y position of the mouse cursor.|
|Supported Shapes|Chart supports the following shapes from the [.**shape**()](Visualization-Methods#shape) method:<br>**"line"**|

***

###<a name="network" href="#wiki-network">#</a> Network

A static network of nodes and links. Here are the specific features of **D3plus** that are supported:

|Feature|Description|
|---|---|
|Required Keys|Chart requires the following keys to be set: [.**nodes**()](Visualization-Methods#nodes), [.**links**()](Visualization-Methods#links)|
|Static Tooltip|When small tooltips are created, they will be anchored to each node and not follow the X and Y position of the mouse cursor.|
|Supported Shapes|Chart supports the following shapes from the [.**shape**()](Visualization-Methods#shape) method:<br>**"circle", "square", "donut"**|

***

###<a name="rings" href="#wiki-rings">#</a> Rings

A way of viewing a network focused around 1 node. With **Rings**, nodes are positioned as radiating outwards from the focused nodes, showing both primary and secondary connections. Here are the specific features of **D3plus** that are supported:

|Feature|Description|
|---|---|
|Required Keys|Chart requires the following keys to be set: [.**focus**()](Visualization-Methods#focus), [.**links**()](Visualization-Methods#links)|
|Static Tooltip|When small tooltips are created, they will be anchored to each node and not follow the X and Y position of the mouse cursor.|
|Supported Shapes|Chart supports the following shapes from the [.**shape**()](Visualization-Methods#shape) method:<br>**"circle", "square", "donut"**|

***

###<a name="scatter" href="#wiki-scatter">#</a> Scatter

A scatter plot that builds off of the capabilities of the [Chart](#chart). Here are the specific features of **D3plus** that are supported:

|Feature|Description|
|---|---|
|Required Keys|Chart requires the following keys to be set: [.**x**()](Visualization-Methods#x), [.**y**()](Visualization-Methods#y)|
|Static Tooltip|When small tooltips are created, they will be anchored to each node and not follow the X and Y position of the mouse cursor.|
|Supported Shapes|Chart supports the following shapes from the [.**shape**()](Visualization-Methods#shape) method:<br>**"circle", "square", "donut"**|

***

###<a name="stacked" href="#wiki-stacked">#</a> Stacked Area

A stacked area chart that builds off of the capabilities of the [Chart](#chart). Here are the specific features of **D3plus** that are supported:

|Feature|Description|
|---|---|
|Required Keys|Chart requires the following keys to be set: [.**x**()](Visualization-Methods#x), [.**y**()](Visualization-Methods#y)|
|Static Tooltip|When small tooltips are created, they will be anchored to each area and not follow the X and Y position of the mouse cursor.|
|Supported Shapes|Chart supports the following shapes from the [.**shape**()](Visualization-Methods#shape) method:<br>**"area"**|

***

###<a name="tree_map" href="#wiki-tree_map">#</a> Tree Map

A share view of hierarchical data. Here are the specific features of **D3plus** that are supported:

|Feature|Description|
|---|---|
|Required Keys|Chart requires the following keys to be set: [.**size**()](Visualization-Methods#size)|
|Follow Tooltip|When small tooltips are created, they will be anchored to the X and Y position of the mouse cursor.|
|Supported Shapes|Chart supports the following shapes from the [.**shape**()](Visualization-Methods#shape) method:<br>**"square"**|
