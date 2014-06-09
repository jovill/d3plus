The visualizations and forms in **D3plus** have numerous methods that allow you to tweak to get the perfect visualization that suits your needs. Some methods are specific for only one visualization type, while other are used across multiple visualizations.

All of the available methods are listed to your right, ordered by most common to least common. :point_right:

## Global Behavior

Every method supports the following global behaviors in addition to their specific modifiers. In these examples, you would replace "**method**" with the specific name of the method you are invoking, such as "**id**" or "**data**".

#### <a name="value" href="#value">.method( *string* | *number* | *boolean* | *array* | *object* | *function* )</a>

When passing a value to a method, the method's main value will be set as the value passed (if accepted by the method).

The returned object will always be the **D3plus** element. This means that, when used correctly, every method is chainable.

#### <a name="callback" href="#callback">.method( value , *function* )</a>

Regardless of the type of data passed for the value, every method supports passing a *function* as the second variable. This *function* will be called whenever that method's value is changed, whether internally by **D3plus** or externally by a user.

The *function* will be passed the proposed new value for the method, and it is up to the *function* to process the information.

If the *function* returns a value, **D3plus** will use that new value instead of the one it had originally passed to the *function*.

#### <a name="undefined" href="#undefined">.method( )</a>

Without passing anything to a method, the return object will be the method's current value (unless the method supports an *undefined* value, such as [[Draw]]).

This is helpful when you need to extract data from the visualization, such as the [[Focus Element]] of [[Rings]].

#### <a name="Object" href="#Object">.method( Object )</a>

When you pass a method the literal constructor element for an *Object*, **D3plus** will return a keyed object with everything it is storing for that specific method.

This is helpful when needing to debug **D3plus**, as well as to give a better understanding of what's going on under the hood.

## Available Methods

Certain methods are available across all of **D3plus**, while other are specific to either Visualizations or Forms. Here is a breakdown of each method and where it can be used:

| Method | Visualizations | Forms |
| --- | :-: | :-: |
| [.active( )](Segmenting-Data#active) | :white_check_mark: | :x: |
| [.aggs( )](Custom-Aggregations) | :white_check_mark: | :x: |
| [.alt( )](Alt-Text-Parameters) | :x: | :white_check_mark: |
| [.attrs( )](Attribute-Data) | :white_check_mark: | :x: |
| [.axes( )](Axis-Parameters#axes) | :white_check_mark: | :x: |
| [.background( )](Background) | :white_check_mark: | :x: |
| [.color( )](Color-Parameters) | :white_check_mark: | :white_check_mark: |
| [.container( )](Container-Element) | :white_check_mark: | :white_check_mark: |
| [.coords( )](Geography-Data) | :white_check_mark: | :x: |
| [.csv( )](CSV-Export) | :white_check_mark: | :x: |
| [.data( )](Data-Points) | :white_check_mark: | :white_check_mark: |
| [.depth( )](Visible-Depth) | :white_check_mark: | :x: |
| [.descs( )](Value-Definitions) | :white_check_mark: | :x: |
| [.dev( )](Verbose-Mode) | :white_check_mark: | :white_check_mark: |
| [.draw( )](Draw) | :white_check_mark: | :white_check_mark: |
| [.edges( )](Edges-List) | :white_check_mark: | :x: |
| [.error( )](Custom-Error-Message) | :white_check_mark: | :x: |
| [.focus( )](Focus-Element) | :white_check_mark: | :white_check_mark: |
| [.font( )](Font-Styles) | :white_check_mark: | :white_check_mark: |
| [.footer( )](Custom-Footer) | :white_check_mark: | :x: |
| [.format( )](Value-Formatting) | :white_check_mark: | :white_check_mark: |
| [.height( )](Height) | :white_check_mark: | :white_check_mark: |
| [.history( )](User-History) | :white_check_mark: | :x: |
| [.hover( )](Hover-Element) | :x: | :white_check_mark: |
| [.icon( )](Icon-Parameters) | :white_check_mark: | :white_check_mark: |
| [.id( )](Unique-ID) | :white_check_mark: | :white_check_mark: |
| [.keywords( )](Keyword-Parameters) | :x: | :white_check_mark: |
| [.labels( )](Data-Labels) | :white_check_mark: | :x: |
| [.legend( )](Legend) | :white_check_mark: | :x: |
| [.links( )](Link-Styles) | :white_check_mark: | :x: |
| [.margin( )](Outer-Margins) | :white_check_mark: | :x: |
| [.messages( )](Status-Messages) | :white_check_mark: | :x: |
| [.nodes( )](Node-Positions) | :white_check_mark: | :x: |
| [.open( )](Open) | :x: | :white_check_mark: |
| [.order( )](Data-Ordering) | :white_check_mark: | :white_check_mark: |
| [.remove( )](Remove) | :x: | :white_check_mark: |
| [.search( )](Search-Box) | :x: | :white_check_mark: |
| [.select( )](Selecting-Elements) | :x: | :white_check_mark: |
| [.selectAll( )](Selecting-Elements#selectall) | :x: | :white_check_mark: |
| [.shape( )](Data-Shapes) | :white_check_mark: | :x: |
| [.size( )](Size-Parameters) | :white_check_mark: | :x: |
| [.temp( )](Segmenting-Data#temp) | :white_check_mark: | :x: |
| [.text( )](Text-Parameters) | :white_check_mark: | :white_check_mark: |
| [.time( )](Time-Parameters) | :white_check_mark: | :x: |
| [.timeline( )](Timeline) | :white_check_mark: | :x: |
| [.timing( )](Animation-Timing) | :white_check_mark: | :white_check_mark: |
| [.title( )](Custom-Titles) | :white_check_mark: | :white_check_mark: |
| [.tooltip( )](Tooltip-Parameters) | :white_check_mark: | :x: |
| [.total( )](Segmenting-Data#total) | :white_check_mark: | :x: |
| [.type( )](Output-Type) | :white_check_mark: | :white_check_mark: |
| [.ui( )](Interface-Elements) | :white_check_mark: | :white_check_mark: |
| [.width( )](Width) | :white_check_mark: | :white_check_mark: |
| [.x( )](Axis-Parameters) | :white_check_mark: | :x: |
| [.y( )](Axis-Parameters) | :white_check_mark: | :x: |
| [.zoom( )](Zooming) | :white_check_mark: | :x: |
