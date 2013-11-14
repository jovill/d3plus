This section is to help you get acquainted with **D3plus**. It is highly recommended that you are at least somewhat familiar with [D3](http://d3js.org/) before using **D3plus**, although it is not necessary. If you would like a crash course in [D3](http://d3js.org/), we recommend this tutorial: [Three Little Circles](http://mbostock.github.io/d3/tutorial/circle.html)
##<a name="installation" href="#installing">#</a> Installing
Download the latest versions of D3plus (directory includes all dependencies):

* <http://d3plus.org/d3plus.v1.zip>

Note that because we will be running these files locally, our browser will raise errors when trying to do AJAX requests. The best way around this is to run a local server, if you have python installed this can be accomplished on the command line via:

    python -m SimpleHTTPServer 8888 &

or for Python 3+

    python -m http.server 8888 &

Once this is running, go to <http://localhost:8888/>.

Another alternative is using [MAMP] (http://www.mamp.info/) (on OSX) or [WampServer](http://www.wampserver.com/) (on Windows), which will install a local version of the Apache web server.

##<a name="viz" href="#wiki-viz">#</a> Creating a Visualization
Invoking a **D3plus** visualization is a simple 3-step process. First, you must create a container element in the page &#60;body&#62;:

```html
<div id="viz"></div> 
```

Then you must initialize the visualization:

```js
var visualization = d3plus.viz()
```

Finally, given we have a "data" variable as an array of objects, we give that "data" to the container and call the visualization:

```js
d3.select("#viz").datum(data).call(visualization)
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

d3.select("#viz").call(visualization)
```

There are many more variables you can (and in some cases, should) change on the visualization in order to get it looking the way you want it. See our variable documentation [here](wiki/Visualization-Variables).

##<a name="data" href="#wiki-data">#</a> Changing Data
But wait, now I want to change the data associated with my visualization! That's easy too, just pass the container new data and call the visualization again:

```js
d3.select("#viz").datum(new_data).call(visualization)
```

As you can probably tell by now, initiating a "[.call()](https://github.com/mbostock/d3/wiki/Selections#wiki-call)" on the container redraws the visualization.