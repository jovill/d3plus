SVG does not natively support wrapping text. Because of this, we created our own solution to break lines of SVG text at appropriate points, while also allowing the text to resize to fit the available space (if desired). Here are all of the available methods:

### <a name="container" href="#container">.container( *selector* )</a>

This required method tells **d3plus** which SVG text element to wrap text inside of. We support all of the [D3 Selection Methods](https://github.com/mbostock/d3/Selections#selecting-elements), including D3 elements.

For example, to select a text element with the ID of "box", you could say:

```js
.container( "text#box" )
```

Or alternatively, you could also say:

```js
.container( d3.select("text#box") )
```

**d3plus** will replace the contents of the text element with tspans for each line of text.

---

### <a name="dev" href="#dev">.dev( *Boolean* )</a>

Toggles verbose development mode, which displays logs and timers in the browser's console related to the activity on screen. Defaults to `false`.

---

### <a name="draw" href="#draw">.draw( )</a>

Wraps the text in the given [text container](Text Wrapping - Container Element).

---

### <a name="format" href="#format">.format( *locale* )</a>

Changes the language of the displayed console messages. Supports all of the available [Localizations](Localization) and defaults to `"en_US"`.

---

### <a name="height" href="#height">.height( *Number* )</a>

Sets the available inner bounding height to wrap text.

---

### <a name="resize" href="#resize">.resize( *Boolean* )</a>

Defines whether or not the text size in should be resized to fit the available space.

---

### <a name="shape" href="#shape">.shape( *String* )</a>

This defines the type of shape to fit the text in. Accepts `"circle"` and `"square"`, and defaults to `"square"`.

---

### <a name="size" href="#size">.size( *Array* )</a>

An *Array* of 2 *numbers* to be used as a minimum and maximum font size when [resizing](Text Wrapping Resizing) text.

---

### <a name="text" href="#text">.text( *String* )</a>

The *String* passed is used as the text to wrap.

---

### <a name="text-array" href="#text-array">.text( *Array* )</a>

Defines a list of value to try to use for labels. If the value of the first key does not fit in the allotted space, **d3plus** will then try to fit the second value, and so on.

---

### <a name="text-object" href="#text-object">.text( *Object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| html | Whether or not to use foreign elements instead of tspans. | *Boolean* | `false` |
| split | An array of characters to split the text, in addition to spaces. | *Array* | `["-", "/", ";", ":", "&"]` |
| value | When passing only a *String* or *Array* to the method, this is the variable that actually gets set. | *String*, *Array* | `false` |

---

### <a name="width" href="#width">.width( *Number* )</a>

Sets the available inner bounding width to wrap text.
