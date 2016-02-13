**d3plus.client** contains a set utilities that provide information about the user's browser.

### <a name="css" href="#css">d3plus.client.css( *String* )</a>

Returns a *Boolean* stating whether or not the specified stylesheet has been loaded on the page.

### <a name="ie" href="#ie">d3plus.client.ie</a>

Returns a *Boolean* stating whether or not the user is using Internet Explorer.

### <a name="pointer" href="#pointer">d3plus.client.pointer</a>

An object that contains several common javascript mouse events, depending on if a touch screen is present and/or they are using Internet Explorer. Here are the events available:

| Key | Touch Device | Mouse (non-IE) | Mouse (IE) |
| --- | --- | --- | --- |
| click | touchend | click | click |
| down | touchstart | mousedown | mousedown |
| up | touchend | mouseup | mouseup |
| over | touchstart | mouseover | mouseenter |
| out | touchend | mouseout | mouseleave |
| move | touchmove | mousemove | mousemove |

### <a name="prefix" href="#prefix">d3plus.client.prefix( )</a>

Returns a *String* containing the appropriate vendor prefix for the current browser.

### <a name="rtl" href="#rtl">d3plus.client.rtl</a>

Returns a *Boolean* stating whether or not the HTML page is in "Right to Left" text direction mode. This is used for languages that are written right to left, such as Arabic.

### <a name="scroll" href="#scroll">d3plus.client.scroll.x() and y()</a>

Returns the current page scroll position.

### <a name="scrollbar" href="#scrollbar">d3plus.client.scrollbar( )</a>

Returns an *Number* value that is the width of the browser's scrollbar. This is useful when having to manually set the width of a scrolling div.

### <a name="touch" href="#touch">d3plus.client.touch</a>

Returns a *Boolean* stating whether or not the user's device supports touch events.
