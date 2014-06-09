**D3plus** features a set of methods that relate to various object properties. These methods may be used outside of the normal constraints of the visualizations.

#### <a name="merge" href="#merge">d3plus.object.merge( *object* , *object* )</a><sup> ***new***</sup>

Given any two objects, this method will merge the two objects together, returning a new third object. The values of the second object always overwrite the first. Take a look at this example:

```js
var obj1 = {"id": 3, "color": "#cc0000"}
var obj2 = {"id": 7, "name": "Alex"}
var obj3 = d3plus.util.merge(obj1,obj2)
```

Here is what the newly created "obj3" variable looks like. Notice how the new object's "id" key is ```7``` and not ```3```. The second object's values always overwrite the first object's value.

```js
{"id": 7, "color": "#cc0000", "name": "Alex"}
```

#### <a name="validate" href="#validate">d3plus.object.validate( *variable* )</a>

This function returns ```true``` if the variable passed is a literal javascript keyed *Object*. It's a small little function, but it catches some nasty edge-cases that can throw off your code (such as *Arrays* and ```null```).
