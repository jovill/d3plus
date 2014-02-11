**D3plus** features some global public variables that you may find useful when developing your visualizations.

***

<a name="evt" href="#wiki-evt">#</a> d3plus.**evt**[event]

An object that contains several common javascript mouse events, depending on if a touch screen is present and/or they are using Internet Explorer. Touch events are only registered if you have included the [Modernizr](Dependencies#modernizr) library to detect touch screens. Here are the events featured in d3plus.**evt**:

|Key|Touch Device|Mouse (non-IE)|Mouse (IE)|
|---|---|---|---|
|click|touchend|click|click|
|down|touchstart|mousedown|mousedown|
|up|touchend|mouseup|mouseup|
|over|touchstart|mouseover|mouseenter|
|out|touchend|mouseout|mouseleave|
|move|touchmove|mousemove|mousemove|

***

<a name="fontawesome" href="#wiki-fontawesome">#</a> d3plus.**fontawesome**

Returns a *boolean* stating whether or not the [Font Awesome](Dependencies#wiki-fontawesome) CSS library is loaded on the page.

***

<a name="ie" href="#wiki-ie">#</a> d3plus.**ie**

Returns a *boolean* stating whether or not the user is using Internet Explorer.

***

<a name="rtl" href="#wiki-rtl">#</a> d3plus.**rtl**

Returns a *boolean* stating whether or not the HTML page is in "Right to Left" text direction mode. This is used for languages that are written right to left, such as Arabic.

***

<a name="scrollbar" href="#wiki-rtl">#</a> d3plus.**scrollbar**()

Returns an *number* value that is the width of the browser's scrollbar. This is useful when having to manually set the width of a scrolling div.

***

<a name="version" href="#wiki-version">#</a> d3plus.**version**

The current version of **D3plus** you are using. Returns a string in [semantic versioning](http://semver.org/) format.