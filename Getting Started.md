This section is to help you get acquainted with **D3plus**. It is highly recommended that you are at least somewhat familiar with [D3](http://d3js.org/) before using **D3plus**, although it is not necessary. If you would like a crash course in [D3](http://d3js.org/), we recommend this tutorial: [Three Little Circles](http://mbostock.github.io/d3/tutorial/circle.html)

##<a name="setup" href="#setup">#</a> Environment Setup

Download the latest versions of D3plus (directory includes all dependencies):

* <http://d3plus.org/d3plus.v1.zip>

Note that because we will be running these files locally, our browser will raise errors when trying to do AJAX requests. The best way around this is to run a local server, if you have python installed this can be accomplished on the command line via:

```js
python -m SimpleHTTPServer 8888 &
```

or for Python 3+

```js
python -m http.server 8888 &
```

Once this is running, go to <http://localhost:8888/>.

Another alternative is using [MAMP](http://www.mamp.info/) (on OSX) or [WampServer](http://www.wampserver.com/) (on Windows), which will install a local version of the Apache web server.

##<a name="viz" href="#wiki-viz">#</a> Creating a Visualization

To initialize a **D3plus** visualization, you must first create a container element in the page &#60;body&#62;:

```html
<div id="viz"></div> 
```

Then, you must initialize the visualization:

```js
var visualization = d3plus.viz()
```

Finally, given we have a "data" variable as an array of objects, we pass both that "data" and our container element (using standard [D3 Selection Methods](https://github.com/mbostock/d3/wiki/Selections#selecting-elements)) to the visualization:

```js
visualization
	.data(data)
	.container("#viz")
```

And that's it! All you have to do now is invoke the [.**draw**()](Visualization-Methods#draw) method to draw the visualization on the page.

```js
visualization.draw()
```

##<a name="variables" href="#wiki-variables">#</a> Changing Variables
Given you followed the tutorial above to create a **D3plus** visualization, your page should look, well, fairly empty and broken.

That is because there are some specific methods you should invoke on your visualization that will tell it a little more about your data and what you would like to display. For example, if you want to display a [Tree Map](Visualization-Types#tree_map) and your data is keyed with an id of "person", you would call the following methods:

```js
visualization
	.type("tree_map")
	.id("person")
```

Once you set the [methods](Visualization-Methods) you need, you will just need to invoke the [.**draw**()](Visualization-Methods#draw) method to display your changes.