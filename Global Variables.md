**D3plus** features some global public variables that you may find useful when developing your visualizations.

#### <a name="evt" href="#wiki-evt">d3plus.evt</a>

An object that contains several common javascript mouse events, depending on if a touch screen is present and/or they are using Internet Explorer. Here are the events available:

| Key | Touch Device | Mouse (non-IE) | Mouse (IE) |
| --- | --- | --- | --- |
| click | touchend | click | click |
| down | touchstart | mousedown | mousedown |
| up | touchend | mouseup | mouseup |
| over | touchstart | mouseover | mouseenter |
| out | touchend | mouseout | mouseleave |
| move | touchmove | mousemove | mousemove |

#### <a name="ie" href="#wiki-ie">d3plus.ie</a>

Returns a *boolean* stating whether or not the user is using Internet Explorer.

#### <a name="prefix" href="#wiki-prefix">d3plus.prefix( )</a>

Returns a *string* containing the appropriate vendor prefix for the current browser.

#### <a name="rtl" href="#wiki-rtl">d3plus.rtl</a>

Returns a *boolean* stating whether or not the HTML page is in "Right to Left" text direction mode. This is used for languages that are written right to left, such as Arabic.

#### <a name="scrollbar" href="#wiki-rtl">d3plus.scrollbar( )</a>

Returns an *number* value that is the width of the browser's scrollbar. This is useful when having to manually set the width of a scrolling div.

#### <a name="version" href="#wiki-version">d3plus.version</a>

The current version of **D3plus** you are using. Returns a string in [semantic versioning](http://semver.org/) format.
