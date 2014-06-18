**D3plus** features Utilities that can be used to help with some common javascript processes.

#### <a name="buckets" href="#buckets"> d3plus.util.buckets( *array* , *integer* )</a>

Given an *array* of 2 *numbers* and a desired *integer* of buckets, this method returns an *array* of values in between (and including) the original *array*. For example, if we wanted to define 5 buckets between `0` and `100`, we would call:

```js
var buckets = d3plus.util.buckets([0,100],5)
```

The array returned will look like this:

```js
[0, 25, 50, 75, 100]
```

#### <a name="child" href="#child">d3plus.util.child( *parent* , *child* )</a>

Returns a *boolean* whether or not the *child* element is inside of the *parent* element. This function is recursive, meaning it will return `true` if the element is a "grandchild", and so forth.

#### <a name="closest" href="#closest"> d3plus.util.closest( *array* , *number* )</a>

Given an *array* of *numbers* and a defined *number*, .**closest**() will search the *array* for the value closest to the defined *number*. Take this example:

```js
var closest = d3plus.util.closest([0,25,50,75,100],31)
```

The value returned would be `25`, as it is the closest numeric value in the given *array* to `31`

#### <a name="copy" href="#copy">d3plus.util.copy( *object* )</a>

This method clones an object and remove all symbolic links to the original object.

#### <a name="dataurl" href="#dataurl">d3plus.util.dataurl( *url* , *callback* )</a>

Given an image *url* and a callback *function*, .**dataurl**() will convert the image URL into a Base 64 data URL and return it to the *callback*.

This is used internally in the [[Legend]] to make it easier for sites using **D3plus** to download an SVG with the icons embedded in the file.

#### <a name="d3selection" href="#d3selection">d3plus.util.d3selection( *selection* )</a>

Returns a *boolean* whether or not the *selection* passed is an actual [d3.selection](https://github.com/mbostock/d3/wiki/Selections).

#### <a name="distances" href="#distances">d3plus.util.distances( *array* , *callback* )</a>

Returns an *array* listing all of the pixel distances between the X/Y positions of each node. If the nodes in the *array* passed to the function do not have "x" and "y" keys, you may pass a *callback* function to the utility that should return the node's X and Y coordinates as an *array* ([x,y]).

#### <a name="offset" href="#offset">d3plus.util.offset( *radians* , *distance* , *shape* )

Returns an *object* with X and Y pixel offsets based on an angle and the distance from the center. "Shape" should either be "square" or "circle".

This function is used internally by **D3plus** to position network edges on the, no pun intended, "edge" of the shape and not at the center.

#### <a name="uniques" href="#uniques">d3plus.util.uniques( *array* , *string* )</a>

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
