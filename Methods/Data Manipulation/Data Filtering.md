Once your **D3plus** visualization has been passed data, a number of [[Methods]] allow the ability to only show specific slices of that data using [mute](#mute) and [solo](#solo) filters.

When both [mute](#mute) and [solo](#solo) parameters are passed to a given method, only the [solo](#solo) parameter is used.

## <a name="mute" href="#wiki-mute">mute</a>

Muting data refers to the act of hiding specific data points. The data points that are muted will not be displayed on the screen. Many of the methods in **D3plus** can accept "mute" parameters. The "mute" parameter can accept any of the approved filtering values listed [here](#values).

## <a name="solo" href="#wiki-solo">solo</a>

Soloing data refers to the act of only showing specific data points. The data points that are soloed will be the only nodes displayed on the screen. Many of the methods in **D3plus** can accept "solo" parameters. The "solo" parameter can accept any of the approved filtering values listed [here](#values).

## <a name="values" href="#wiki-values">values</a>

Both [mute](#mute) and [solo](#solo) parameters accept the same type of values. They are:

#### <a name="value" href="#wiki-value">key value</a>

By passing only a *value*, the *value* will be added to the list of values to match. If the *value* passed is already present in the list, it will be removed from the list (an easy way to toggle filtering specific data points).

For example, to hide all data with a [[Unique ID]] of "Boston", we would call the following method:

```js
.id({ "mute" : "Boston" })
```

When filtering on the [[Unique ID]] method, all nesting levels are checked for matches (if nesting is applicable).

#### <a name="function" href="#wiki-function">function</a>

Additionally, you can pass functions as a way of filtering data. For example, to only show data with a [[size|Size Parameters]] greater than ```0.5```, where ```"weight"``` is our size value, we can pass this function to "solo":

```js
.size({ "solo" : function(node) {
	return node.weight > 0.5
}})
```

#### <a name="array" href="#wiki-array">array</a>

If you have multiple filters you would like to pass to a method, you can pass an array of values/functions. In this example, we will hide all data with a [[Unique ID]] matching 3 specific names:

```js
.id({ "mute" : [ "Alex" , "Dave" , "Mario" ] })
```

When passing an array to one of the filters, it will completely overwrite any previous filter parameters.

#### <a name="empty" href="#wiki-empty">empty array</a>

In order to reset all solo or mute data, you simply pass an empty array to the applicable method. In this example, we are resetting the solo for [[Unique ID]]:

```js
.id({ "solo" : [] })
```
