A standard X and Y plot. This is the basis for the [Line Plot](#line) and [[Stacked Area]] visualizations. Here are the specific features of **D3plus** that are supported:

|Feature|Description|
|---|---|
|Required Keys|Chart requires the following keys to be set: [.**x**()](Visualization-Methods#x), [.**y**()](Visualization-Methods#y)|
|Shape Fill|Nodes can be filled like pie charts using the [.**active**()](Visualization-Methods#active), [.**temp**()](Visualization-Methods#temp), and [.**total**()](Visualization-Methods#total) methods.|
|Static Tooltip|When small tooltips are created, they will be anchored to each node and not follow the X and Y position of the mouse cursor.|
|Supported Shapes|Chart supports the following shapes from the [.**shape**()](Visualization-Methods#shape) method:<br>**"circle", "donut", "line", "square", "area"**|
