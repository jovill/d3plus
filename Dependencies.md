Here are the external javascript libraries/extensions that are required to use D3plus in its full capacity.

##<a name="d3" href="#wiki-d3">#</a> D3.js
Obviously, as this entire library is an extension of D3, you need to have D3 loaded for any of the code to work. You can download the most current version [here](http://d3js.org/d3.v3.zip).

##<a name="topojson" href="#wiki-topojson">#</a> TopoJSON
This D3 plug-in enables our Geo Map visualizations to accept topoJSON files instead of geoJSON files. TopoJSON files are quicker, more efficient, and have a smaller footprint than standard geoJSON files. Download the latest version [here](https://github.com/mbostock/topojson/blob/master/topojson.js).

##<a name="modernizr" href="#wiki-modernizr">#</a> Modernizr
We use Modernizr to detect if the user is on a touch device. This lets us treat touch and mouse events independantly, giving us appropriate interaction on both device types. You can build a custom download of Modernizr [here](http://modernizr.com/download/), just make sure to include "Touch Events", under the "Misc." heading.