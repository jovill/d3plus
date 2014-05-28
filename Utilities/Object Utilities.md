**D3plus** features a set of methods that relate to various object properties. These methods may be used outside of the normal constraints of the visualizations.

#### <a name="validate" href="#wiki-validate">d3plus.object.validate( *variable* )</a>

This function returns ```true``` if the variable passed is a literal javascript keyed *Object*. It's a small little function, but it catches some nasty edge-cases that can throw off your code (such as *Arrays* and ```null```).
