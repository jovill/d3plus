#### <a name="selector" href="#wiki-selector">.container( *selector* )</a>

Tells **D3plus** which page element to build the visualization inside of. This is a required method for every visualization. We support all of the [D3 Selection Methods](https://github.com/mbostock/d3/Selections#selecting-elements), including D3 elements.

For example, to select an element with the ID of "box", you could say:

```js
.container( "#box" )
```

Or alternatively, you could also say:

```js
.container( d3.select("#box") )
```

Before creating a visualization, **D3plus** will remove all contents of the specified container element.
