**D3plus** features Utilities that can be used to help with some common javascript processes.

#### <a name="buckets" href="#wiki-buckets"> d3plus.util.buckets( *array* , *integer* )</a>

Given an *array* of 2 *numbers* and a desired *integer* of buckets, this method returns an *array* of values in between (and including) the original *array*. For example, if we wanted to define 5 buckets between ```0``` and ```100```, we would call:

```js
var buckets = d3plus.util.buckets([0,100],5)
```

The array returned will look like this:

```js
[0, 25, 50, 75, 100]
```

#### <a name="child" href="#wiki-child">d3plus.util.child( *parent* , *child* )</a>

Returns a *boolean* whether or not the *child* element is inside of the *parent* element. This function is recursive, meaning it will return ```true``` if the element is a "grandchild", and so forth.

#### <a name="closest" href="#wiki-closest"> d3plus.util.closest( *array* , *number* )</a>

Given an *array* of *numbers* and a defined *number*, .**closest**() will search the *array* for the value closest to the defined *number*. Take this example:

```js
var closest = d3plus.util.closest([0,25,50,75,100],31)
```

The value returned would be ```25```, as it is the closest numeric value in the given *array* to ```31```

#### <a name="copy" href="#wiki-copy">d3plus.util.copy( *object* )</a>

This method clones an object and remove all symbolic links to the original object.

#### <a name="dataurl" href="#wiki-dataurl">d3plus.util.dataurl( *url* , *callback* )</a>

Given an image *url* and a callback *function*, .**dataurl**() will convert the image URL into a Base 64 data URL and return it to the *callback*.

This is used internally in the [[Legend]] to make it easier for sites using **D3plus** to download an SVG with the icons embedded in the file.

#### <a name="d3selection" href="#wiki-d3selection">d3plus.util.d3selection( *selection* )</a>

Returns a *boolean* whether or not the *selection* passed is an actual [d3.selection](https://github.com/mbostock/d3/wiki/Selections).

#### <a name="distances" href="#wiki-distances">d3plus.util.distances( *array* , *callback* )</a>

Returns an *array* listing all of the pixel distances between the X/Y positions of each node. If the nodes in the *array* passed to the function do not have "x" and "y" keys, you may pass a *callback* function to the utility that should return the node's X and Y coordinates as an *array* ([x,y]).

#### <a name="offset" href="#wiki-offset">d3plus.util.offset( *radians* , *distance* , *shape* )

Returns an *object* with X and Y pixel offsets based on an angle and the distance from the center. "Shape" should either be "square" or "circle".

This function is used internally by **D3plus** to position network edges on the, no pun intended, "edge" of the shape and not at the center.

#### <a name="uniques" href="#wiki-uniques">d3plus.util.uniques( *array* , *string* )</a>

Given an *array* of objects and a *string* to be used as a key, this method will return an array of the unique values for the given key that exist in the data *array*. In this example, we use  .**uniques**() to find the unique years available in the data:

```js
var obj = [
	{"year": 2005, "id": 1},
	{"year": 2006, "id": 1},
	{"year": 2006, "id": 2},
	{"year": 2010, "id": 1},
	{"year": 2010, "id": 2}
]

var uniques = d3plus.util.uniques(obj,"year")
```

The returned variable "uniques" looks like this:

```js
[ 2005 , 2006 , 2010 ]
```

#### <a name="wordwrap" href="#wiki-wordwrap">d3plus.util.wordwrap(*object*)</a>

The biggest utility of the bunch, this utility will wrap lines of SVG text to fit within specified bounds. The function accepts an *object* of specific parameters. Here are the available parameters and their defaults:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| font_max | When "resize" is set to ```true```, this defines the maximum allowed font size for the text. | *number* | ```40``` |
|font_min|When "resize" is set to ```true```, this defines the minimum allowed font size for the text. If the text is still too large to be wrapped, no text will be displayed.|*number*|```9```|
|height|The pixel height of the text area used to wrap the text. If the final wrapped text does not fit in the height allowed, the function will either move onto the next specified text to try (if an *array* was passed for "text") or it will place an ellipsis on the end of the last word to fit.|*number*|```20,000```|
|parent|The ```<text>``` element where the wrapped text will be placed. Each line of wrapped text becomes a ```<tspan>``` element inside of the parent element.| ```<text>```|```null```|
|resize|Whether or not .**wordwrap**() should try to resize the given text to fit into the defined  area. This can be seen in our [Tree Map](Visualization-Types#tree_map) visualization. When resize is set to ```false```, the wrapped text inherits its font size from its "parent"  element.|*boolean*|```false```|
|text|The text that will be wrapped. You can pass it a *string*, or an *array* of multiple strings to check. If the text in the first *string* of the *array* is too large to be wrapped, then the function will try the second *string*, and so on.|*string*, *array*|```null```|
|width|The pixel width of the text area used to wrap the text.|*number*|```20,000```|

Based on those variables, let's take a look at an example:

```html
<svg height="200px" width="400px">
	<text id="wrapText" font-size="24px"></text>
</svg>
```

Let's say we want to place the sentence "The quick brown fox jumps over the lazy dog" into that text element, but we know it is too long to fit. This is how we would invoke .**wordwrap**():

```js
var sentence = "The quick brown fox jumps over the lazy dog"

d3plus.util.wordwrap({
	"height": 200,
	"parent": d3.select("#wrapText"),
	"resize": false,
	"text": sentence,
	"width": 400
})
```

This would place our sentence inside of the ```<text>``` element, splitting it up into as many ```<tspan>``` elements as needed.
