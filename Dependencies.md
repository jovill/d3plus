#Dependencies
##<a id="d3">D3.js</a>
Obviously, as this entire library is an extension of D3, you need to have D3 loaded for any of the code to work. You can download the most current version [here](http://d3js.org/d3.v3.zip).
##<a id="tiles">Zoomable Tiles</a>
Zoomable Tiles is a D3 plug-in, developed by the guys at D3, that enables our Geo Map visualization to use Google Map tiles. Download the latest version [here](https://github.com/d3/d3-plugins/blob/master/geo/tile/tile.js). 
##<a id="topojson">TopoJSON</a>
This is another D3 plug-in that enables our Geo Map visualizations to accept topoJSON files instead of geoJSON files. TopoJSON files are quicker, more efficient, and have a smaller footprint than standard geoJSON files. Download the latest version [here](https://github.com/mbostock/topojson/blob/master/topojson.js).
##<a id="modernizr">Modernizr</a>
We use Modernizr to detect if the user is on a touch device. This lets us treat touch and mouse events independantly, giving us appropriate interaction on both device types. You can build a custom download of Modernizr [here](http://modernizr.com/download/), just make sure to include "Touch Events", under the "Misc." heading.