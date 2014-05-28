#### <a name="undefined" href="#wiki-undefined">.draw( )</a>

Draws the visualization inside of the specified [[Container Element]]. When the visualization gets drawn for the first time, or if the container has changed, all previous contents of the element will be removed.

This method should to be called after updating other methods in order to update the content being displayed.

If our [[Container Element]] has an id of ```"container"```, and our instance of ```d3plus.viz()``` is called ```visualization```, calling the draw method is the equivalent of saying:

```js
d3.select("#container").call(visualization)
```

Instead of having to select the container element every time we need to update the display, we can simply say:

```js
visualization.draw()
```
