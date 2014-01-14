Once your **D3plus** visualization has been passed [.**data**()](wiki/Visualization-Methods#data), a number of [methods](wiki/Visualization-Methods) allow the ability to only show specific slices of that data using [mute](#mute) and [solo](#solo) filters.

When both [mute](#mute) and [solo](#solo) parameters are passed to a given [method](wiki/Visualization-Methods), only the [solo](#solo) parameter is used.

##<a name="mute" href="#wiki-mute">#</a> **Mute**

Muting data refers to the act of hiding specific data points. The data points that are muted will not be displayed on the screen. Many of the [methods](wiki/Visualization-Methods) in **D3plus** can accept "mute" parameters. The "mute" parameter can accept any of the approved filtering values listed [here](#methods).

##<a name="solo" href="#wiki-solo">#</a> **Solo**

Soloing data refers to the act of only showing specific data points. The data points that are soloed will be the only nodes displayed on the screen. Many of the [methods](wiki/Visualization-Methods) in **D3plus** can accept "solo" parameters. The "solo" parameter can accept any of the approved filtering values listed [here](#methods).

##<a name="values" href="#wiki-values">#</a> **Values**

Both [mute](#mute) and [solo](#solo) parameters accept the same type of values. They are:

<a name="value" href="#wiki-value">#</a> *key value*

By passing only a **value**, the **value** will be added to the list of values to match. If the **value** passed is already present in the list, it will be removed from the list (an easy way to toggle filtering specific data points).

For example, to hide all data with an [.**id**()](wiki/Visualization-Methods#id) of "Boston", we would call the following method on your visualization named "viz":

```js
viz.id({"mute": "Boston"})
```

When filtering on the [.**id**()](wiki/Visualization-Methods#id) method, all nesting levels are checked for matches (if nesting is applicable).

<a name="function" href="#wiki-function">#</a> *function*

Additionally, you can pass functions as a way of filtering data. For example, to only show data with a [.**size**()](wiki/Visualization-Methods#size) greater than 0.5, where "value" is our key for [.**size**()](wiki/Visualization-Methods#size), we can pass this function to a visualization named "viz":

```js
function filter_active(node) {
	return node.value > 0.5;
}

viz.size({"solo": filter_active})
```

<a name="array" href="#wiki-array">#</a> *array*

If you have multiple filters you would like to pass to a [method](wiki/Visualization-Methods), you can pass an array of values/functions. In this example, we will hide all data with an [.**id**()](wiki/Visualization-Methods#id) matching either "Alex", "Dave", or "Mario":

```js
viz.id({"mute": ["Alex", "Dave", "Mario"]})
```