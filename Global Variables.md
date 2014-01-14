**D3plus** features some global public variables that you may find useful when developing your visualizations.

***

<a name="evt" href="#wiki-evt">#</a> d3plus.**evt**[event]

An object that contains several common javascript mouse events, depending on if a touch screen is present and/or they are using Internet Explorer. Touch events are only registered if you have included the [Modernizr](wiki/Dependencies#modernizr) library to detect touch screens. Here are the events featured in d3plus.**evt**:

|Key|Touch Device|Mouse (non-IE)|Mouse (IE)|
|---|---|---|---|
|click|touchend|click|click|
|down|touchstart|mousedown|mousedown|
|up|touchend|mouseup|mouseup|
|over|touchstart|mouseover|mouseenter|
|out|touchend|mouseout|mouseleave|
|move|touchmove|mousemove|mousemove|

***

<a name="ie" href="#wiki-ie">#</a> d3plus.**ie**

Returns a *boolean* stating whether or not the user is using Internet Explorer.

***

<a name="version" href="#wiki-version">#</a> d3plus.**version**

The current version of **D3plus** you are using. Returns a string in [semantic versioning](http://semver.org/) format.