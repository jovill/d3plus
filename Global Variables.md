**D3plus** features some global public variables that you may find useful when developing your content.
##<a id="version">d3plus.version</a>
Useful for checking which version of **D3plus** you are using. Returns a string in [semantic versioning](http://semver.org/) format.

##<a id="timing">d3plus.timing</a>
Returns the current time, in milliseconds, that all **D3plus** visualizations use for transitions. This value can be changed to any integer in order to customize your visualizations. Default value is **600**.

##<a id="ie">d3plus.ie</a>
Returns a *boolean* stating whether or not the user is using Internet Explorer.

##<a id="evt">d3plus.evt[event]</a>
d3plus.evt is an object that contains several common javascript mouse events, depending on if a touch screen is present and/or they are using Internet Explorer. Touch events are only registered if you have included the [Modernizr](wiki/Dependencies#modernizr) library to detect touch screens. Here are the events featured in d3plus.evt:

<table>
  <tr>
    <th>Key</th><th>Touch Screen</th><th>Mouse (non-IE)</th><th>Mouse Value (IE)</th>
  </tr>
  <tr>
    <td>click</td>
    <td>touchend</td>
    <td>click</td>
    <td>click</td>
  </tr>
  <tr>
    <td>down</td>
    <td>touchstart</td>
    <td>mousedown</td>
    <td>mousedown</td>
  </tr>
  <tr>
    <td>up</td>
    <td>touchend</td>
    <td>mouseup</td>
    <td>mouseup</td>
  </tr>
  <tr>
    <td>over</td>
    <td>touchstart</td>
    <td>mouseover</td>
    <td>mouseenter</td>
  </tr>
  <tr>
    <td>out</td>
    <td>touchend</td>
    <td>mouseout</td>
    <td>mouseleave</td>
  </tr>
  <tr>
    <td>mover</td>
    <td>touchmove</td>
    <td>mousemove</td>
    <td>mousemove</td>
  </tr>
</table>