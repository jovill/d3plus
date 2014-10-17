**d3plus** includes advanced, cross-browser form styling and behavior that helps make normal HTML forms beautiful and reliable. Here are the supported form types:

* Buttons
* Dropdown Menus
* Radio Toggles
* Auto Detect

Here are some example usages:

| Converting Existing HTML Forms | Creating Forms from Javascript | Using Forms in Visualizations | Forms with Nested Data |
| :-: | :-: | :-: | :-: |
| <a href="http://d3plus.org/examples/forms/62d1df2506fd7c73b4c6/"><img src="https://gist.githubusercontent.com/davelandry/62d1df2506fd7c73b4c6/raw/thumbnail.png" width="100px"></a> | <a href="http://d3plus.org/examples/forms/8ea69aa2266c39d35380/"><img src="https://gist.githubusercontent.com/davelandry/8ea69aa2266c39d35380/raw/thumbnail.png" width="100px"></a> | <a href="http://d3plus.org/examples/basic/2ce67895efd23771943b/"><img src="https://gist.githubusercontent.com/davelandry/2ce67895efd23771943b/raw/thumbnail.png" width="100px"></a> | <a href="http://d3plus.org/examples/forms/55bbd9665eb1a8019c68/"><img src="https://gist.githubusercontent.com/davelandry/55bbd9665eb1a8019c68/raw/thumbnail.png" width="100px"></a> |

# Available Methods

### <a name="active" href="#active">.active( *String* | *Number* | *Array* | *Function* )</a>

Defines any "active" data points in your Form. For example, used in drop down forms to show selected values in the list.

---

### <a name="alt" href="#alt">.alt( *String* | *Object* )</a>

Defines the value in your data associated with the alternative text of each element.

As with some of the other methods, an *Object* can be passed to this method. Here are the keys accessible by the user:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *Function*, *Array* | `[]` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *Function*, *Array* | `[]` |
| value | When passing only a *String* to this method, this is the variable that actually gets set. | *String*, *Array* | `"alt"` |

---

### <a name="color" href="#color">.color( *String* )</a>

Defines the value in your data associated with the color of each node. If the value is a hexadecimal color *String* (eg. `"#cc0000"`), **d3plus** will simply use that as the node's color. If the value is a non-color *String* or *Number*, a random color based on that string will be used.

---

### <a name="container" href="#container">.container( *selector* )</a>

Tells **d3plus** which page element to build the form inside of. It supports all of the [D3 Selection Methods](https://github.com/mbostock/d3/Selections#selecting-elements), including D3 elements.

---

### <a name="data" href="#data">.data( *Array* | *selector* | *url* | *Object* [, *callback* ] )</a>

Sets the data associated with your visualization. Either an *Array* of data objects, or a *selector* for an already existing HTML form element from which to extract the data.

When passing a *URL* to the data method, **d3plus** will use it to load the data dynamically for you. If a *callback* function is provided, the downloaded data will be passed through the function for formatting (which should then return the correctly formatted data).

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| delimiter | The string delimiter used when parsing DSV files from a *url*. | *String* | "&#124;" |
| filetype | The file extension when loading data from a *url*. If set to `false`, **d3plus** will try to auto-detect. | `false`, `"json"`, `"xml"`, `"html"`, `"csv"`, `"dsv"`, `"tsv"`, `"txt"` | `false` |
|sort|Whether or not the form should sort the data values being passed.|*Boolean*| `true` |

---

### <a name="depth" href="#depth">.depth( *integer* )</a>

If you have specified nesting while setting [.id( )](#id), then this method allows you to switch between those nesting levels. It accepts integer values that match the desired position in the nesting array.

For example, given the following nesting:

```js
.id( [ "country" , "state" , "city" ] )
```

You would show `"state"` aggregations by setting the depth as follows:

```js
.depth( 1 )
```

---

### <a name="dev" href="#dev">.dev( *Boolean* )</a>

Toggles verbose development mode, which displays logs and timers in the browser's console related to the activity on screen. Defaults to `false`.

---

### <a name="draw" href="#draw">.draw( )</a>

Draws, and redraws, the **d3plus** form, based on the methods set and/or changed.

---

### <a name="focus" href="#focus">.focus( *String* | *Number* )</a>

This defines which data node to focus on. The value passed much match a [unique ID](#id) in your data.

---

### <a name="font" href="#font">.font( *String* | *Array* | *Object* )</a>

Sets the default overall font family(s) to be used. This method also supports passing a keyed *Object*. Here are the accepted keys:

| Key | Description | Accepted Value(s) | Default Value |
| --- | --- | --- | --- |
| align | Sets the global font alignment. | `"left"`, `"center"`, `"right"` | `"left"` |
| color | Sets the color of all fonts used in the visualization. | *color* | `"#444444"` |
| decoration | Sets the text-decoration of all fonts used in the visualization. | `"line-through"`, `"none"`, `"overline"`, `"underline"` | `"none"` |
| family | Sets the font-family used throughout the entire visualization. Can be a single *String*, *Array*, or comma-separated font-families (like with CSS). This is the value that gets set when only passing a *String* to the method. | *Array*, *String* | `[ "Helvetica Neue" , "HelveticaNeue" ` `, "Helvetica" , "Arial" , "sans-serif" ]` |
| secondary | Defines a secondary font style. For example, the drop down menu. | *Object* | Same as primary font style. |
| size | General pixel font size. | *Number* | `12` |
| spacing | General pixel letter spacing. | *Number* | `0` |
| transform | Sets the text-transform of all fonts used in the visualization. | `"capitalize"`, `"lowercase"`, `"none"`, `"uppercase"` | `"none"` |
| weight | Sets the font-weight of all fonts used in the visualization. | *String* or *Number* | `200` |

---

### <a name="format" href="#format">.format( *String* | *Function* | *Object* )</a>

Passing a *String* to the method changes the current locale used to display text and numbers. Here are the [supported languages](Localization). Passing a *Function* overrides the default value formatting behavior, which tests whether a value is a *String* or a *Number*, and then passes it through the correct formatting function. It is not recommended that you change this *Function*, but rather edit the specific text and number functions in the object, as seen below when passing an *Object*:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| locale | When passing only a *String* to the method, this is the variable that actually gets set. | *String* | `"en_US"` |
| number | The function that formats all *Number* values displayed on the screen. <br><br> This is helpful when you would like specific variables to always be formatted a certain way, whether it's to a certain decimal place or replacing commas with periods for international usage. **d3plus** passes 2 variables to the function you provide: the number that needs to be formatted, and the key associated with that number. | *Function* | Custom formatting function. |
| text | The function that formats all *String* values displayed on the screen. <br><br> This is helpful for displaying certain short javascript keys as their full capitalized names, and also enables you to implement additional localization for your form. **d3plus** passes 2 variables to the function you provide: the *String* that needs to be formatted, and the key associated with that *String*. | *Function* | Custom formatting function. |
| value | When passing only a *Function* to the method, this is the variable that actually gets set. | *Function* | Custom formatting function. |

Say for instance, you wanted all numbers for the key "year" to return as-is, and all other numbers formatted to 2 decimal places. You would pass the following *Function* to the "number" key:

```js
.format({ "number" : function( number , key ) {

    if (key === "year") {
      return number;
    }
    else {
      return d3.round(number,2);
    }

  }
})
```

In addition, if you wanted to display the key "export_val" as "Export Value" and capitalize all other strings. You would pass the following function to the text key:

```js
.format({ "text" : function( text , key ) {

    if (key === "export_val") {
      return "Export Value";
    }
    else {
      return text.charAt(0).toUpperCase() + text.substr(1).toLowerCase();
    }

  }
})
```

---

### <a name="height" href="#height">.height( *Number* | *Object* )</a>

Sets the height, in pixels, of the form. This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| secondary | Sets the height of secondary elements, such as the dropdown window in the "drop" Form. <br><br> If set to `false`, the height will be calculated based on the available space inside of the current window. | *Number*, `false` | `false` |
| max | Sets the max-height of secondary elements, such as the dropdown window in the "drop" Form. Auto-calculated if the value is `false`. | *Number*, `false` | `600` |
| value | When passing only a *Number* to the method, this is the variable that actually gets set. Auto-calculated if the value is `false`. | *Number*, `false` | `false` |

---

### <a name="hover" href="#hover">.hover( *String* | *Number* )</a>

This defines which data point's hover event should be triggered.

---

### <a name="icon" href="#icon">.icon( *String* | *Object* )</a>

Defines the value for a data point's image icon URL. This method also supports passing a keyed *Object* to change advanced options. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| back | Defines the graphic used with nested drop down menus. The *String* can either be an HTML entity or a Font Awesome class. | `false`, *String* | **Font&nbsp;Awesome**:`"fa-angle-left"` <br> **HTML Entity**:`"&#x276e;"`|
| button | Defines the graphic used on all UI buttons. The *String* can either be an HTML entity or a Font Awesome class. | `false`, *String* | `false` |
| drop | Defines the graphic used on all UI drop down arrows. The *String* can either be an HTML entity or a Font Awesome class. | `false`, *String* | **Font&nbsp;Awesome**:`"fa-angle-down"` <br> **HTML Entity**:`"&#x276f;"` (&nbsp;&#x276f;&nbsp;rotated&nbsp;90<sup>o</sup>&nbsp;)|
| next | Defines the graphic used with nested drop down menus. The *String* can either be an HTML entity or a Font Awesome class. | `false`, *String* | **Font&nbsp;Awesome**:`"fa-angle-right"` <br> **HTML Entity**:`"&#x276f;"`|
| select | Defines the graphic used on all selected UI elements. The *String* can either be an HTML entity or a Font Awesome class. | `false`, *String* | **Font&nbsp;Awesome**:`"fa-check"` <br> **HTML Entity**:`"&#x2713;"` (&nbsp;&#x2713;&nbsp;)|
| style | Defines the icon style used in tooltips. `"default"` mode just shows the icon as is, while `"knockout"` will assume that the icon is an image with a transparent background, so **d3plus** will fill the background area with the object's current color. <br><br> You can also pass a single keyed *Object*, keyed by the appropriate nesting level's [.id( )](#id), to define different styles for each nesting level. | `"default"`, `"knockout"` | `"default"` |
| value | When passing only a *String* to the method, this is the variable that actually gets set. | *String* | `"icon"` |

---

### <a name="id" href="#id">.id( *String* | *Array* | *Object* )</a>

Defines the accessor key to be used as each data point's unique identifier. When passing an *Array* to this method, **d3plus** will use each item in the *Array* as a different level of nesting for the data. Additionally, as with some of the other methods, an *Object* can be passed to this method. Here are the keys accessible by the user:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *Function*, *Array* | `[]` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *Function*, *Array* | `[]` |
| value | Defines the accessor key to be used as each data point's unique identifier. When passing only a *String* or *Array* to this method, this is the variable that actually gets set. | *String*, *Array* | `"value"` |

---

### <a name="keywords" href="#keywords">.keywords( *String* )</a>

Defines the value in your data associated with the keywords for each element. These keywords are used to improve the [search box](#search) results.

---

### <a name="margin" href="#margin">.margin( *Number* | *String* )</a>

Defines the pixel margins, on all sides, of the overall element. You can also pass a standard **CSS** *String* to define the margin. For example, to set the top and bottom margins to `10` and the left and right margins to `20`, you would pass the following:

```js
.margin( "10px 20px" )
```

---

### <a name="open" href="#open">.open( *Boolean* )</a>

Whether or not a drop down menu is opened or closed. Defaults to `false`.

---

### <a name="order" href="#order">.order( *String* | *Object* )</a>

Sets the value to use when trying to order data points. This method also supports passing a keyed *Object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| sort | Changes the sort order of the data between ascending and descending. | `"asc"`, `"desc"` |`"asc"` |
| value | When passing only a *String* to the method, this is the variable that actually gets set. | *String*, `false` | `false` |

---

### <a name="remove" href="#remove">.remove( )</a>

Destroys the entire **d3plus** form element.

---

### <a name="search" href="#search">.search( *Boolean* )</a>

Enables/disables a search box in drop down menus. Defaults to `"auto"`, which will enable the search box if there are more than 10 items in the list.

---

### <a name="select" href="#select">.select( *selector* )</a>

Returns a specific D3 selection inside of the [.container( )](#container). This method support all of the [D3 Selection Methods](https://github.com/mbostock/d3/Selections#selecting-elements), including D3 elements.

---

### <a name="selectAll" href="#selectAll">.selectAll( *selector* )</a>

Returns an array of D3 selections inside of the [.container( )](#container). This method support all of the [D3 Selection Methods](https://github.com/mbostock/d3/Selections#selecting-elements), including D3 elements.

---

### <a name="text" href="#text">.text( *String* )</a>

Defines the value used when labeling elements. When not defined, **d3plus** defaults to using the [.id( )](#id) value for all labeling. This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| mute | Hides specific data points from the viewer. Full documentation can be found [here](Data-Filtering#mute). | **value**, *Function*, *Array* | `[]` |
| solo | Shows only specific data points to the viewer. Full documentation can be found [here](Data-Filtering#solo). | **value**, *Function*, *Array* | `[]` |
| value | When passing only a *String* to the method, this is the variable that actually gets set. | *String*, `false` | `false` |

---

### <a name="timing" href="#timing">.timing( *Object* )</a>

This method only supports passing a keyed *Object*. Here are the accepted keys:

| Key | Description | Accepted Value(s) | Default |
| --- | --- |
| mouseevents | The time, in milliseconds, for hover events. | *Number* | `60` |
| ui | The time, in milliseconds, for UI element behavior (ex. drop down open/close). | *Number* | `200` |

---

### <a name="title" href="#title">.title( *String* | *Object* )</a>

Defines a title for a form. To remove the title, simply pass `false` to the method. Here are the supported keys when passing an *Object*:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| font | Font styles for the main title. Currently supports passing a keyed *Object* with the following keys: "align", "color", "decoration", "family", "size", "transform", "weight". | *Object* | Default style |
| link | A URL for the title to open when clicked. The page will open in a new window/tab. | *String* | `false` |
| value | When passing only a *String* to the method, this is the variable that actually gets set.<br><br>Can be removed by passing `false`. | *String*, `false` | `false` |

---

### <a name="type" href="#type">.type( *String* )</a>

Sets the current form type. Here are the currently availables values: `"auto"`, `"button"`, `"drop"`, `"toggle"`.

---

### <a name="ui" href="#ui">.ui( *Array* )</a>

Defines styles for the UI elements. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| border | Pixel border for all UI elements. | *Number* | `1` |
| color | Object that sets the "primary" and "secondary" UI colors. <br><br> When only setting a "primary" color, the "secondary" is automatically calculated based on the "primary". | *Object* | Default style |
| display | The display behavior of the UI elements. | `"block"`, `"inline-block"` | `"inline-block"` |
| font | [[Font Styles]] for the UI elements. Currently supports passing a keyed *Object* with the following keys: "align", "color", "decoration", "family", "size", "transform", and "weight". | *Object* | Default style |
| margin | Pixel margin for all UI elements. | *Number* | `5` |
| padding | Pixel padding for all UI elements. | *Number* | `5` |

---

### <a name="width" href="#width">.width( *Number* | *Object* )</a>

Sets the width, in pixels, of the current form. This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| secondary | Sets the width of secondary elements, such as the dropdown window in the "drop" Form. <br><br> If set to `false`, the width will be calculated based on the width of the primary element. | *Number*, `false` | `false` |
| value | When passing only a *Number* to the method, this is the variable that actually gets set. If `false`, it is calculated based on either the defined width of the container or the width of each element displayed. | *Number*, `false` | `false` |
