#### <a name="array" href="#array">.ui( *array* )</a>

Creates UI elements, using [[Forms]], that help the user navigate [[Visualizations]]. The *array* of objects passed should contain methods and values, which correspond to how the UI element should behave.

For example, if you wanted to create a toggle that switches the "size" method from "export" to "import", you would pass the following:

```js
.ui([
  {
    "method": "size",
    "value": [ "export" , "import" ]
  }
])
```

The UI can be removed by passing ```false``` to the method.

#### <a name="object" href="#object">.ui( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| align | Sets the horizontal alignment of the UI elements. | ```"left"```, ```"center"```, ```"right"``` | ```"center"``` |
| border | Pixel border for all UI elements. | *number* | ```1``` |
| color | Object that sets the "primary" and "secondary" UI colors. <br><br> When only setting a "primary" color, the "secondary" is automatically calculated based on the "primary". | *object* | Default style |
| display | The display behavior of the UI elements. | ```"block"```, ```"inline-block"``` | ```"inline-block"``` |
| font | [[Font Styles]] for the UI elements. Currently supports passing a keyed *object* with the following keys: "align", "color", "decoration", "family", "size", "transform", and "weight". | *object* | Default style |
| margin | Pixel margin for all UI elements. | *number* | ```5``` |
| padding | Pixel padding for all UI elements. | *number* | ```5``` |
| position | The position of the container for all UI elements. | ```"top"``` , ```"right"``` , ```"bottom"``` , ```"left"``` | ```"bottom"``` |
| value | When passing only an *array* to the method, this is the variable that actually gets set. | *array*, ```false``` | ```false``` |
