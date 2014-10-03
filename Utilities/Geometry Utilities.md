### <a name="largestRect" href="#largestRect">d3plus.geom.largestRect( *polygon* [, *options*] )

Finds the maximum area rectangle that fits inside a polygon. The polygon must be an array of two-dimensional arrays corresponding to the points of the polygon.

Returns the largest found rectangle as an object with the following attributes:
* width - the width of the rectangle
* height - the height of the rectangle
* cx - the x coordinate of the rectangle's center
* cy - the y coordinate of the rectangle's center
* angle - rotation angle in degrees. The anchor of rotation is the center point

Options is a dictionary of options with the following attributes:

#### angle
Specifies the rotation of the polygon. An angle of zero means that the longer side of the polygon (the width) will be aligned with the x axis.  An angle of +90 and/or -90 means that the longer side of the polygon (the width) will be aligned with the y axis. The accepted values are:
* a number between -90 and +90 specifying the angle of rotation of the polygon.
* a string which is parsed to a number
* an array of numbers, specifying the possible rotations of the polygon
* unspecified, which means the polygon can have any possible angle (default)

#### aspectRatio
The ratio between the width and the height of the rectangle, i.e. width/height. The parameter aspectRatio can be:
* a number
* a string which is parsed to a number
* an array of numbers, specifying the possible aspectRatios of the polygon

#### maxAspectRatio
The maximum aspect ratio (width/height). Default is 15.

#### nTries
The number of randomly drawn points inside the polygon which the algorithm explores as possible center points of the maximal rectangle. Default value is 20.

#### minWidth
The minimum width of the rectangle. Default is 0.

#### minHeight
The minimum height of the rectangle. Default is 0.

#### tolerance
The simplification tolerance factor. Should be between 0 and 1. Default is 0.02. Larger tolerance corresponds to more extensive simplification.

#### origin
The center point of the rectangle. If specified, the rectangle is fixed at that point, otherwise the algorithm optimizes across all possible points. The parameter origin can be:
* a two dimensional array specifying the x and y coordinate of the origin
* an array of two dimensional arrays specifying the the possible center points of the maximal rectangle.

### <a name="offset" href="#offset">d3plus.geom.offset( *radians* , *distance* [, *shape*] )

Returns an *Object* with X and Y pixel offsets based on an angle and the distance from the center. "Shape" should either be "square" or "circle".

This function is used internally by **d3plus** to position network edges on the, no pun intended, "edge" of the shape and not at the center.

### <a name="path2poly" href="#path2poly">d3plus.geom.path2poly( *path* )

Returns an *Array* of coordinates generated from a standard SVG *path*.
