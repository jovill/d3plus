#Required Dependencies

###<a name="d3" href="#wiki-d3">#</a> D3.js

Obviously, as this entire library is an extension of D3, you need to have D3 loaded for any of the code to work. You can download the most current version [here](http://d3js.org/d3.v3.zip).

***

#Optional Dependencies

The following libraries are optional, and should be used when you need them.

###<a name="fontawesome" href="#wiki-fontawesome">#</a> Font-Awesome

Font Awesome is a CSS library that contains beautiful scalable vector based icons. Currently, Font Awesome is used in the beta d3plus.ui() code, and will be used more extensively in future versions of **D3plus**. [Visit their site](http://fontawesome.io/) to learn more about Font Awesome.

###<a name="modernizr" href="#wiki-modernizr">#</a> Modernizr

**D3plus** can use Modernizr to detect if the user is on a touch device. This lets **D3plus** treat touch and mouse events independantly, giving us appropriate interaction on both device types. You can build a custom download of Modernizr [here](http://modernizr.com/download/), just make sure to include "Touch Events", under the "Misc." heading.

###<a name="topojson" href="#wiki-topojson">#</a> TopoJSON

This D3 plug-in enables the [Geo Map](Visualization-Types#wiki-geo_map) visualization to accept topoJSON files instead of geoJSON files. TopoJSON files are quicker, more efficient, and have a smaller footprint than standard geoJSON files. Download the latest version [here](https://github.com/mbostock/topojson/blob/master/topojson.js).