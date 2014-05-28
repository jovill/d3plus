The visualizations and forms in **D3plus** have numerous methods that allow you to tweak to get the perfect visualization that suits your needs. Some methods are specific for only one visualization type, while other are used across multiple visualizations.

All of the available methods are listed to your right, ordered by most common to least common. :point_right:

## Global Behavior

Every method supports the following global behaviors in addition to their specific modifiers. In these examples, you would replace "**method**" with the specific name of the method you are invoking, such as "**id**" or "**data**".

#### <a name="value" href="#wiki-value">.method( *string* | *number* | *boolean* | *array* | *object* | *function* )</a>

When passing a value to a method, the method's main value will be set as the value passed (if accepted by the method).

The returned object will always be the **D3plus** element. This means that, when used correctly, every method is chainable.

#### <a name="callback" href="#wiki-callback">.method( value , *function* )</a>

Regardless of the type of data passed for the value, every method supports passing a *function* as the second variable. This *function* will be called whenever that method's value is changed, whether internally by **D3plus** or externally by a user.

The *function* will be passed the proposed new value for the method, and it is up to the *function* to process the information.

If the *function* returns a value, **D3plus** will use that new value instead of the one it had originally passed to the *function*.

#### <a name="undefined" href="#wiki-undefined">.method( )</a>

Without passing anything to a method, the return object will be the method's current value (unless the method supports an *undefined* value, such as [[Draw]]).

This is helpful when you need to extract data from the visualization, such as the [[Focus Element]] of [[Rings]] or to examine the current [[Data]] array.

#### <a name="Object" href="#wiki-Object">.method( Object )</a>

When you pass a method the literal constructor element for an *Object*, **D3plus** will return a keyed object with everything it is storing for that specific method.

This is helpful when needing to debug **D3plus**, as well as to give a better understanding of what's going on under the hood.

## Available Methods

Certain methods are available across all of **D3plus**, while other are specific to either Visualizations or Forms. Here is a breakdown of each method and where it can be used:

| Method | Visualizations | Forms |
| --- | :-: | :-: |
| [.active( )](wiki/Segmenting-Data#active) | :white_check_mark: | :x: |
| [.aggs( )](wiki/Custom-Aggregations) | :white_check_mark: | :x: |
| [.alt( )](wiki/Alt-Text-Parameters) | :x: | :white_check_mark: |
| [.attrs( )](wiki/Attribute-Data) | :white_check_mark: | :x: |
| [.axes( )](wiki/Axis-Parameters#axes) | :white_check_mark: | :x: |
| [.background( )](wiki/Background) | :white_check_mark: | :x: |
| [.color( )](wiki/Color-Parameters) | :white_check_mark: | :white_check_mark: |
| [.container( )](wiki/Container-Element) | :white_check_mark: | :white_check_mark: |
| [.coords( )](wiki/Geography-Data) | :white_check_mark: | :x: |
| [.csv( )](wiki/CSV-Export) | :white_check_mark: | :x: |
| [.data( )](wiki/Data-Points) | :white_check_mark: | :white_check_mark: |
| [.depth( )](wiki/Visible-Depth) | :white_check_mark: | :x: |
| [.descs( )](wiki/Value-Definitions) | :white_check_mark: | :x: |
| [.dev( )](wiki/Verbose-Mode) | :white_check_mark: | :white_check_mark: |
| [.draw( )](wiki/Draw) | :white_check_mark: | :white_check_mark: |
| [.edges( )](wiki/Edges-List) | :white_check_mark: | :x: |
| [.error( )](wiki/Custom-Error-Message) | :white_check_mark: | :x: |
| [.focus( )](wiki/Focus-Element) | :white_check_mark: | :white_check_mark: |
| [.font( )](wiki/Font-Styles) | :white_check_mark: | :white_check_mark: |
| [.footer( )](wiki/Custom-Footer) | :white_check_mark: | :x: |
| [.format( )](wiki/Value-Formatting) | :white_check_mark: | :white_check_mark: |
| [.height( )](wiki/Height) | :white_check_mark: | :white_check_mark: |
| [.history( )](wiki/User-History) | :white_check_mark: | :x: |
| [.hover( )](wiki/Hover-Element) | :x: | :white_check_mark: |
| [.icon( )](wiki/Icon-Parameters) | :white_check_mark: | :white_check_mark: |
| [.id( )](wiki/Unique-ID) | :white_check_mark: | :white_check_mark: |
| [.keywords( )](wiki/Keyword-Parameters) | :x: | :white_check_mark: |
| [.labels( )](wiki/Data-Labels) | :white_check_mark: | :x: |
| [.legend( )](wiki/Legend) | :white_check_mark: | :x: |
| [.links( )](wiki/Link-Styles) | :white_check_mark: | :x: |
| [.margin( )](wiki/Outer-Margins) | :white_check_mark: | :x: |
| [.messages( )](wiki/Status-Messages) | :white_check_mark: | :x: |
| [.nodes( )](wiki/Node-Positions) | :white_check_mark: | :x: |
| [.open( )](wiki/Open) | :x: | :white_check_mark: |
| [.order( )](wiki/Data-Ordering) | :white_check_mark: | :white_check_mark: |
| [.remove( )](wiki/Remove) | :x: | :white_check_mark: |
| [.search( )](wiki/Search-Box) | :x: | :white_check_mark: |
| [.select( )](wiki/Selecting-Elements) | :x: | :white_check_mark: |
| [.selectAll( )](wiki/Selecting-Elements#selectall) | :x: | :white_check_mark: |
| [.shape( )](wiki/Data-Shapes) | :white_check_mark: | :x: |
| [.size( )](wiki/Size-Parameters) | :white_check_mark: | :x: |
| [.temp( )](wiki/Segmenting-Data#temp) | :white_check_mark: | :x: |
| [.text( )](wiki/Text-Parameters) | :white_check_mark: | :white_check_mark: |
| [.time( )](wiki/Time-Parameters) | :white_check_mark: | :x: |
| [.timeline( )](wiki/Timeline) | :white_check_mark: | :x: |
| [.timing( )](wiki/Animation-Timing) | :white_check_mark: | :white_check_mark: |
| [.title( )](wiki/Custom-Titles) | :white_check_mark: | :white_check_mark: |
| [.tooltip( )](wiki/Tooltip-Parameters) | :white_check_mark: | :x: |
| [.total( )](wiki/Segmenting-Data#total) | :white_check_mark: | :x: |
| [.type( )](wiki/Output-Type) | :white_check_mark: | :white_check_mark: |
| [.ui( )](wiki/Interface-Elements) | :white_check_mark: | :white_check_mark: |
| [.width( )](wiki/Width) | :white_check_mark: | :white_check_mark: |
| [.x( )](wiki/Axis-Parameters) | :white_check_mark: | :x: |
| [.y( )](wiki/Axis-Parameters) | :white_check_mark: | :x: |
| [.zoom( )](wiki/Zooming) | :white_check_mark: | :x: |
