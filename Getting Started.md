This section is to help you get acquainted with **D3plus**. It is highly recommended that you are at least somewhat familiar with [D3](http://d3js.org/) before using **D3plus**, although it is not necessary. If you would like a crash course in [D3](http://d3js.org/), we recommend this tutorial: [Three Little Circles](http://mbostock.github.io/d3/tutorial/circle.html)
##<a name="viz" href="#wiki-viz">#</a> Creating a Visualization
Invoking a **D3plus** visualization is a simple 3-step process. First, you must create a container element in the page &#60;body&#62;:

```html
<div id="container"></div> 
```

Then you must initialize the visualization:

```js
var visualization = d3plus.viz()
```

Finally, given we have a "data" variable as an array of objects, we give that "data" to the container and call the visualization:

```js
d3.select("#container").datum(data).call(visualization)
```

And that's it! You've got the working pieces of a **D3plus** visualization.

##<a name="variables" href="#wiki-variables">#</a> Changing Variables
Given you followed the tutorial above to create a **D3plus** visualization, your page should look, well, fairly empty and broken.

That is because there are some specific variables you need to call on the d3plus.viz() element in order to start displaying data. For example, if you want a tree map, you should have initialized your visualization like this:

```js
var visualization = d3plus.viz()
	.type("tree_map")
```

You would then call your visualization as normal. But what if you want to change from a Tree Map to a Stacked visualization after you've already drawn the Tree Map to the page? No problem, simply change the variables you want and then call it again!

```js
visualization.type("stacked")

d3.select("#container").call(visualization)
```

There are many more variables you can (and in some cases, should) change on the visualization in order to get it looking the way you want it. See our variable documentation [here](wiki/Visualization-Variables).

##<a name="data" href="#wiki-data">#</a> Changing Data
But wait, now I want to change the data associated with my visualization! That's easy too, just pass the container new data and call the visualization again:

```js
d3.select("#container").datum(new_data).call(visualization)
```

As you can probably tell by now, initiating a "[.call()](https://github.com/mbostock/d3/wiki/Selections#wiki-call)" on the container redraws the visualization.