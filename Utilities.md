**D3plus** features Utilities that can be used globally.
##<a name="rand_color" href="#rand_color">#</a> d3plus.utils.rand_color()
Returns a random 6-digit hexidecimal color, as a string, using [d3.scale.category20](https://github.com/mbostock/d3/wiki/Ordinal-Scales#wiki-category20).
##<a name="text_color" href="#text_color">#</a> d3plus.utils.text_color(color)
This utility will analyze the color passed to it, and return either #ffffff" or "#333333", depending on the color's hue, saturation, and luminosity. Take this example:

```js
var color = d3plus.utils.text_color("#da251d")
```

d3.plus.utils.text_color() returns **#ffffff** in this case, because the color <font color='#da251d'>**#da251d**</font> is dark enough to display white text on top of it. On the other hand...

```js
var color = d3plus.utils.text_color("#d1ff00")
```

...the color <font color='#d1ff00'>**#d1ff00**</font> returns <font color='#333333' background-color="#ff0000">**#333333**</font>, because it is too light to have legible white text on top of it.
##<a name="darken_color" href="#darken_color">#</a> d3plus.utils.darker_color(color)
If you are going to be placing text on a white background, but are worried that the dynamic text color may be too light to read, pass it through this function. This function will take a color and darken it until it is dark enough to be read on a white background. Look at this example:

```js
var color = d3plus.utils.darker_color("#e6f5ff")
```

Here, the color that is returned is <font color='#0a78c2'>**#0a78c2**</font>, because the original color <font color='#e6f5ff'>**#e6f5ff**</font> is almost illegible on a white background.
##<a name="uniques" href="#uniques">#</a> d3plus.utils.uniques(data,key)
Given an array of objects and a lookup key, this function will return an array of the unique values of the given key that exist in the data. Take this code as an example:

```js
var obj = [
	{"year": 2005},
	{"year": 2006},
	{"year": 2006},
	{"year": 2010},
	{"year": 2010}
]
var uniques = d3plus.utils.uniques(obj,"year")
```

The returned variable "uniques" looks like this:

```js
[2005, 2006, 2010]
```

##<a name="merge" href="#merge">#</a> d3plus.utils.merge(obj,obj)
Given any two objects, this function will merge the two objects together, creating a third new object. The values of the second object always overwrite the first. Take a look at this example:

```js
var obj1 = {"id": 3, "color": "#cc0000"}
var obj2 = {"id": 7, "name": "Alex"}
var obj3 = d3plus.utils.merge(obj1,obj2)
```

Here is what the newly created "obj3" variable looks like. Notice how the new object's "id" key is 7 and not 3. The second object's values always overwrite the first object's value.

```js
{"id": 7, "color": "#cc0000", "name": "Alex"}
```

This utility function is also helpful when you need to clone an object and remove all links to the original object. You would simply merge your object with an empty object:

```js
var object_clone = d3plus.utils.merge({},object)
```

##<a name="wordwrap" href="#wordwrap">#</a> d3plus.utils.wordwrap(params)
The biggest utility of the bunch, d3plus.utils.wordwrap() will wrap lines of SVG text to fit within specified bounds. The function accepts an object of parameters. Here are the available parameters and their defaults:

<table>
  <tr>
    <th>Key</th><th>Default Value</th><th>Supported Type(s)</th><th>Description</th>
  </tr>
  <tr>
    <td>text</td>
    <td>null (required)</td>
    <td>String, Array</td>
    <td>One of two required variables, which I think makes sense. This is the text that will be wrapped. You can pass it a string, or an array of multiple strings to check. If the first String in the Array is too large to be wrapped, then the function will try the second String, and so on.</td>
  </tr>
  <tr>
    <td>parent</td>
    <td>null (required)</td>
    <td>Javascript DOM Element</td>
    <td>The other required variable. This is the &#60;text&#62; element where the finished wrapped text will be placed. Each line of wrapped text becomes a &#60;tspan&#62; element inside of the parent element.</td>
  </tr>
  <tr>
    <td>width</td>
    <td>20,000</td>
    <td>Number</td>
    <td>The pixel width of the text area used to wrap the text.</td>
  </tr>
  <tr>
    <td>height</td>
    <td>20,000</td>
    <td>Number</td>
    <td>The pixel height of the text area used to wrap the text. If the final wrapped text does not fit in the height allowed, the function will either move onto the next specified text to try (if an Array was passed for texts) or it will place an ellipsis (...) on the end of the last word to fit.</td>
  </tr>
  <tr>
    <td>padding</td>
    <td>10</td>
    <td>Number</td>
    <td>The pixel padding of the text area defined by width and height used when wrapping the text.</td>
  </tr>
  <tr>
    <td>resize</td>
    <td>false</td>
    <td>Boolean</td>
    <td>Whether or not the function should try to resize the given text to fit into the defined text area. This can be seen in our default tree map visualization. When resize is set to false, the wrapped text inherits its font size from its parent &#60;text&#62; element.</td>
  </tr>
  <tr>
    <td>font_max</td>
    <td>40</td>
    <td>Number</td>
    <td>The maximum pixel height for the text when resizing is set to true.</td>
  </tr>
  <tr>
    <td>font_min</td>
    <td>10</td>
    <td>Number</td>
    <td>The minimum pixel height for the text when resizing is set to true.</td>
  </tr>
</table>

So based on those variables, let's take a look at an example:

```html
<svg height="200px" width="400px">
	<text id="wrapText" font-size="24px"></text>
</svg>
```

Let's say we want to place the sentence "The quick brown fox jumps over the lazy dog" into that text element, but we know it is too long to fit. This is how we would invoke the d3plus.utils.wordwrap() function:

```js
var sentence = "The quick brown fox jumps over the lazy dog"

d3plus.utils.wordwrap({
	"text": sentence,
	"parent": document.getElementById("wrapText"),
	"width": 400,
	"height": 200,
	"resize": false
})
```

This would place our sentence inside of the &#60;text&#62; element, splitting it up into as many &#60;tspan&#62; elements as needed.