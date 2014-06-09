#### <a name="string" href="#string">.title( *string* )</a>

Defines the title of the visualization. **D3plus** will place the supplied *string* above the visualization, wrapping the lines if they are too long to fit.

To remove the title, simply pass ```false``` to the method.

#### <a name="object" href="#object">.title( *object* )</a>

This method also supports passing a keyed object. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| font | [[Font Styles]] for the main title. Currently supports passing a keyed *object* with the following keys: "align", "color", "decoration", "family", "size", "transform", "weight". | *object* | Default style |
| height | Minimum pixel height for the main title. If ```false```, **D3plus** determines the appropriate amount of vertical space automatically. | *number*, ```false``` | ```false``` |
| padding | Pixel padding for the main title. If ```false```, **D3plus** determines the appropriate amount of vertical space automatically. | *number* | ```2``` |
| position | What side of the visualization the title should be positioned on. | ```"top"```, ```"bottom"``` | ```"top"``` |
| link | A URL for the title to open when clicked. The page will open in a new window/tab. | *string* | ```false``` |
| sub | Defines the sub-title of the visualization. This is a smaller title that gets positioned directly under the main title.<br><br>Can be removed by passing ```false```. <br><br> Can also be provided the following keys similar to the main title: "font", "padding", "position", "link". | *string*, ```false```, *object* | ```false``` |
| total | Toggles a title line that appears underneath both the main title and sub-title that displays the total value of all of the data currently being shown (using whichever [[Custom Aggregations]] are defined for the current [[Sizing Data]] value). <br><br> Instead of passing ```true```, you can pass an *object* with "prefix" and/or "suffix" keys, whose values will be displayed on either side of the calculated total value. Will be removed by passing ```false```. <br><br> Can also be provided the following keys similar to the main title: "font", "padding", "position", "link". | *boolean*, *object* | ```false``` |
| width | Minimum pixel width for the main title. If ```false```, **D3plus** determines the appropriate amount of horizontal space automatically. | *number*, ```false``` | ```false``` |
| value | Defines the title of the visualization. When passing only a *string* to the method, this is the variable that actually gets set.<br><br>Can be removed by passing ```false```. | *string*, ```false``` | ```false``` |
