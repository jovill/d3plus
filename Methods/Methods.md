The visualizations and forms in **D3plus** have numerous methods that allow you to tweak to get the perfect visualization that suits your needs. Some methods are specific for only one visualization type, while other are used across multiple visualizations.

All of the available methods are listed to your right, ordered by most common to least common. :point_right:

## Global Behavior

Every method supports the following global behaviors in addition to their specific modifiers. In these examples, you would replace "**method**" with the specific name of the method you are invoking, such as "**id**" or "**data**".

#### <a name="value" href="#value">.method( *string* | *number* | *boolean* | *array* | *object* | *function* )</a>

When passing a value to a method, the method's main value will be set as the value passed (if accepted by the method).

The returned object will always be the **D3plus** element. This means that, when used correctly, every method is chainable.

#### <a name="callback" href="#callback">.method( value , *function* )</a>

Regardless of the type of data passed for the value, every method supports passing a *function* as the second variable. This *function* will be called whenever that method's value is set, whether internally by **D3plus** or externally by a user.

The *function* will be passed the proposed new value for the method, and it is up to the *function* to process the information.

If the *function* returns a value, **D3plus** will use that new value instead of the one it had originally passed to the *function*.

#### <a name="undefined" href="#undefined">.method( )</a>

Without passing anything to a method, the return object will be the method's current value (unless the method supports an *undefined* value, such as [[Draw]]).

This is helpful when you need to extract data from the visualization, such as the [[Focus Element]] of [[Rings]].

#### <a name="Object" href="#Object">.method( Object )</a>

When you pass a method the literal constructor element for an *Object*, **D3plus** will return a keyed object with everything it is storing for that specific method.

This is helpful when needing to debug **D3plus**, as well as to give a better understanding of what's going on under the hood.

## Available Methods

Certain methods are available across all of **D3plus**, while other are specific to certain functions. Here is a breakdown of each method, where it can be used, and the supporting documentation:

| Method | [[Visualizations]] | [[Forms]] | [[Text Wrapping]] | Documentation |
| :-- | :-: | :-: | :-: | :-- |
| .active | :white_check_mark: | :x: | :x: | [Segmenting Data](Segmenting-Data#active) |
| .aggs | :white_check_mark: | :x: | :x: | [Custom Aggregations](Custom-Aggregations) |
| .alt | :x: | :white_check_mark: | :x: | [Alt Text Parameters](Alt-Text-Parameters) |
| .attrs | :white_check_mark: | :x: | :x: | [Attribute Data](Attribute-Data) |
| .axes | :white_check_mark: | :x: | :x: | [Axis Parameters](Axis-Parameters#axes) |
| .background | :white_check_mark: | :x: | :x: | [Background](Background) |
| .color | :white_check_mark: | :white_check_mark: | :x: | [Color Parameters](Color-Parameters) |
| .container | :white_check_mark: | :white_check_mark: | :white_check_mark: | [Container Element](Container-Element) |
| .coords | :white_check_mark: | :x: | :x: | [Geography Data](Geography-Data) |
| .csv | :white_check_mark: | :x: | :x: | [CSV Export](CSV-Export) |
| .data | :white_check_mark: | :white_check_mark: | :x: | [Data Points](Data-Points) |
| .depth | :white_check_mark: | :x: | :x: | [Visible Depth](Visible-Depth) |
| .descs | :white_check_mark: | :x: | :x: | [Value Definitions](Value-Definitions) |
| .dev | :white_check_mark: | :white_check_mark: | :white_check_mark: | [Verbose Mode](Verbose-Mode) |
| .draw | :white_check_mark: | :white_check_mark: | :white_check_mark: | [Draw](Draw) |
| .edges | :white_check_mark: | :x: | :x: | [Edges List](Edges-List) |
| .error | :white_check_mark: | :x: | :x: | [Custom Error Message](Custom-Error-Message) |
| .focus | :white_check_mark: | :white_check_mark: | :x: | [Focus Element](Focus-Element) |
| .font | :white_check_mark: | :white_check_mark: | :x: | [Font Styles](Font-Styles) |
| .footer | :white_check_mark: | :x: | :x: | [Custom Footer](Custom-Footer) |
| .format | :white_check_mark: | :white_check_mark: | :white_check_mark: | [Value Formatting](Value-Formatting) |
| .height | :white_check_mark: | :white_check_mark: | :white_check_mark: | [Height](Height) |
| .history | :white_check_mark: | :x: | :x: | [User History](User-History) |
| .hover | :x: | :white_check_mark: | :x: | [Hover Element](Hover-Element) |
| .icon | :white_check_mark: | :white_check_mark: | :x: | [Icon Parameters](Icon-Parameters) |
| .id | :white_check_mark: | :white_check_mark: | :x: | [Unique ID](Unique-ID) |
| .keywords | :x: | :white_check_mark: | :x: | [Keyword Parameters](Keyword-Parameters) |
| .labels | :white_check_mark: | :x: | :x: | [Data Labels](Data-Labels) |
| .legend | :white_check_mark: | :x: | :x: | [Legend](Legend) |
| .links | :white_check_mark: | :x: | :x: | [Link Styles](Link-Styles) |
| .margin | :white_check_mark: | :x: | :x: | [Outer Margins](Outer-Margins) |
| .messages | :white_check_mark: | :x: | :x: | [Status Messages](Status-Messages) |
| .nodes | :white_check_mark: | :x: | :x: | [Node Positions](Node-Positions) |
| .open | :x: | :white_check_mark: | :x: | [Open](Open) |
| .order | :white_check_mark: | :white_check_mark: | :x: | [Data Ordering](Data-Ordering) |
| .remove | :x: | :white_check_mark: | :x: | [Remove](Remove) |
| .resize | :x: | :x: | :white_check_mark: | [Automatic Resizing](Automatic Resizing) |
| .search | :x: | :white_check_mark: | :x: | [Search Box](Search-Box) |
| .select | :x: | :white_check_mark: | :x: | [Selecting Elements](Selecting-Elements) |
| .selectAll | :x: | :white_check_mark: | :x: | [Selecting Elements](Selecting-Elements#selectall) |
| .shape | :white_check_mark: | :x: | :white_check_mark: | [Data Shapes](Data-Shapes) |
| .size | :white_check_mark: | :x: | :white_check_mark: | [Size Parameters](Size-Parameters) |
| .temp | :white_check_mark: | :x: | :x: | [Segmenting Data](Segmenting-Data#temp) |
| .text | :white_check_mark: | :white_check_mark: | :white_check_mark: | [Text Parameters](Text-Parameters) |
| .time | :white_check_mark: | :x: | :x: | [Time Parameters](Time-Parameters) |
| .timeline | :white_check_mark: | :x: | :x: | [Timeline](Timeline) |
| .timing | :white_check_mark: | :white_check_mark: | :x: | [Animation Timing](Animation-Timing) |
| .title | :white_check_mark: | :white_check_mark: | :x: | [Custom Titles](Custom-Titles) |
| .tooltip | :white_check_mark: | :x: | :x: | [Tooltip Parameters](Tooltip-Parameters) |
| .total | :white_check_mark: | :x: | :x: | [Segmenting Data](Segmenting-Data#total) |
| .type | :white_check_mark: | :white_check_mark: | :x: | [Output Type](Output-Type) |
| .ui | :white_check_mark: | :white_check_mark: | :x: | [Interface Elements](Interface-Elements) |
| .width | :white_check_mark: | :white_check_mark: | :white_check_mark: | [Width](Width) |
| .x | :white_check_mark: | :x: | :x: | [Axis Parameters](Axis-Parameters) |
| .y | :white_check_mark: | :x: | :x: | [Axis Parameters](Axis-Parameters) |
| .zoom | :white_check_mark: | :x: | :x: | [Zooming](Zooming) |
