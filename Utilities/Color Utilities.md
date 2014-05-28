**D3plus** features a set of methods that help manipulate colors to best display your visualizations. These methods may be used outside of the normal constraints of the visualizations to help in dynamic web design.

#### <a name="darker" href="#wiki-darker">d3plus.color.darker( *color* [ , *increment* ] )</a>

This method takes a *color* and darkens it slightly. If the desired output is either too dark or too light for your liking, you can pass an *increment* (between ```0``` and ```1```) as a second variable.

#### <a name="legible" href="#wiki-legible">d3plus.color.legible( *color* )</a>

If you are going to be placing text on a white background, but are worried that the dynamic text *color* may be too light to read, pass it through this method. .**legible**() will take a *color* and darken it until it is dark enough to be read on a white background. Look at this example:

```js
var color = d3plus.color.legible("#e6f5ff")
```

Here, the color that is returned is ```#0a78c2```, because the original color ```#e6f5ff``` is almost illegible on a white background.

#### <a name="lighter" href="#wiki-lighter">d3plus.color.lighter( *color* [ , *increment* ] )</a>

This method takes a *color* and lightens it slightly. If the desired output is either too light or too dark for your liking, you can pass an *increment* (between ```0``` and ```1```) as a second variable.

#### <a name="mix" href="#wiki-mix">d3plus.color.mix( *color1* , *color2* [ , *opacity1* , *opacity2* ] )

Mixes two hexadecimal colors and returns the new mixed hexadecimal value. Opacity values must be between ```0``` and ```1```, and when they are not specified they are set to ```1```.

#### <a name="random" href="#wiki-random">d3plus.color.random( )</a>

Returns a random 6-digit hexidecimal color, as a string, using [d3.scale.category20()](https://github.com/mbostock/d3/wiki/Ordinal-Scales#wiki-category20b).

#### <a name="random" href="#wiki-random">d3plus.color.random( *value* )</a>

When passed a value (either a *string* or *number*), .**random**() will return a color tied to the specific **value**.

#### <a name="text" href="#wiki-text">d3plus.color.text( *color* )</a>

This method will analyze the *color* passed to it and return either ```#ffffff``` or ```#444444``` depending on the color's hue, saturation, and luminosity. Take this example:

```js
var color = d3plus.color.text("#da251d")
```

In this case, ```#ffffff``` will be returned because the color ```#da251d``` is dark enough to display white text on top of it. On the other hand...

```js
var color = d3plus.color.text("#d1ff00")
```

...the color ```#d1ff00``` returns ```#333333```, because it is too light to have legible white text placed on top of it.