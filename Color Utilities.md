**D3plus** features a set of methods that help manipulate colors to best display your visualizations. These methods may be used outside of the normal constraints of the visualizations to help in dynamic web design.

***

<a name="darker" href="#wiki-darker">#</a> color.**darker**(*color*[, *increment*])

This method takes a *color* and darkens it slightly. If the desired output is either too dark or too light for your liking, you can pass an *increment* (between <code>**0**</code> and <code>**1**</code>) as a second variable.

***

<a name="legible" href="#wiki-legible">#</a> color.**legible**(*color*)

If you are going to be placing text on a white background, but are worried that the dynamic text *color* may be too light to read, pass it through this method. .**legible**() will take a *color* and darken it until it is dark enough to be read on a white background. Look at this example:

```js
var color = d3plus.color.legible("#e6f5ff")
```

Here, the color that is returned is <font color='#0a78c2'>**#0a78c2**</font>, because the original color <font color='#e6f5ff'>**#e6f5ff**</font> is almost illegible on a white background.

***

<a name="lighter" href="#wiki-lighter">#</a> color.**lighter**(*color*[, *increment*])

This method takes a *color* and lightens it slightly. If the desired output is either too light or too dark for your liking, you can pass an *increment* (between <code>**0**</code> and <code>**1**</code>) as a second variable.

***

<a name="mix" href="#wiki-mix">#</a> color.**mix**(*color1*,*color2*,*opacity1*,*opacity2*)

Mixes two hexadecimal colors and returns the new mixed hexadecimal value. Opacity values must be between <code>**0**</code> and <code>**1**</code>, and when they are not specified they are set to <code>**1**</code>.

***

<a name="random" href="#wiki-random">#</a> color.**random**()

Returns a random 6-digit hexidecimal color, as a string, using [d3.scale.category20()](https://github.com/mbostock/d3/wiki/Ordinal-Scales#wiki-category20b).

<a name="random" href="#wiki-random">#</a> color.**random**(**value**)

When passed a value (either a *string* or *number*), .**random**() will return a color tied to the specific **value**.

***

<a name="text" href="#wiki-text">#</a> color.**text**(*color*)

This method will analyze the *color* passed to it and return either <code>**#ffffff**</code> or <code>**#444444**</code> depending on the color's hue, saturation, and luminosity. Take this example:

```js
var color = d3plus.color.text("#da251d")
```

In this case, <code>**#ffffff**</code> will be returned because the color <font color='#da251d'>**#da251d**</font> is dark enough to display white text on top of it. On the other hand...

```js
var color = d3plus.color.text("#d1ff00")
```

...the color <font color='#d1ff00'>**#d1ff00**</font> returns <code>**#333333**</code>, because it is too light to have legible white text placed on top of it.
