**D3plus** features a set of methods that relate to various font properties. These methods may be used outside of the normal constraints of the visualizations to help in dynamic web design.

#### <a name="awesome" href="#awesome">d3plus.font.awesome</a>


Returns a *boolean* stating whether or not the [Font Awesome](Dependencies#fontawesome) CSS library is loaded on the page. **D3plus** uses this internally to determine if it can use nicer icons when needed (instead of plain HTML entities).

#### <a name="validate" href="#validate">d3plus.font.validate( *array* | *string* )</a>

When dealing with rendering SVG to a static file (such as a PNG or PDF), the render will not display fonts correctly if a list of fonts is given (like with CSS). SVG requires a single font family to be specified.

To get around this, and to provide a fallback font for users who may not have a specific font installed, you can use this function to determine which font in a given list of fonts is installed on the computer the site is being rendered on.

This function can be passed either an *array* of font names, or a *string* with comma separated values (like with CSS standards). The function will return the first font family in the list that is usable for a given computer.

This function is directly inspired by **Derek Leung's** work, found [here](http://derek1906.site50.net/works/jfont.php).
