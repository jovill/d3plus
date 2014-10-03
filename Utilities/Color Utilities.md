**d3plus** features a set of methods that help manipulate colors to best display your visualizations. These methods may be used outside of the normal constraints of the visualizations to help in dynamic web design.

### <a name="legible" href="#legible">d3plus.color.legible( *color* )</a>

If you are going to be placing text on a white background, but are worried that the dynamic text *color* may be too light to read, pass it through this method. .**legible**() will take a *color* and darken it until it is dark enough to be read on a white background. Look at this example:

| Make Colored Text Legible <br> on White Backgrounds | [D3plus.org](http://d3plus.org/examples/utilities/b3063df74711f4e69166/) |
| :-- | :-: |
| Here is an example page <br> showing how this function <br> behaves with various colors. | <a href="http://d3plus.org/examples/utilities/b3063df74711f4e69166/"><img src="https://gist.githubusercontent.com/davelandry/b3063df74711f4e69166/raw/thumbnail.png" width="150px"></a> |

Here, the color that is returned is `#0a78c2`, because the original color `#e6f5ff` is almost illegible on a white background.

### <a name="lighter" href="#lighter">d3plus.color.lighter( *color* [ , *increment* ] )</a>

This method takes a *color* and lightens it slightly. If the desired output is either too light or too dark for your liking, you can pass an *increment* (between `0` and `1`) as a second variable.

| Lighten Colors | [D3plus.org](http://d3plus.org/examples/utilities/53696917e5fd0964f91e/) |
| :-- | :-: |
| Here is an example page <br> showing how this function <br> behaves with various colors. | <a href="http://d3plus.org/examples/utilities/53696917e5fd0964f91e/"><img src="https://gist.githubusercontent.com/davelandry/53696917e5fd0964f91e/raw/thumbnail.png" width="150px"></a> |

### <a name="mix" href="#mix">d3plus.color.mix( *color1* , *color2* [ , *opacity1* , *opacity2* ] )

Mixes two hexadecimal colors and returns the new mixed hexadecimal value. Opacity values must be between `0` and `1`, and when they are not specified they are set to `1`.

### <a name="random" href="#random">d3plus.color.random( )</a>

Returns a random 6-digit hexidecimal color, as a string, using [d3.scale.category20()](https://github.com/mbostock/d3/wiki/Ordinal-Scales#category20b).

### <a name="random" href="#random">d3plus.color.random( *value* )</a>

When passed a value (either a *String* or *Number*), .**random**() will return a color tied to the specific **value**.

### <a name="sort" href="#sort">d3plus.color.sort( *a* , *b* )</a>

A sort comparator that sorts color values by hue.

### <a name="text" href="#text">d3plus.color.text( *color* )</a>

This method will analyze the *color* passed to it and return either `#ffffff` or `#444444` depending on the color's hue, saturation, and luminosity.

| Legible Text on <br> Colored Backgrounds | [D3plus.org](http://d3plus.org/examples/utilities/20a9042a60d87616e9ea/) |
| :-- | :-: |
| Here is an example page <br> showing how this function <br> behaves with various colors. | <a href="http://d3plus.org/examples/utilities/20a9042a60d87616e9ea/"><img src="https://gist.githubusercontent.com/davelandry/20a9042a60d87616e9ea/raw/thumbnail.png" width="150px"></a> |

### <a name="validate" href="#validate">d3plus.color.validate( *color* )

When passed a *String* value, this method will return `true` or `false` depending on if the value is a [valid CSS color string](http://www.w3schools.com/cssref/css_colors_legal.asp).
