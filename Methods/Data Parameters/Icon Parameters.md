#### <a name="string" href="#string">.icon( *string* )</a>

Defines the value for a data point's icon URL (shown in tooltips and the [[Legend]]). This is a great example of where you would probably want to pass the icon URL with [[Attribute Data]], as the icon probably does not change throughout time.

#### <a name="function" href="#function">.icon( *function* )</a>

You can also pass a *function* as a method of determining the icon URL for a data point. D3plus will pass the *function* the data point in question, and the function should return the value requested.

#### <a name="object" href="#object">.icon( *object* )</a>

This method also supports passing a keyed *object*. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
| button | Defines the graphic used on all UI buttons. The *string* can either be an HTML entity or a Font Awesome class. | ```false```, *string* | ```false``` |
| drop | Defines the graphic used on all UI drop down arrows. The *string* can either be an HTML entity or a Font Awesome class. | ```false```, *string* | **Font&nbsp;Awesome**:```"fa-angle-down"``` <br> **HTML Entity**:```"&#x276f;"``` (&nbsp;&#x276f;&nbsp;rotated&nbsp;90<sup>o</sup>&nbsp;)|
| select | Defines the graphic used on all selected UI elements. The *string* can either be an HTML entity or a Font Awesome class. | ```false```, *string* | **Font&nbsp;Awesome**:```"fa-check"``` <br> **HTML Entity**:```"&#x2713;"``` (&nbsp;&#x2713;&nbsp;)|
| style | Defines the icon style used in tooltips. ```"default"``` mode just shows the icon as is, while ```"knockout"``` will assume that the icon is an image with a transparent background, so **D3plus** will fill the background area with the object's current color. <br><br> You can also pass a single keyed *object*, keyed by the appropriate nesting level's [[Unique ID]], to define different styles for each nesting level. | ```"default"```, ```"knockout"``` | ```"default"``` |
| value | When passing only a *string* or *array* to the method, this is the variable that actually gets set. <br><br> You can also pass a single keyed *object*, keyed by the appropriate nesting level's [[Unique ID]]. This will tell **D3plus** to look in that specific nesting level's attribute list for the value. | *string*, *array*, *object* | ```"icon"``` |
